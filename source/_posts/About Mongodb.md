---
title: About　MongoDB
tags: mongodb
category: 甫夸之谈———mongoDB
---
> 关于mongoDB

　MongoDB是一种基于分布式文件存储的数据库，高性能、易部署、易使用。

> 配置mongoDB数据库的步骤

+  安装mongoDB
+  启动数据库
	　1.创建一个文件夹，作为数据库存放目录
	　2.打开cmd，cd到mongoDB/bin中
	　3.执行mongod.exe --path "数据库目录"
+ 连接数据库
	使用mongo.exe可以自动连接mongo数据库
	
<!---more--->
>mongo.exe命令大全

+ use dbname
	切换到某个数据库，如果不存在，则会创建并切换
---
+ show dbs
	查询所有的数据库
---
+ 数据集合.insert() 或 数据集合.save()
	数据集合类似于关系型数据库中的表。向数据库的某个数据集合中插入一条数据，如果集合不存在，则会自动创建并执行操作
---
+ 数据集合.find()
	查询某个数据集合中的所有数据
+ 数据集合.find({查询条件})，按照某个条件查询
	+ 等于 　　　{key:value}
	+ 小于 　　　{key:{$lt:value}}
	+ 小于等于 　{key:{$lte:value}}
	+ 不等于 　　{key:{$ne:value}}
+ 数据集合.find({条件1，条件2，条件3...})
	查找所有满足（条件1，条件2，条件3）的数据
+ 数据集合.find({$or:{条件1，条件2}})
	查找所有满足条件1或条件2的数据
---
+ db.createCollection('表名')
	在数据库中创建一张表（数据集合）
---
+ show collections
	查看当前数据库中的所有的表
---
+ .sort({排序的键：1或-1})
	把查询结果按照某个字段进行排序。1为升序，-1为降序
---
+ .limit(n)
	从查询结果中取前n条数据
+ .skip(n)
	跳过（删除）查询结果中前n条数据
+ .skip+.limit 
	实现从第几条开始，往后查多少条
---
+ .remove({查询条件})
	删除表中满足条件的数据

> 把mongoDB安装为windows服务

	1.创建日志存放路径log文件夹和数据库存放路径db文件夹
	2.cd到mongoDB安装目录下，然后cd到bin中
	3.执行　mongod.exe --dbpath "数据库存放路径" --logpath "日志存放路径" --install
	4.从windows的任务管理器中打开或关闭mongoDB服务