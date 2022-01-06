---
title: win10上安装 Emscripten 安装
abbrlink: 52323
date: 2022-01-06 10:09:18
tags:
categories:
  - [电脑,软件配置,安装教程]
---
背景

**WebAssembly 的出现为 Web 开发者打开了一扇新的大门** 。在去年，wasm 对你来说也许还仅是技术文章中的一个常见名词，你压根想不到他会在浏览器中得到怎样的应用，什么时候会被大公司真正用起来。 **在今年，你很有可能已在不知不觉中成为 wasm 的使用者了** 。目前国内外越来越多的团队基于 wasm 进行了业务实践

一、Emscripten是什么？

Emscripten编译器，是WebAssembly开发的重要工具之一，主要是通过emcc（Emscripten Compiler Frontend）来工作的。这是个命令行工

二、安装步骤

1.环境准备

git 2.32.0 python 3.7

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MmM5MGFkN2JhODAxZjc0MmZkYzQzZDM1NGI4NWQ2OTVfSVFvUE0yTXZCSk5LWEthNzVqa0FzWm5jOTBBemJtU05fVG9rZW46Ym94Y250ZFJuUElFdkRTaGdwSTRlaEZrZ21nXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWI1YmY5YTQxNTg5YmYxNjg1ZWQ3NTk1ZTlmNWM4ZTFfcHZibHJiYktqOExNZlFCOGtiMzNHcTlRRktwUEhvdjRfVG9rZW46Ym94Y25PNElidEVBTXZaRGdMNnZESnJJWDhnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

2.安装

创建文件夹

python

mkdir d:\WebAssemblyTestmkdir

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NzYyOGRkMzhhZThjNWFhNWRkYTIzZTUwODJhMTYyNjRfWmw3MGxEWEpIUExKS1NHNEx2Q0VWWkwwMUdwb1pQRHFfVG9rZW46Ym94Y25nUGllczdYZDhHREFNUFcyQ3Mwb1lkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

进入目录🧐

python

cd WebAssemblyTestmkdir\

Emscripten环境安装

python

git clone https://github.com/emscripten-core/emsdk.git

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YTJkZmMwZmI5ZmQ1NTE1OTVjYmMyNWM2MWU3Y2MzZWRfS0JzSjdJMkdUemhvMUNmTzVzcEp0aER4THU4V3QxeU5fVG9rZW46Ym94Y25FY3lxWWhTNkFZR3UwaHpLMzZhZ2hkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

python

cd emsdk

安装最新根据包

python

emsdk install latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YzUzNjIzMGI2ZDczYWQ4NWM2MDQ5ZTYwZTMxMDE5MGVfVWhDWDdvS201TXhRcnVIVnRuM0NYM21nRzJzVFg1M3VfVG9rZW46Ym94Y25UMU9yQkNucUg2M3p3YTc5T2hPaHhwXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

激活sdk

python

emsdk activate latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDQ0MTQ0YmE5Y2M2MjJkNjJlNzJkNTM0NTI5NzVhNjFfcHo3RHlyMXY4ZVRUVk9nWkpld242SzRCckY0ZGlveDJfVG9rZW46Ym94Y25zYkRPUG9FQWpHSkxhM2ZrRXd1QVVoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

执行环境变量

python

emsdk_env.bat

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTc5MzY2NTVkMjYxZjRlMWU2YTcyMjQxOTVkMjgxY2NfRUg1UmVQbkZrV1VnRzZvbUFLQTRSUEVxdDRVR2toZ0pfVG9rZW46Ym94Y25jeGZtakNsRVlST0VpRURRQTZPQVFkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

安装完成

测试一下

python

emcc -v

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MDUyYjI4MjNkN2ZjMGZjMzI5ZWQwMTE3MDQzMDc1YjJfYXFWTDZhWmJ0c1FoR2hla3RKVFdUVTJNMDAyaGJrbVpfVG9rZW46Ym94Y242SzI3NndwblZVM3JiTlNDYXRRQVJoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

开始helloworld

