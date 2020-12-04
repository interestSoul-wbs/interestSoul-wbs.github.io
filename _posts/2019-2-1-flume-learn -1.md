---
layout: post
title: Flume数据库学习
categories: BigData
tags: Flume
author: wbs
---

* content
{:toc}

### Flume是一个高可用的、高可靠的、分布式的海量日志采集、聚合和传输的系统，基于流式架构。
* Flume最主要的作用就是读取服务器本地文件中的数据然后上传到HDFS
### Flume的基础架构
* Agent,是一个JVM进程
* Source 用来读数据,负责接收数据到Channel,可以接受不同类型的数据源中的数据，分为驱动型的source和轮询型的source，数据源可以有avro、thrift
（前两种表示数据传输的协议）、exec、等等
* Channel 中间件,主要起到一个缓冲区的作用，channel允许source和sink运行在不同的速率上，channel是线程安全的，因此channel可以同时处理多个source的写入和多个sink的读出
channel主要有memory channel、file channel和kafka channel,memorychannel的速度快，但是缓存的容量较小，file  channel 相反。
* Sink 用来写数据，轮询Channel将其中的事件批量的写入到一个文件系统或者索引系统，或者下一个flume agent中，sink的目的地有hdfs、avro、hbase、thrift
logger等
* Event是数据传输的基本单元，主要有header和body组成，header来存放event属性信息时k-v结构，body存放的是字节数组。




