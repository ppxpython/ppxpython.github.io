---
title: locust+prometheus+grafana压测
abbrlink: 47799
date: 2022-09-15 15:23:35
tags:
---
# 了解压测

## 为什么要压测和目标

> 这个问题有很多答案，而每个人内心的答案可能都是不同的。

1. 项目上线稳定后，对系统的评估
2. 系统研发后期，对系统的检验
3. 活动前，摸高压测，预估流量
4. 线上出现性能问题
5. 合作活动、系统，对方要求上线前压测

**目标**：

* 新服务，无预估目标，需要通过压测得到服务基准数据或找到系统瓶颈进行优化
* 有明确的压测目标，需要通过压测确定服务的各项指标是否达标
* 常态化压测，为后期性能优化指导方向或提供参考依据

## 压测的分类

![](https://pic.imgdb.cn/item/6322d41916f2c2beb1e33f1e.jpg)

![](https://pic.imgdb.cn/item/6322d45416f2c2beb1e3a08e.jpg)

## 压力测试指标

### 基础的关注点

#### QPS

每秒处理的请求个数， “**每秒查询率**”，是**一台服务器每秒能够响应的查询次数**，是对一个特定的查询服务器在规定时间内所处理流量多少的衡量标准。 单位是`request/s`。`每秒处理的请求数量`。

#### TPS

Transactions Per Second的缩写，也就是**事务数/秒**。它是软件测试结果的测量单位。一个事务是指一个客户机向服务器发送请求然后服务器做出反应的过程。**客户机在发送请求时开始计时，收到服务器响应后结束计时，以此来计算使用的时间和完成的事务个数**。TPS <= QPS

#### RPS

Requests Per Second的缩写，**每秒能处理的请求数目。**等效于QPS

这三个过程，每秒能够完成N个这三个过程，Tps也就是N；

Qps基本类似于Tps，但是不同的是， **对于一个页面的一次访问** ，形成一个Tps；但 **一次页面请求，可能产生多次对服务器的请求** ，服务器对这些请求，就可计入“Qps”之中。

例如：访问一个页面会请求服务器3次，一次放，产生一个“T”，产生3个“Q”

#### RT

#响应时间#，这个指标比较多，比如，最小响应时间、平均响应时间、最大响应时间等等，详细指标还有`P50`、`P95`、`P99` 等等`响应时间`(RT)是指用户从客户端发出请求到接收完服务器返回结果的整个过程所需花费的时间，包含网络传输时间以及服务器处理时间。

#### VU

虚拟用户，**系统模拟并发的用户**。主要目的是最大程度的模拟用户操作，从而得到较为准确的压测数据，这个参数一般由压测人员制定，梯度递增。

```js
阶段1: 50虚拟用户，压测1小时；
阶段2: 100虚拟用户，压测1小时；
阶段3: 150虚拟用户，压测1小时；
阶段4: 200虚拟用户，压测1小时；
阶段5: 250虚拟用户，压测1小时；
```

一般在为达到最佳负载的情况下，`QPS` 会随着`VU`的数量等比递增。 比如，`50VU`下的`QPS`是`1000`，那么`100VU`下的`QPS`会接近`2000` 。

#### 操作系统负载、外部系统等

压测期间，还需要关注下服务器的负载、网络 IO 情况，如果涉及到外围系统，比如 Mysql、Redis 等，那么也要纳入观察范围。所以也就需要运维同学查看监控的读写情况。


列举一些常用指标，并不一定都需要关注，根据业务考虑指标的细化粒度。

* QPS：Query Per Second，每秒处理的请求个数
* TPS：Transactions Per Second，每秒处理的事务数，TPS <= QPS
* RT： Response Time，响应时间，等价于Latency RT分平均延时，Pct延时（Percentile分位数）。平均值不能反映服务真实响应延时，实际压测中一般参考Pct90，Pct99等指标
* CPU使用率：出于节点宕机后负载均衡的考虑，一般 CPU使用率 < 75% 比较合适
* 内存使用率：内存占用情况，一般观察内存是否有尖刺或泄露

![](https://pic.imgdb.cn/item/6322d47b16f2c2beb1e3f4d1.jpg)

### 学会观察

#### 运行良好的特征

* 测试期间响应时间呈平稳趋势；
* 请求速率遵循与虚拟用户相同的斜坡（如果 VU 增加，则请求速率也会增加）；

#### 达到最大吞吐量的特征

* 随着虚拟用户数量的增加，活动的正在进行中的请求数量继续增加，而 QPS（完成的请求）却趋于平稳（甚至下降）。此时，系统过载，从而导致更长的响应时间。
* HTTP 失败率增加

#### 性能问题/瓶颈的特征

* 测试期间响应时间显著增加；

  【ge:在引擎鉴权测试时并发到达2000开始出现TR明显变长】
* 响应时间显著增加，然后迅速触底并保持平稳（HTTP 被降级了）；
* QPS 不会随着 VU 的增加而增加，并且响应时间开始增加，疑似达到最大吞吐量；

#### 发生故障的特征

* 高 HTTP 错误率
* 低 QPS 下的系统高负载

大概呈现的趋势为

除了前面说到的情况，肯定还有一些我们无法下手的三无接口，无参考、无预估、无历史数据，这时候只能一点一点来，慢慢把压力提上去的同时收集数据，最终得出接口的最优处理能力。

最佳并发用户数（The Optimum Number of Concurrent Users）

最大并发用户数（The Maximum Number of Concurrent Users）

资源的利用情况（Utilization，包括硬件资源和软件资源）、

吞吐量（Throughput，这里是指每秒事务数）

响应时间（Response Time）

坐标轴的横轴从左到右表现了并发用户数（Number of Concurrent Users）的不断增长。

![常见性能折线图](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/5/3/171db0b40cbc0832~tplv-t2oaga2asx-zoom-in-crop-mark:3024:0:0:0.awebp)

资源占用达到饱和，吞吐量增长明显放缓甚至停止增长，而响应时间却进一步延长
![](https://pic.imgdb.cn/item/6322d49d16f2c2beb1e4345b.jpg)

蓝线表示 TPS，黄色表示响应时间

在 TPS 增加的过程中，响应时间一开始会处在较低的状态，也就是在 A 点之前。接着响应时间开始有些增加，直到业务可以承受的时间点 B，这时 TPS 仍然有增长的空间。再接着增加压力，达到 C 点时，达到最大 TPS。我们再接着增加压力，响应时间接着增加，但 TPS 会有下降。

# locust

## locust原理

### What is Locust？

一个易于使用的分布式用户**负载测试工具**。它旨在对网站（或其他系统）进行**负载测试**，并确定一个系统可以处理多少并发用户。

Locust是完全基于**事件**的，因此可以在单台机器中支持数以千计的用户在线。和其它基于事件的程序相比较，它是不需要使用回调的。相反，它通过gevent使用轻量级的进程。每一个locust测试你的网站时，实际上是真实的在内部运行它自己的进程(或greenlet自行调度的微线程,准确的说)。这样就允许你不使用复杂的回调方法，而是使用Python编写复杂的场景。

Locust 在英文中是 `蝗虫` 的意思：

作者的想法是，在测试期间，放一大群 [蝗虫](https://en.wikipedia.org/wiki/Locust) 攻击您的网站。

### What is Gevent？

gevent是一个基于协程的Python网络库，它使用greenlet在libev或libuv事件循环之上提供一个高级的同步API

`在Python中实现协程的第三方库。协程又叫微线程Corouine。使用gevent可以获取极高的并发能力`

![](https://pic.imgdb.cn/item/6322d4c116f2c2beb1e47e93.jpg)


#### 并发机制

①Locust的并发机制采用协程（gevent）的机制。

②采用多线程来模拟多用户时，线程数会随着并发数的增加而增加，而线程之间的切换是需要占用资源的，IO的阻塞和线程的sleep会不可避免的导致并发效率下降；正因如此，LoadRunner和Jmeter这类采用进程和线程的测试工具，都很难在单机上模拟出较高的并发压力。

③而协程和线程的区别在于：协程避免了系统级资源调度，由此大幅提高了性能。

④正常情况下，单台普通配置的测试机可以生产数千并发压力，这是LoadRunner和Jmeter都无法实现的。

[协程](https://so.csdn.net/so/search?q=%E5%8D%8F%E7%A8%8B&spm=1001.2101.3001.7020)又称为微线程，纤程。英文名Coroutine:协程是一种用户态的轻量级线程
协程拥有自己的[寄存器](https://so.csdn.net/so/search?q=%E5%AF%84%E5%AD%98%E5%99%A8&spm=1001.2101.3001.7020)上下文和栈。协程调度切换时，将寄存器上下文和栈保存到其他地方，在切回来的时候，恢复之前保存的寄存器上下文和栈

![](https://pic.imgdb.cn/item/6322d4e216f2c2beb1e4c274.jpg)

### 特点

①、不需要编写笨重的UI或者臃肿的XML代码，基于协程而不是回调，脚本编写简单易读；

②、有一个基于we简洁的HTML+JS的UI用户界面，可以实时显示相关的测试结果；

③、支持分布式测试，用户界面基于网络，因此具有跨平台且易于扩展的特点；

④、所有繁琐的I / O和协同程序都被委托给gevent，替代其他工具的局限性；

同样配置下，单台负载机可模拟的负载数远超jmeter

![](https://pic.imgdb.cn/item/6322d4fa16f2c2beb1e4f1ea.jpg)

#### Loucst执行流程

具体流程如下：
①先执行WebsiteTasks中的on_start（只执行一次），作为初始化；

②从WebsiteTasks中随机挑选（如果定义了任务间的权重关系，那么就按照权重关系随机挑选）一个任务执行；

③根据Locust类中min_wait和max_wait定义的间隔时间范围（如果TaskSet类中也定义了min_wait或者max_wait，以TaskSet中的优先），在时间范围中随机取一个值，休眠等待；

④重复2~3步骤，直到测试任务终止。

![](https://pic.imgdb.cn/item/6322d51116f2c2beb1e52182.jpg)

### Locust 核心类介绍

#### TaskSet()

定义了每个用户的任务集合，测试任务开始后，每个Locust用户会从TaskSet中随机挑选（如果定义了任务间的权重关系，那么就是按照权重关系随机挑选）一个任务执行，然后随机等待Locust类中定义的min_wait和max_wait（如果TaskSet类中也定义了min_wait或者max_wait，按照TaskSet中的为准）之间的一段时间，执行下一个任务。

```AssertionError:
# TaskSet 提供的常用方法
client # client  源码：return self.locust.client  返回 locust的client，用法与Request库类似
locust # 当任务集被实例化时，将引用根蝗虫类实例
parent # 任务集被实例化时，指向每个TaskSet所属的父类TaskSet （用于 TaskSet嵌套）
client # 指向TaskSet所属的父HttpLocust类的client属性，self.client与self.locust.client效果是一样的。如果TaskSet所属的父类是个Locust类，则没有这个client属性

```

#### HttpLocust()

继承了Locust类，表示将要生成的每一个虚拟的HTTP用户，用来发送请求到进行负载测试的系统

```AssertionError:
HttpLocust 继承 Locust   -> class HttpLocust(Locust):

task_set # 定义locust执行任务行为的 任务集类   如：task_set = TestDemo
host  # 要测试的 目标服务地址
min_wait = 1000  # 单位为ms  最小等待时间  最新版本 已弃用 （当前版本:0.14.5）
max_wait = 1000  # 单位为ms  最大等待时间  最新版本 已弃用 （当前版本:0.14.5）

#between(min_wait, max_wait)

wait_time = between(100, 1000)  # 单位为ms   等待时间  任务执行间隔时间 随机从100~1000区间内取
```

#### task 装饰器 可控制任务执行权重比

，defautl：weight=1 如下

```AssertionError:
class ForumPage(TaskSet):
    @task(100)
    def read_thread(self):
        pass
  
    @task(7)
    def create_thread(self):
        pass

```

##### eg

```python
import json
import os

from locust import HttpLocust, TaskSet, task, between


class Demo(TaskSet):
    @task
    def test_get(self):
        self.client.get("http://www.baidu.com")

    @task
    def test_post(self):
        responses = self.client.post(url='url', headers='headers', data='body')
        # 对返回内容 进行断言
        if responses.status_code == 200:
            rst = json.loads(responses.text, strict=False)
            if rst['code'] == '00000':
                responses.success()  # Locust ResponseContextManager类提供的  Report the response as successful
            else:
                responses.failure('code：%s ErrorMsg：%s' % (rst['code'], rst['errorMsg']))
        else:
            responses.failure('status_code：%s' % responses.status_code)


class WebsiteUser(HttpLocust):
    task_set = Demo
    host = 'http://www.baidu.com'  # 目标服务地址
    # min_wait = 1000  # 单位为ms  最小等待时间  最新版本 已弃用 （当前版本:0.14.5）
    # max_wait = 1000  # 单位为ms  最大等待时间  最新版本 已弃用 （当前版本:0.14.5）

    # between(min_wait, max_wait)
    wait_time = between(2, 5)  # 单位为s   等待时间  任务执行间隔时间


# 以下 便于当前脚本 本地调试
# 启动 当前脚本
if __name__ == "__main__":
    cmd = 'locust -f locust_demo.py'
    os.system(cmd)


```

#### 核心

如果Locust类代表蝗虫群，则可以说TaskSet类代表蝗虫的大脑。每个Locust类必须设置一个task_set属性，该属性指向TaskSet。

顾名思义，TaskSet是任务的集合。这些任务是普通的python可调用对象。

 TaskSet()

> 定义了每个用户的任务集合，测试任务开始后，每个Locust用户会从TaskSet中随机挑选（如果定义了任务间的权重关系，那么就是按照权重关系随机挑选）一个任务执行，然后随机等待Locust类中定义的min_wait和max_wait（如果TaskSet类中也定义了min_wait或者max_wait，按照TaskSet中的为准）之间的一段时间，执行下一个任务。

* HttpLocust()

> 继承了Locust类，表示将要生成的每一个虚拟的HTTP用户，用来发送请求到进行负载测试的系统


* taks

  >  装饰器 可控制任务执行权重比，defautl：weight=1 如下：
  >

# IPT流程

## 操作

输入接口，参数，账号，服务器ip们，内核数，返回结果，执行权重；输入模拟用户数模拟用户并发

## IPT准备：

我们以校园版为例：

1. 观察机：146上为主环境代码
2. 执行机：145，147，148，158
3. 准备：测试账号数据：需要找开发邓锦明提供是否有现成代码，生成批量账号。
4. 现需：教师账号：学生账号  1：50
5. 数量:教师账号：70个 学生3500-个，一个教师对应50个学生
6. 图形界面进行`逐步负载模式`
7. 前端主机配置4g8c

找相应的开发去获取接口文档，接口参数。和并发量（需要与产品和开发确定）

## IPT部署环境

### 1.登录远程服务器  配置python3环境

### 2. 刚申请时需要直接pip3 install locust，不成功可能是因为**没有安装python 的dev包**，yum install python3-devel后重新输入pip3 install locust

### 3. 安装ansible，在观察机上用于部署代码

1. 安装ansible
    yum -y install epel-release
    yum -y install ansible
2. 配置ansible权限

    vi /etc/ansible/ansible.cfg
    在文件中进行搜索定位到
     :/host_key_checking
    修改后：

       #uncomment this to disable SSH key host checking
    	        host_key_checking = False

### 4.安装locust

#### 安装依赖

1、支持的python版本：2.7、3.4、3.5、3.6；

2、 安装locust

①、直接通过 **pip install locustio** 命令安装；

②、通过为pyzmq、gevent和greenlet安装预先构建的二进制包，然后在[这里](https://www.lfd.uci.edu/~gohlke/pythonlibs/)找到非官方的预制包，下载.whl文件后，使用 **pip install name-of**-file**.whl** 命令安装；

安装成功后可以输入 **pip show locust** 命令查看是否安装成功，以及通过 **locust -help** 命令查看帮助信息。

pip3 install locust -i http://pypi.douban.com/simple --trusted-host pypi.douban.com

Flask-BasicAuth

psutil

msgpack

roundrobin

gevent

geventhttpclient-wheels

### 5. pip3 install prometheus_client用于采集数据

### 6. 将IPT项目进行拷贝

### 7.安装prometheus用于收集locust监听的请求接口信息

1. 将#prometheus-2.36.2.linux-amd64.tar.gz#文件进行解压，直接运行即可。

    版本有要求：可视化观察grafana-7.3.6在172.17.20.146上，注意必须是要该版本或者以上否则主题面板数据可能不会显示，主题12081

    需要在prometheus.yml文件中配置一下监听locust

    ```source
    global:
      scrape_interval:     10s
      evaluation_interval: 10s

    scrape_configs:
      - job_name: prometheus
        static_configs:
          - targets: ['localhost:9090']
            labels:
              instance: prometheus

      - job_name: locust

        metrics_path: '/export/prometheus'
        static_configs:
          - targets: ['localhost:8089']  # 地址修改为实际地址
            labels:
              instance: locust

    ```

    进入后运行./prometheus

### 8. 将test_locust.py替换

```source
# coding: utf8
 
import six
from itertools import chain
 
from flask import request, Response
from locust import stats as locust_stats, runners as locust_runners
from locust import User, task, events
from prometheus_client import Metric, REGISTRY, exposition
 
# This locustfile adds an external web endpoint to the locust master, and makes it serve as a prometheus exporter.
# Runs it as a normal locustfile, then points prometheus to it.
# locust -f prometheus_exporter.py --master
 
# Lots of code taken from [mbolek's locust_exporter](https://github.com/mbolek/locust_exporter), thx mbolek!
 
 
class LocustCollector(object):
    registry = REGISTRY
 
    def __init__(self, environment, runner):
        self.environment = environment
        self.runner = runner
 
    def collect(self):
        # collect metrics only when locust runner is spawning or running.
        runner = self.runner
 
        if runner and runner.state in (locust_runners.STATE_SPAWNING, locust_runners.STATE_RUNNING):
            stats = []
            for s in chain(locust_stats.sort_stats(runner.stats.entries), [runner.stats.total]):
                stats.append({
                    "method": s.method,
                    "name": s.name,
                    "num_requests": s.num_requests,
                    "num_failures": s.num_failures,
                    "avg_response_time": s.avg_response_time,
                    "min_response_time": s.min_response_time or 0,
                    "max_response_time": s.max_response_time,
                    "current_rps": s.current_rps,
                    "median_response_time": s.median_response_time,
                    "ninetieth_response_time": s.get_response_time_percentile(0.9),
                    # only total stats can use current_response_time, so sad.
                    #"current_response_time_percentile_95": s.get_current_response_time_percentile(0.95),
                    "avg_content_length": s.avg_content_length,
                    "current_fail_per_sec": s.current_fail_per_sec
                })
 
            # perhaps StatsError.parse_error in e.to_dict only works in python slave, take notices!
            errors = [e.to_dict() for e in six.itervalues(runner.stats.errors)]
 
            metric = Metric('locust_user_count', 'Swarmed users', 'gauge')
            metric.add_sample('locust_user_count', value=runner.user_count, labels={})
            yield metric
      
            metric = Metric('locust_errors', 'Locust requests errors', 'gauge')
            for err in errors:
                metric.add_sample('locust_errors', value=err['occurrences'],
                                  labels={'path': err['name'], 'method': err['method'],
                                          'error': err['error']})
            yield metric
 
            is_distributed = isinstance(runner, locust_runners.MasterRunner)
            if is_distributed:
                metric = Metric('locust_slave_count', 'Locust number of slaves', 'gauge')
                metric.add_sample('locust_slave_count', value=len(runner.clients.values()), labels={})
                yield metric
 
            metric = Metric('locust_fail_ratio', 'Locust failure ratio', 'gauge')
            metric.add_sample('locust_fail_ratio', value=runner.stats.total.fail_ratio, labels={})
            yield metric
 
            metric = Metric('locust_state', 'State of the locust swarm', 'gauge')
            metric.add_sample('locust_state', value=1, labels={'state': runner.state})
            yield metric
 
            stats_metrics = ['avg_content_length', 'avg_response_time', 'current_rps', 'current_fail_per_sec',
                             'max_response_time', 'ninetieth_response_time', 'median_response_time', 'min_response_time',
                             'num_failures', 'num_requests']
 
            for mtr in stats_metrics:
                mtype = 'gauge'
                if mtr in ['num_requests', 'num_failures']:
                    mtype = 'counter'
                metric = Metric('locust_stats_' + mtr, 'Locust stats ' + mtr, mtype)
                for stat in stats:
                    # Aggregated stat's method label is None, so name it as Aggregated
                    # locust has changed name Total to Aggregated since 0.12.1
                    if 'Aggregated' != stat['name']:
                        metric.add_sample('locust_stats_' + mtr, value=stat[mtr],
                                          labels={'path': stat['name'], 'method': stat['method']})
                    else:
                        metric.add_sample('locust_stats_' + mtr, value=stat[mtr],
                                          labels={'path': stat['name'], 'method': 'Aggregated'})
                yield metric
 
 
@events.init.add_listener
def locust_init(environment, runner, **kwargs):
    print("locust init event received")
    if environment.web_ui and runner:
        @environment.web_ui.app.route("/export/prometheus")
        def prometheus_exporter():
            registry = REGISTRY
            encoder, content_type = exposition.choose_encoder(request.headers.get('Accept'))
            if 'name[]' in request.args:
                registry = REGISTRY.restricted_registry(request.args.get('name[]'))
            body = encoder(registry)
            return Response(body, content_type=content_type)
        REGISTRY.register(LocustCollector(environment, runner))
 
 
class Dummy(User):
    @task(20)
    def hello(self):
        pass
```

使用方式两种，

a、直接修改改文件，将自己的压测类替换Dummy类，当启动压测，自动会启动ip:/export/prometheus的服务，该服务的数据就是我们需要收集的数据

b、以master启动该脚本，压测脚本以worker形式启动，指向master为启动该脚本的地址

b优势在于，监听服务可以永远启动，第一种方式只有压测时才启动
 

### 9. 运行测试代码，保证与监控互通

1. 运行locust -f test_locust.py --worker --master-host=159.75.109.171 执行

    locust --master -f prometheus_exporter.py观察
2. 在159.75.109.171：8089中访问进行并发请求

    ![](https://pic.imgdb.cn/item/6322d56516f2c2beb1e5b46e.jpg)
3. 在访问[159.75.109.171:8089/export/prometheus](http://159.75.109.171:8089/export/prometheus)中保证监听locust程序正常执行

  ![](https://pic.imgdb.cn/item/6322d57316f2c2beb1e5c9d9.jpg)
4. 访问[Prometheus Time Series Collection and Processing Server](http://159.75.109.171:9090/graph?g0.expr=locust_errors&g0.tab=0&g0.stacked=0&g0.show_exemplars=0&g0.range_input=2h&g1.expr=locust_slave_count&g1.tab=0&g1.stacked=0&g1.show_exemplars=0&g1.range_input=1h)

    http://159.75.109.171:9090/graph 

    http://159.75.109.171:9090/targets

    保证promethus接收到locust请求的数据

     
![](https://pic.imgdb.cn/item/6322d5ad16f2c2beb1e63eed.jpg)
5. 访问[Locust for Prometheus 全链路压测 - Grafana](http://172.17.20.147:3000/d/VvJxUgCWa/locust-for-prometheus-quan-lian-lu-ya-ce?orgId=1&refresh=1h&from=now-3h&to=now)
6. http://172.17.20.147:3000/ 

    用账号admin admin访问grafana数据图表可视化

    设置数据源将

![](https://pic.imgdb.cn/item/6322d5d616f2c2beb1e69054.jpg)

![](https://pic.imgdb.cn/item/6322d5eb16f2c2beb1e6b840.jpg)

![](https://pic.imgdb.cn/item/6322d5f816f2c2beb1e6d4d5.jpg)

至此我们的环境部署完毕，可以开始准备测试了

## 

# 测试流程

压测流程

完整的压测流程一般包含下面几个步骤

1. 压测目标的制定
2. 压测链路的梳理
3. 压测环境的准备
4. 压测数据的构造
5. 发压测试
6. 瓶颈定位及容量微调
7. 压测总结

![常规压测流程](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/5/3/171db0b32ecc8ba0~tplv-t2oaga2asx-zoom-in-crop-mark:3024:0:0:0.awebp)

## 压测目标

性能测试中， ***平均值的作用是十分有限的*** ， **我们不应看最好的结果，相反地，应该控制最坏的结果** ，

总结一下，较为科学的评估方法应该将`指标-成功率-流量`三者挂钩在一起的：

> xx%的响应在xx毫秒内返回，其中成功率为xx%。

根据这个方针，可以得到一些测试思路：

1. 在响应时间的限制下，系统最高的吞吐量（这里不对吞吐量做严格定义，当成是QPS或TPS即可）
2. 在成功率100%的前提下，不考虑响应时间长短，系统能承受的吞吐量
3. 容忍一定的失败率和慢响应，系统最高能承受的吞吐量（95%成功率，前95%的请求响应时间为xx毫秒时的最大QPS）
4. 在上面的场景下还要考虑时间和资源，比如最高吞吐量持续10分钟和持续1小时是不一样的，不同的时间持续长度下，机器资源（cpu、内存、负载、句柄、线程数、IO、带宽）的占用是否合理

## 压测准备

### 压测场景

压测是有目的的压测，也就是说不是随便找些接口发一通压力，而压测全部的接口也是做不到的或者说无意义的，得有压测的优先级，所以**梳理压测场景是很重要**的。高优场景主要有下面几个：

1. 高频业务场景
2. 关键业务场景，使用频率低，一旦出问题就很严重（学生登录）
3. 性能高消耗场景（上传答案）
4. 曾经出现过问题的场景

压测有分单接口压测和场景化压测，前者会简单一些，后者一般是多个接口混合操作以组成一个业务场景，两者在方法上是相通的。

梳理场景时QA需要与RD对齐，确认不同接口的RD负责人、**需要压测的接口、系统性能现状以及压测目标**；在确定每个接口的压测目标时，要考虑到**压测对象是单实例单机房还是集群**；在细节上也要确认是单接口压测还是场景化压测，**每个接口的流量占比以及优先级**，需不需要发足够的压力来触发系统的自动扩容或降级等更进一步的运维能力。

### 压测环境

**脏数据问题**

* 如果是在独立的一套环境中操作，不存在该问题【eg：校园版压测会单独部署一套被压系统】
* 影子表：如果是在线上操作，一般将数据写入影子表（与原数据表在schema上一致的不同名表）而非原数据表，实现压测数据与线上数据隔离【eg：翼课网压测采用影子库】
* 白名单：指定测试id或者测试账号，在入库后通过统一id区分压测数据，统一处理

可以**独立部署一套线下环境进行压测**。在不影响线上环境的前提下，确保机房，网络，存储，上下游服务与线上保持一致，部署一套独立的环境进行测试，机器与线上隔离，机器出问题不会影响线上。这种方式压测只是针对较少的几个系统进行，因为很**难把整个链路所有系统都独立再部署一套**，所以应用范围有限。

### 压测监控体系

确认好压测流程的技术支持，确认**压测链路的监控体系**是否完整，一来方便在压测过程中及时发现问题，二来是为了积攒历史压测数据，三来顺便确认监控系统本身是否可靠且全部到位。一般监控项包括（也就是压测指标）：

* 核心接口和核心依赖的流量、响应耗时、成功率【eg：IPT接入监控系统或日志查看】
* 消息队列、缓存、数据库【eg：由服务端观察队列和数据库的情况】
* 机器物理资源【eg：压测机器qa可查看机器负载情况】

## 压测总结

给出一个完整的压测过程例子：

1. 确定本次的压测目标，预估各项指标的达标值
2. 根据服务接口的优先级和使用场景，确认出需要压测的接口
3. 梳理压测链路上的服务，确认链路完整性
4. 针对压测链路设计的服务进行压测改造
5. 准备压测数据，确认压测策略
6. 开始压测，监控各项指标，多轮压测检验性能优化效果
7. 压测环境清理
8. 压测总结报告输出

压测最终应该输出一份报告总结，其实也就是把整个压测方案、过程、结论记录下来，写明压测目标、压测接口、压测数据、压测结论，给出发现的问题并提供优化方案。往往在压测报告完成时，性能问题已经基本被解决了，报告的意义在于梳理前面的整个流程，给后续的压测提供经验指导。

## 压测准备

### 确定压测范围

### 压测指标

### 压测前数据环境准备

### 压测中

### 日志结果分析

### 总结得出结论
1. 调参，通过抓包分析各接口参数和接口之间参数对应关系
2. 接口请求方式，接口请求方式一般分为

    #### application/x-www-form-urlencoded

    数据发送过程中会对数据进行[序列化](https://so.csdn.net/so/search?q=%E5%BA%8F%E5%88%97%E5%8C%96&spm=1001.2101.3001.7020)处理，以键值对形式?key1=value1&key2=value2的方式发送到服务器。 数据被编码成以 `'&'` 分隔的键-值对, 同时以 `'='` 分隔键和值。非字母或数字的字符会被 [percent-encoding](https://developer.mozilla.org/zh-CN/docs/Glossary/percent-encoding)。传参时`urllib.parse.urlencode`需要对dict编码

    * 优势: 所有浏览器都兼容。
    * 问题：在数据结构及其复杂时，服务端数据解析变得很难

    #### application/json

    请求头中加入 content-type: application/jsonapplication/json ， 方便的提交复杂的结构化数据， ，告诉服务器请求的主体内容是 json 格式的字符串，服务器端会对json字符串进行解析，**json 格式要支持比键值对复杂得多的结构化数据。**这种方式的好处不需要关心数据结构的复杂度，只需要标准的json格式就能提交成功，传参时**json.dumps**需要转成json格式

    * 优势：是前端不需要关心数据结构的复杂度，后端解析方便。
    * 问题：少数浏览器不兼容
3. 衡量指标，有时候开发会直接给出，但有时候我们需要自己去判定测试是否达标。

    常见的方法

    #### 二八原则

     *日PV=QPS*x60x*60*x24 *//*即QPS乘以一天的秒数

     **峰值QPS=(日PV*80%)/(60*x60x*24*x20%）** *//通用公式每天80%的访问集中在20%的时间里，这20%时间叫做峰值时间* 一天内80%的请求会在20%的时间内到达

    每台服务器每秒处理请求的数量=((80%*总PV量)/(24小时*60分*60秒*40%)) / 服务器数量
4. 通常测试过程中出现一些异常：

    1. 网络波动问题，可以让运维同事协助解决(比如切换网段或选择内网压测)，或者等到网络较为稳定时候进行压测验证；

    2. 资源竞争问题：通过命令监控和服务梳理，找出压测时正在运行的其他服务，通过沟通协调停止该服务(或者换个没资源竞争的服务节点重新压测也可以)；
    3. 高并发下大量报错

                    原因解析：出现该类问题，常见的原因有短连接导致的端口被完全占用以及线程池最大线程数配置较小及超时时间较短导致。

                  调优方案：

                 短连接问题：修改服务节点的tcp_tw_reuse参数为1，释放TIME_WAIT scoket用于新连接；

                 线程池问题：修改服务节点中容器的server.xml文件中的配置参数，主要修改如下几个参数：

                  最大线程数，即服务端可以同时响应处理的最大请求数

    4. 集群类系统，各服务节点负载不均衡

    原因解析：出现这类问题的原因一般是SLB服务设置了会话保持，会导致请求只分发到其中一个节点。

    调优方案：如果确认是如上原因，可通过修改SLB服务(F5/HA/Nginx)的会话保持参数为None，然后再次压测验证；

    1. 并发数不断增加，TPS上不去，CPU使用率较低

    原因解析：出现该类问题，常见的原因有：SQL没有创建索引/SQL语句筛选条件不明确、代码中设有同步锁，高并发时出现锁等待；
5. 数据清理

    如果使用了影子表，可能收尾工作会简单一些，只需要下掉影子表即可。如果数据直接落到了线上数据库，可能一大堆压测数据要清理，压测时会对数据染色（比如指定测试账号或流量携带压测标记），逐层透传，最后根据标志识别删除。
6. 举例一些可能会发现的典型问题：

    1. 存在多余的http header，导致额外带宽占用；解决方式：去除多余参数，只带必填参数
    2. spin_lock对RT影响大，优化锁的方式（资源冲突）；解决方式：增加压测服务器性能或个数
    3. 调整nginx worker数量可提高性能
    4. 不恰当的长链接数，解决方式：调整代码进程连接时间和周期
    5. 代码实现上对象没有较好复用 解决方式：优化代码
    6. 业务流程上存在冗余
    7. 响应码or错误码可能要继续规范
    8. 内部系统对压测的限流，需要变更配置或者协商解除限制 解决方式：添加高并发host


### 参考资料

[独家揭秘 | 阿里怎么做双11全链路压测？-阿里云开发者社区 (aliyun.com)](https://developer.aliyun.com/article/721643)

[RFC 2616 - Hypertext Transfer Protocol -- HTTP/1.1 (ietf.org)](https://datatracker.ietf.org/doc/html/rfc2616#section-1.3)