创建个文件夹

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWJmODcyN2E2N2RlY2I5ZjViYWQ5YjgzNjkzNTUxODRfcUdzcjJ6bjl4bE5hNHNtNVVITjc0TUZROTBkMGJocm1fVG9rZW46Ym94Y240TG5qbjNhRVFMdkpZS3lXWU9MTWljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTRmOTRhMmZhZDEwYWIzOTBjMzRjYzIwZTQzNThlMWVfczl0OE83SGpuZk9Qb2NhWGFDY1ZycHBsb3BJdzFDODlfVG9rZW46Ym94Y245OVJxUERPQUxNa0RhbnB4ZTV3SUpkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

创建hello_world.c文件内容如下🧐

python

#include <stdio.h>

int main(int argc, char ** argv) {

printf("Hello World\n");

}

运行一下

emcc 执行c文件路径 -s WASM=1 -o 目标文件名.html

python

emcc  hello_world.c -s WASM=1 -o hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjEwZWEyNTA0MTU3MzNhNmU5NTE3MDkxMDhiNmM3NmZfeVI5clJnaTlMb3M3WVlSYlUwVGRRTmNnSVpjY1ZVVmhfVG9rZW46Ym94Y25aSmFUazllNGl5TWlhU25PVEFUNGJjXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

文件c变成

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NWIxNjEwNjUyM2JhMDczOWQzMzc4YzljZGNhODhkMmRfeGhSVnRPbVBodUNESndMaHdSZnA3YW1Mb3pZczFlVEZfVG9rZW46Ym94Y25DeW5NU1VqejJNNXpzdDdWSkhCQnljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

启动http服务命令

python

emrun --no_browser --port 8080 hello_world.html

访问网址🧐

http://localhost:8080/hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDM1MWM0MDgyYjIxNWNlZTJmMmZhNDNmNmI2MzAwMDNfazFnRGlaMmF1ZjEwOXBlczYwM1VzdXZ1QlNQYTVMSkNfVG9rZW46Ym94Y25IZ2RJcjI1MERZQVI1NE9ZZ3Qzc3hnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

参考链接

(19条消息) Windows10中Emscripten 安装详解_cnds123的专栏-CSDN博客_emscripten安装

开发者引导 - WebAssembly 中文网|Wasm 中文文档

在Windows10搭建WebAssembly开发环境 - kunger - 博客园 (cnblogs.com)

2021 年大前端技术趋势解读-InfoQ

win10上安装 Emscripten 安装

背景

**WebAssembly 的出现为 Web 开发者打开了一扇新的大门** 。在去年，wasm 对你来说也许还仅是技术文章中的一个常见名词，你压根想不到他会在浏览器中得到怎样的应用，什么时候会被大公司真正用起来。 **在今年，你很有可能已在不知不觉中成为 wasm 的使用者了** 。目前国内外越来越多的团队基于 wasm 进行了业务实践

一、Emscripten是什么？

Emscripten编译器，是WebAssembly开发的重要工具之一，主要是通过emcc（Emscripten Compiler Frontend）来工作的。这是个命令行工

二、安装步骤

1.环境准备

git 2.32.0 python 3.7

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MmM5MGFkN2JhODAxZjc0MmZkYzQzZDM1NGI4NWQ2OTVfSVFvUE0yTXZCSk5LWEthNzVqa0FzWm5jOTBBemJtU05fVG9rZW46Ym94Y250ZFJuUElFdkRTaGdwSTRlaEZrZ21nXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWI1YmY5YTQxNTg5YmYxNjg1ZWQ3NTk1ZTlmNWM4ZTFfcHZibHJiYktqOExNZlFCOGtiMzNHcTlRRktwUEhvdjRfVG9rZW46Ym94Y25PNElidEVBTXZaRGdMNnZESnJJWDhnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

2.安装

创建文件夹

python

mkdir d:\WebAssemblyTestmkdir

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NzYyOGRkMzhhZThjNWFhNWRkYTIzZTUwODJhMTYyNjRfWmw3MGxEWEpIUExKS1NHNEx2Q0VWWkwwMUdwb1pQRHFfVG9rZW46Ym94Y25nUGllczdYZDhHREFNUFcyQ3Mwb1lkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

进入目录🧐

python

cd WebAssemblyTestmkdir\

Emscripten环境安装

python

