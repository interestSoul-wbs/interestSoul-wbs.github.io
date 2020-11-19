---
layout: post
title: Spark学习
categories: BigData
tags: Spark
author: wbs
---

* content
{:toc}

## Spark
<br>Spark只是一个计算框架，不像hadoop一样包括分布式文件系统和调度系统，如果要使用spark，需要其他的文件系统和调度系统。</br>
#### MapReduce有一些缺点
1. 计算过程比较缓慢，不适应迭代计算，不适应交互计算。
2. 不是所有的计算都有map阶段或者reduce阶段组成。
#### Spark可以解决以上的问题
1. 使用内存存储中间结果，速度快。
2. 提供更好更灵活的API。
3. 支持多种语言，提供完整的技术栈，包括SQL执行，机器学习MLilib,图计算，流计算等。
4. 兼容多种工具。可以运行在Hdoop YARN,Apache Mesos,Spark Standalone等
5. 访问多种工具。 Hbase,Hive,HDFS等






### Spark的重要的组件
1. Spark Core
    + 是spark的基础，提供了基本的任务调度和I/O功能
    + 弹性分布式数据集（RDD），是一个可以并行操作，有容错的数据集合。
2. Spark Sql
    + 在spark-core的基础上定义了Dataset和DataFrame的数据抽象化的概念。
    + 提供了在Dataset和DataFrame上执行SQL的能力。
    + 可以使用Scala、Python能语言对Dataset、DataFrame进行操作。
3. Spark Streaming
### Spark集群
![](../images/spark-learn/spark集群.png)
1. Driver 该进程负责调用spark程序的main方法，并且启动SparkContext
2. Cluster Manager 该进程负责和外部的集群管理工具打交道，申请或者释放集群资源
3. Worker 是一个守护进程，负责启动和管理Executor
4. Executor 该进程是一个JVM虚拟机，负责运行SparkTask

### 运行一个Spark任务的几个步骤
1. 启动Driver，创建SparkContext
2. Client提交程序给Driver，Driver向ClusterManager申请集群资源
3. 资源申请之后，Worker启动Executor
4. Driver将程序转化为Task,分发给Executor执行。



