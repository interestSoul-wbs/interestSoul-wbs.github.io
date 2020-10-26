---
layout: post
title: Hive-数据仓库学习
categories: BigData
tags: Hive
author: wbs
---

* content
{:toc}

## 数据仓库与数据库的区别
<br>数据仓库的英文名叫做Data WareHouse,数据仓库的目的是构建面向分析的集成化数据环境，为企业提供决策支持。
数据仓库本身不生产数据也不消费数据，数据来源于外部，并且开放给外部用户。</br>
<br>数据库叫做OLTP（On-line Transaction Process),联机事务处理，也叫操作型处理，包括操作的响应时间、数据的安全性、完整性和并发支持的用户数。</br>
<br>数据仓库支持OLAP(On-Line Analyse Process)，联机分析处理，用来支持管理决策。</br>
1. 数据库是面向应用的，数据仓库是面向主题的。
2. 数据库一般存储业务数据，数据仓库存储的一般是历史数据。
3. 数据库的设计一般避免冗余







## 数据仓库的主要特征
数据仓库是面向主题的、集成的、非易失的和时变的数据的集合，以来支持管理决策。
1. 集成性。通过对分散、独立、异构的数据进行抽取、清理、转换和汇总就得到了数据仓库的数据，保证数据仓库内的数据关于整个企业的一致性。
    * 要统一数据源中的矛盾之处。比如字段的同名异义、单位不统一等等。
    * 数据仓库中的数据可以从外部数据中进行抽取，但也可以在进入数据仓库之后进行综合生成。
    * 上面的这些操作叫做ETL（extract、transform、load）
2. 非易失性，也叫作不可更新性。传统的操作型数据库需要不断的对数据进行更新，不至于影响正常的业务操作。
   在数据仓库中只要保存过去的业务数据，不需要每一笔数据都进行实时的更新。只需要进行定期的导入。
3. 时变性。数据仓库中包含各种粒度的历史数据，可能与某个特定日期、星期、月份等有关。数据仓库的建设是一个项目，更是一个过程。
   其中的数据随时间的变化一般有几个特点：
    * 数据时限远远长于操作型数据库
    * 一般是历史数据，操作型数据库存储的是当前数据
    * 数据是按照时间顺序进行追加的，都带有时间属性。
4. 面向主题，数据库是面向事务的。
## 数据仓库的分层架构
![](../images/hive-learn/数据仓库的分层架构.png)
1. 源数据层(ODS)
2. 数据仓库层(DW)
3. 数据应用层(APP)
<br>ETL的作用：ETL是数据仓库的流水线，也是数据仓库的血液，维系着数据仓库的新陈代谢，数据仓库的日常的管理
和维护的大部分经理就是维护ETL的正常和稳定</br>
### 为什么要对数据仓库进行分层？
<br>表面上来看，从元数据到数据仓库，产生了大量的数据冗余，是因为用空间换时间，用大量的预处理来换取用户的体验。</br>
<br>化整为零，将数据处理的步骤分为一步一步，提高容错能力。</br>

## 数据库元数据管理
## Hive实现思路的模拟
![](../images/hive-learn/hive实现思路模拟.png)
### 使用Hive的原因
1. 直接使用Hadoop MapReduce处理数据比较复杂，人员的学习成本高，实现复杂逻辑困难。
2. 使用sql的语法，开发迅速，扩展方便