git clone https://github.com/emscripten-core/emsdk.git

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YTJkZmMwZmI5ZmQ1NTE1OTVjYmMyNWM2MWU3Y2MzZWRfS0JzSjdJMkdUemhvMUNmTzVzcEp0aER4THU4V3QxeU5fVG9rZW46Ym94Y25FY3lxWWhTNkFZR3UwaHpLMzZhZ2hkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

python

cd emsdk

安装最新根据包

python

emsdk install latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YzUzNjIzMGI2ZDczYWQ4NWM2MDQ5ZTYwZTMxMDE5MGVfVWhDWDdvS201TXhRcnVIVnRuM0NYM21nRzJzVFg1M3VfVG9rZW46Ym94Y25UMU9yQkNucUg2M3p3YTc5T2hPaHhwXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

激活sdk

python

emsdk activate latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDQ0MTQ0YmE5Y2M2MjJkNjJlNzJkNTM0NTI5NzVhNjFfcHo3RHlyMXY4ZVRUVk9nWkpld242SzRCckY0ZGlveDJfVG9rZW46Ym94Y25zYkRPUG9FQWpHSkxhM2ZrRXd1QVVoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

执行环境变量

python

emsdk_env.bat

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTc5MzY2NTVkMjYxZjRlMWU2YTcyMjQxOTVkMjgxY2NfRUg1UmVQbkZrV1VnRzZvbUFLQTRSUEVxdDRVR2toZ0pfVG9rZW46Ym94Y25jeGZtakNsRVlST0VpRURRQTZPQVFkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

安装完成

测试一下

python

emcc -v

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MDUyYjI4MjNkN2ZjMGZjMzI5ZWQwMTE3MDQzMDc1YjJfYXFWTDZhWmJ0c1FoR2hla3RKVFdUVTJNMDAyaGJrbVpfVG9rZW46Ym94Y242SzI3NndwblZVM3JiTlNDYXRRQVJoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

开始helloworld

创建个文件夹

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWJmODcyN2E2N2RlY2I5ZjViYWQ5YjgzNjkzNTUxODRfcUdzcjJ6bjl4bE5hNHNtNVVITjc0TUZROTBkMGJocm1fVG9rZW46Ym94Y240TG5qbjNhRVFMdkpZS3lXWU9MTWljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTRmOTRhMmZhZDEwYWIzOTBjMzRjYzIwZTQzNThlMWVfczl0OE83SGpuZk9Qb2NhWGFDY1ZycHBsb3BJdzFDODlfVG9rZW46Ym94Y245OVJxUERPQUxNa0RhbnB4ZTV3SUpkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

创建hello_world.c文件内容如下🧐

python

#include <stdio.h>

int main(int argc, char ** argv) {

printf("Hello World\n");

}

运行一下

emcc 执行c文件路径 -s WASM=1 -o 目标文件名.html

python

emcc  hello_world.c -s WASM=1 -o hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjEwZWEyNTA0MTU3MzNhNmU5NTE3MDkxMDhiNmM3NmZfeVI5clJnaTlMb3M3WVlSYlUwVGRRTmNnSVpjY1ZVVmhfVG9rZW46Ym94Y25aSmFUazllNGl5TWlhU25PVEFUNGJjXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

文件c变成

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NWIxNjEwNjUyM2JhMDczOWQzMzc4YzljZGNhODhkMmRfeGhSVnRPbVBodUNESndMaHdSZnA3YW1Mb3pZczFlVEZfVG9rZW46Ym94Y25DeW5NU1VqejJNNXpzdDdWSkhCQnljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

启动http服务命令

python

emrun --no_browser --port 8080 hello_world.html

访问网址🧐

http://localhost:8080/hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDM1MWM0MDgyYjIxNWNlZTJmMmZhNDNmNmI2MzAwMDNfazFnRGlaMmF1ZjEwOXBlczYwM1VzdXZ1QlNQYTVMSkNfVG9rZW46Ym94Y25IZ2RJcjI1MERZQVI1NE9ZZ3Qzc3hnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

参考链接

(19条消息) Windows10中Emscripten 安装详解_cnds123的专栏-CSDN博客_emscripten安装

开发者引导 - WebAssembly 中文网|Wasm 中文文档

在Windows10搭建WebAssembly开发环境 - kunger - 博客园 (cnblogs.com)

2021 年大前端技术趋势解读-InfoQ

win10上安装 Emscripten 安装

