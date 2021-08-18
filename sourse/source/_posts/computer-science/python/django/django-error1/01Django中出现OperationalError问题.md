---
title: 01Django中出现OperationalError问题
tags: Django
abbrlink: 39093
date: 2020-09-28 08:47:08
categories:
- [计算机科学, Python, Django框架,前端Django中常见的错误集合]
---
 
# 项目场景：

  Django中连接数据库时出现错误，采用了一个大牛的博客解决的，这里附上链接https://blog.csdn.net/Wathet_blue/article/details/105401717?utm_medium=distribute.pc_relevant.none-task-blog-title-2&spm=1001.2101.3001.4242
 
 

# 问题描述：
  出现错误!OperationalError: (1366, “Incorrect string value: ‘\xE4\xB9\x8B\xE7\xBE\x8E’ for column ‘name’ at row 1”) 
 

# 原因分析：
 数据库的编码规则没有使用utf8，而在存储数据时添加了中文数据，导致报错。

 

# 解决方案：

 
 删除数据库(有数据先备份)
 

```sql
	drop database [database_name];
```
  指定编码重建数据库 或者 修改数据库编码后重建数据库
```sql
create database [database_name] default character set utf8 collate utf8_general_ci;
```
```python
show variables like 'character%';	// 查看mysql的编码
	set character_set_client=utf8;		// 设置客户端的编码为utf8
	set character_set_connection=utf8;
	set character_set_database=utf8;
	set character_set_results=utf8; 
	set character_set_server=utf8;
	set character_set_system=utf8;
	create database [database_name];	// 新创建数据库使用的编码规则是utf8

```
 重新迁移数据库
```powershell
python manage.py makemigrations
	python manage.py migrate
```

	 


