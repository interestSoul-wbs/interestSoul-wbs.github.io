---
layout: post
title: Hive-数据仓库学习
categories: BigData
tags: Hive
author: wbs
---

* content
{:toc}

### Hive与传统的RDBMS（关系型数据库管理系统）的区别
![](../images/hive-learn/hive与RDBMS的区别.png)
<br>hive虽然和传统数据库使用差不多的查询语言，但是区别还是很大的。
### Hive的安装部署
1. 内置Derby版本缺点：不同的路径启动Hive,每一个hive都拥有自己的元数据，不能共用。
2. mysql版本需要进行配置。
### Hive DDL
1. 创建表
```sql
    CREATE TABLE[IF NOT EXISTS] TABLENAME




    ROW FORMAT DELIMITED FIELDS TERMINATED BY ','
    
```
    * 创建表的时候需要指定分隔符,ROW FORMAT DELIMITED表示使用内置的分隔符，
      map terminated by ''
      array terminated by ''
    * PARTITIONED BY
      在hive中select查询一般会扫描整个表，有时候只需要扫描表中的一部分数据，因此建表的的时候引入partition分区的概念。
      在建立分区表的时候，加载数据有专用的命令，
      LOAD DATA LOCAL INPATH  ''  INTO TABLE    PARTITION(dt='')
      LOCAL 关键字表示文件来自linux否则来自HDFS，分区的字段是虚拟的字段，不存放数据，在定义时不能使用已经存在的字段。
数据类型既包括mysql中的数据类型，也包括java中的数据类型。