背景

**WebAssembly 的出现为 Web 开发者打开了一扇新的大门** 。在去年，wasm 对你来说也许还仅是技术文章中的一个常见名词，你压根想不到他会在浏览器中得到怎样的应用，什么时候会被大公司真正用起来。 **在今年，你很有可能已在不知不觉中成为 wasm 的使用者了** 。目前国内外越来越多的团队基于 wasm 进行了业务实践

一、Emscripten是什么？

Emscripten编译器，是WebAssembly开发的重要工具之一，主要是通过emcc（Emscripten Compiler Frontend）来工作的。这是个命令行工

二、安装步骤

1.环境准备

git 2.32.0 python 3.7

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MmM5MGFkN2JhODAxZjc0MmZkYzQzZDM1NGI4NWQ2OTVfSVFvUE0yTXZCSk5LWEthNzVqa0FzWm5jOTBBemJtU05fVG9rZW46Ym94Y250ZFJuUElFdkRTaGdwSTRlaEZrZ21nXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWI1YmY5YTQxNTg5YmYxNjg1ZWQ3NTk1ZTlmNWM4ZTFfcHZibHJiYktqOExNZlFCOGtiMzNHcTlRRktwUEhvdjRfVG9rZW46Ym94Y25PNElidEVBTXZaRGdMNnZESnJJWDhnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

2.安装

创建文件夹

python

mkdir d:\WebAssemblyTestmkdir

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NzYyOGRkMzhhZThjNWFhNWRkYTIzZTUwODJhMTYyNjRfWmw3MGxEWEpIUExKS1NHNEx2Q0VWWkwwMUdwb1pQRHFfVG9rZW46Ym94Y25nUGllczdYZDhHREFNUFcyQ3Mwb1lkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

进入目录🧐

python

cd WebAssemblyTestmkdir\

Emscripten环境安装

python

git clone https://github.com/emscripten-core/emsdk.git

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YTJkZmMwZmI5ZmQ1NTE1OTVjYmMyNWM2MWU3Y2MzZWRfS0JzSjdJMkdUemhvMUNmTzVzcEp0aER4THU4V3QxeU5fVG9rZW46Ym94Y25FY3lxWWhTNkFZR3UwaHpLMzZhZ2hkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

python

cd emsdk

安装最新根据包

python

emsdk install latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YzUzNjIzMGI2ZDczYWQ4NWM2MDQ5ZTYwZTMxMDE5MGVfVWhDWDdvS201TXhRcnVIVnRuM0NYM21nRzJzVFg1M3VfVG9rZW46Ym94Y25UMU9yQkNucUg2M3p3YTc5T2hPaHhwXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

激活sdk

python

emsdk activate latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDQ0MTQ0YmE5Y2M2MjJkNjJlNzJkNTM0NTI5NzVhNjFfcHo3RHlyMXY4ZVRUVk9nWkpld242SzRCckY0ZGlveDJfVG9rZW46Ym94Y25zYkRPUG9FQWpHSkxhM2ZrRXd1QVVoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

执行环境变量

python

emsdk_env.bat

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTc5MzY2NTVkMjYxZjRlMWU2YTcyMjQxOTVkMjgxY2NfRUg1UmVQbkZrV1VnRzZvbUFLQTRSUEVxdDRVR2toZ0pfVG9rZW46Ym94Y25jeGZtakNsRVlST0VpRURRQTZPQVFkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

安装完成

测试一下

python

emcc -v

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MDUyYjI4MjNkN2ZjMGZjMzI5ZWQwMTE3MDQzMDc1YjJfYXFWTDZhWmJ0c1FoR2hla3RKVFdUVTJNMDAyaGJrbVpfVG9rZW46Ym94Y242SzI3NndwblZVM3JiTlNDYXRRQVJoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

开始helloworld

创建个文件夹

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWJmODcyN2E2N2RlY2I5ZjViYWQ5YjgzNjkzNTUxODRfcUdzcjJ6bjl4bE5hNHNtNVVITjc0TUZROTBkMGJocm1fVG9rZW46Ym94Y240TG5qbjNhRVFMdkpZS3lXWU9MTWljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTRmOTRhMmZhZDEwYWIzOTBjMzRjYzIwZTQzNThlMWVfczl0OE83SGpuZk9Qb2NhWGFDY1ZycHBsb3BJdzFDODlfVG9rZW46Ym94Y245OVJxUERPQUxNa0RhbnB4ZTV3SUpkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

创建hello_world.c文件内容如下🧐

python

#include <stdio.h>

int main(int argc, char ** argv) {

printf("Hello World\n");

}

运行一下

emcc 执行c文件路径 -s WASM=1 -o 目标文件名.html

python

emcc  hello_world.c -s WASM=1 -o hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjEwZWEyNTA0MTU3MzNhNmU5NTE3MDkxMDhiNmM3NmZfeVI5clJnaTlMb3M3WVlSYlUwVGRRTmNnSVpjY1ZVVmhfVG9rZW46Ym94Y25aSmFUazllNGl5TWlhU25PVEFUNGJjXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

文件c变成

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NWIxNjEwNjUyM2JhMDczOWQzMzc4YzljZGNhODhkMmRfeGhSVnRPbVBodUNESndMaHdSZnA3YW1Mb3pZczFlVEZfVG9rZW46Ym94Y25DeW5NU1VqejJNNXpzdDdWSkhCQnljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

启动http服务命令

python

emrun --no_browser --port 8080 hello_world.html

访问网址🧐

http://localhost:8080/hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDM1MWM0MDgyYjIxNWNlZTJmMmZhNDNmNmI2MzAwMDNfazFnRGlaMmF1ZjEwOXBlczYwM1VzdXZ1QlNQYTVMSkNfVG9rZW46Ym94Y25IZ2RJcjI1MERZQVI1NE9ZZ3Qzc3hnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

参考链接

(19条消息) Windows10中Emscripten 安装详解_cnds123的专栏-CSDN博客_emscripten安装

开发者引导 - WebAssembly 中文网|Wasm 中文文档

在Windows10搭建WebAssembly开发环境 - kunger - 博客园 (cnblogs.com)

2021 年大前端技术趋势解读-InfoQ

win10上安装 Emscripten 安装

背景

**WebAssembly 的出现为 Web 开发者打开了一扇新的大门** 。在去年，wasm 对你来说也许还仅是技术文章中的一个常见名词，你压根想不到他会在浏览器中得到怎样的应用，什么时候会被大公司真正用起来。 **在今年，你很有可能已在不知不觉中成为 wasm 的使用者了** 。目前国内外越来越多的团队基于 wasm 进行了业务实践

一、Emscripten是什么？

Emscripten编译器，是WebAssembly开发的重要工具之一，主要是通过emcc（Emscripten Compiler Frontend）来工作的。这是个命令行工

二、安装步骤

1.环境准备

git 2.32.0 python 3.7

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MmM5MGFkN2JhODAxZjc0MmZkYzQzZDM1NGI4NWQ2OTVfSVFvUE0yTXZCSk5LWEthNzVqa0FzWm5jOTBBemJtU05fVG9rZW46Ym94Y250ZFJuUElFdkRTaGdwSTRlaEZrZ21nXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWI1YmY5YTQxNTg5YmYxNjg1ZWQ3NTk1ZTlmNWM4ZTFfcHZibHJiYktqOExNZlFCOGtiMzNHcTlRRktwUEhvdjRfVG9rZW46Ym94Y25PNElidEVBTXZaRGdMNnZESnJJWDhnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

2.安装

创建文件夹

python

mkdir d:\WebAssemblyTestmkdir

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NzYyOGRkMzhhZThjNWFhNWRkYTIzZTUwODJhMTYyNjRfWmw3MGxEWEpIUExKS1NHNEx2Q0VWWkwwMUdwb1pQRHFfVG9rZW46Ym94Y25nUGllczdYZDhHREFNUFcyQ3Mwb1lkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

进入目录🧐

python

cd WebAssemblyTestmkdir\

Emscripten环境安装

python

git clone https://github.com/emscripten-core/emsdk.git

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YTJkZmMwZmI5ZmQ1NTE1OTVjYmMyNWM2MWU3Y2MzZWRfS0JzSjdJMkdUemhvMUNmTzVzcEp0aER4THU4V3QxeU5fVG9rZW46Ym94Y25FY3lxWWhTNkFZR3UwaHpLMzZhZ2hkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

python

cd emsdk

安装最新根据包

python

emsdk install latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YzUzNjIzMGI2ZDczYWQ4NWM2MDQ5ZTYwZTMxMDE5MGVfVWhDWDdvS201TXhRcnVIVnRuM0NYM21nRzJzVFg1M3VfVG9rZW46Ym94Y25UMU9yQkNucUg2M3p3YTc5T2hPaHhwXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

激活sdk

python

emsdk activate latest

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDQ0MTQ0YmE5Y2M2MjJkNjJlNzJkNTM0NTI5NzVhNjFfcHo3RHlyMXY4ZVRUVk9nWkpld242SzRCckY0ZGlveDJfVG9rZW46Ym94Y25zYkRPUG9FQWpHSkxhM2ZrRXd1QVVoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

执行环境变量

python

emsdk_env.bat

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTc5MzY2NTVkMjYxZjRlMWU2YTcyMjQxOTVkMjgxY2NfRUg1UmVQbkZrV1VnRzZvbUFLQTRSUEVxdDRVR2toZ0pfVG9rZW46Ym94Y25jeGZtakNsRVlST0VpRURRQTZPQVFkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

安装完成

测试一下

python

emcc -v

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=MDUyYjI4MjNkN2ZjMGZjMzI5ZWQwMTE3MDQzMDc1YjJfYXFWTDZhWmJ0c1FoR2hla3RKVFdUVTJNMDAyaGJrbVpfVG9rZW46Ym94Y242SzI3NndwblZVM3JiTlNDYXRRQVJoXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

开始helloworld

创建个文件夹

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YWJmODcyN2E2N2RlY2I5ZjViYWQ5YjgzNjkzNTUxODRfcUdzcjJ6bjl4bE5hNHNtNVVITjc0TUZROTBkMGJocm1fVG9rZW46Ym94Y240TG5qbjNhRVFMdkpZS3lXWU9MTWljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=ZTRmOTRhMmZhZDEwYWIzOTBjMzRjYzIwZTQzNThlMWVfczl0OE83SGpuZk9Qb2NhWGFDY1ZycHBsb3BJdzFDODlfVG9rZW46Ym94Y245OVJxUERPQUxNa0RhbnB4ZTV3SUpkXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

创建hello_world.c文件内容如下🧐

python

#include <stdio.h>

int main(int argc, char ** argv) {

printf("Hello World\n");

}

运行一下

emcc 执行c文件路径 -s WASM=1 -o 目标文件名.html

python

emcc  hello_world.c -s WASM=1 -o hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=YjEwZWEyNTA0MTU3MzNhNmU5NTE3MDkxMDhiNmM3NmZfeVI5clJnaTlMb3M3WVlSYlUwVGRRTmNnSVpjY1ZVVmhfVG9rZW46Ym94Y25aSmFUazllNGl5TWlhU25PVEFUNGJjXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

文件c变成

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NWIxNjEwNjUyM2JhMDczOWQzMzc4YzljZGNhODhkMmRfeGhSVnRPbVBodUNESndMaHdSZnA3YW1Mb3pZczFlVEZfVG9rZW46Ym94Y25DeW5NU1VqejJNNXpzdDdWSkhCQnljXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

启动http服务命令

python

emrun --no_browser --port 8080 hello_world.html

访问网址🧐

http://localhost:8080/hello_world.html

![](https://u3dof6c39p.feishu.cn/space/api/box/stream/download/asynccode/?code=NDM1MWM0MDgyYjIxNWNlZTJmMmZhNDNmNmI2MzAwMDNfazFnRGlaMmF1ZjEwOXBlczYwM1VzdXZ1QlNQYTVMSkNfVG9rZW46Ym94Y25IZ2RJcjI1MERZQVI1NE9ZZ3Qzc3hnXzE2NDE0MzQ5NzE6MTY0MTQzODU3MV9WNA)

参考链接

(19条消息) Windows10中Emscripten 安装详解_cnds123的专栏-CSDN博客_emscripten安装

开发者引导 - WebAssembly 中文网|Wasm 中文文档

在Windows10搭建WebAssembly开发环境 - kunger - 博客园 (cnblogs.com)

2021 年大前端技术趋势解读-InfoQ
