# java_Interview
看目录自己面试，答案在下边,会慢慢补充。

<!-- TOC -->autoauto- [java_Interview](#java_interview)auto- [并发](#并发)auto    - [基础](#基础)auto        - [1.线程进程含义&关系&区别&优缺点](#1线程进程含义关系区别优缺点)auto        - [2.并发与并行的区别](#2并发与并行的区别)auto        - [3.为何使用多线程 可能带来的问题](#3为何使用多线程-可能带来的问题)auto        - [4.线程的生命周期和状态](#4线程的生命周期和状态)auto        - [5.什么是上下文切换](#5什么是上下文切换)auto        - [6.线程死锁？如何避免？](#6线程死锁如何避免)auto        - [7.sleep()方法和wait()方法的区别/共同点](#7sleep方法和wait方法的区别共同点)auto        - [8.是否可以直接调用run()  不限start()再run()?](#8是否可以直接调用run--不限start再run)auto    - [synchronized](#synchronized)auto        - [1.谈谈自己对于synchronized关键字的了解](#1谈谈自己对于synchronized关键字的了解)auto        - [2.谈谈自己是怎么使用此关键字](#2谈谈自己是怎么使用此关键字)auto        - [3.构造方法可以使用他修饰吗](#3构造方法可以使用他修饰吗)auto        - [4.谈下底层原理](#4谈下底层原理)auto        - [5.谈下1.6后底层做了哪些优化,详细介绍一下](#5谈下16后底层做了哪些优化详细介绍一下)auto        - [6.谈谈synchronized和ReentrantLock区别](#6谈谈synchronized和reentrantlock区别)auto    - [volatile](#volatile)auto        - [1.CPU缓存模型](#1cpu缓存模型)auto        - [2.讲一下JMM](#2讲一下jmm)auto        - [3.并发编程的三个重要特性](#3并发编程的三个重要特性)auto        - [4.介绍一下对此关键字的理解](#4介绍一下对此关键字的理解)auto        - [5.synchronized 与volatile 的区别](#5synchronized-与volatile-的区别)auto    - [ThreadLocal](#threadlocal)auto        - [1.介绍一下是什么及原理](#1介绍一下是什么及原理)auto        - [2.ThreadLocal 内存泄漏的问题](#2threadlocal-内存泄漏的问题)auto    - [线程池](#线程池)auto        - [1.为什么要使用线程池](#1为什么要使用线程池)auto        - [2.实现Runnable和Callable接口的区别](#2实现runnable和callable接口的区别)auto        - [3.execute（） 与submit（） 区别](#3execute-与submit-区别)auto        - [4.如何创建线程池](#4如何创建线程池)auto        - [5.ThreadPoolExecutor类分析](#5threadpoolexecutor类分析)auto        - [6.谈下原理](#6谈下原理)auto    - [Atomic 原子类](#atomic-原子类)auto        - [1.介绍一下 ..](#1介绍一下-)auto        - [2.JUC包中的原子类是哪四类](#2juc包中的原子类是哪四类)auto        - [3.讲讲AtomicInteger的使用](#3讲讲atomicinteger的使用)auto        - [4.简单介绍一下AtomicInteger类的原理](#4简单介绍一下atomicinteger类的原理)auto    - [AQS](#aqs)auto        - [1.介绍一下AQS](#1介绍一下aqs)auto        - [2.AQS原理分析](#2aqs原理分析)auto        - [3.组件](#3组件)auto        - [4.用过CountDownLatch吗 什么场景用的](#4用过countdownlatch吗-什么场景用的)auto    - [Reference](#reference)auto- [Mysql](#mysql)auto    - [架构相关](#架构相关)auto        - [1.结合MySQL架构，聊一下SQL的执行过程](#1结合mysql架构聊一下sql的执行过程)auto        - [2.缓存和缓冲](#2缓存和缓冲)auto        - [3.谈谈Mysql的储引擎](#3谈谈mysql的储引擎)auto        - [4.怎么理解Mysql对于sql的执行时基于成本模型的](#4怎么理解mysql对于sql的执行时基于成本模型的)auto        - [5.优化器是怎么运行的,为什么会有错误的决定](#5优化器是怎么运行的为什么会有错误的决定)auto    - [Schema](#schema)auto        - [1.谈谈数据的范式,为什么需要范式](#1谈谈数据的范式为什么需要范式)auto        - [2.字段有哪些类型](#2字段有哪些类型)auto        - [3.为什么设定主键，选用什么类型](#3为什么设定主键选用什么类型)auto        - [4.水平分表和垂直分表  解释一下？](#4水平分表和垂直分表--解释一下)auto    - [索引](#索引)auto        - [1.有哪些类型,逻辑分类和物理分类有哪些](#1有哪些类型逻辑分类和物理分类有哪些)auto        - [2.为什么使用索引](#2为什么使用索引)auto        - [3.索引采用了哪些数据结构,分别有什么特征](#3索引采用了哪些数据结构分别有什么特征)auto        - [4.like查询可以走索引](#4like查询可以走索引)auto        - [5.不建议对哪些字段建索引](#5不建议对哪些字段建索引)auto        - [6.Mysql是如何建立索引的](#6mysql是如何建立索引的)auto        - [7.哪些场景会导致索引失效](#7哪些场景会导致索引失效)auto        - [8.如何创建/使用高性能的索引](#8如何创建使用高性能的索引)auto        - [9.索引对null值是如何处理的](#9索引对null值是如何处理的)auto    - [事务](#事务)auto        - [1.隔离级别有哪些,分别会存在什么问题](#1隔离级别有哪些分别会存在什么问题)auto        - [2.事务的特征及实现](#2事务的特征及实现)auto        - [3.分布式事务解决方案](#3分布式事务解决方案)auto    - [日志](#日志)auto        - [1.redo log 和bin log 有什么区别](#1redo-log-和bin-log-有什么区别)auto        - [2.事务提交时，redo log和binlog的写入顺序是怎样的](#2事务提交时redo-log和binlog的写入顺序是怎样的)auto        - [3. redo log什么时候释放？undo log什么时候释放？](#3-redo-log什么时候释放undo-log什么时候释放)auto        - [4. 什么是write-Ahead Log策略？](#4-什么是write-ahead-log策略)auto        - [5. bin log记录日志有哪些方式？常用哪种？为什么？各有什么优劣势？](#5-bin-log记录日志有哪些方式常用哪种为什么各有什么优劣势)auto    - [锁](#锁)auto        - [1. 数据库中有哪些锁，有什么作用，有什么弊端？](#1-数据库中有哪些锁有什么作用有什么弊端)auto        - [2. latch 和 lock 有什么区别](#2-latch-和-lock-有什么区别)auto        - [3. RC 和 RR 在加锁方面有什么不同？](#3-rc-和-rr-在加锁方面有什么不同)auto        - [4. 什么是死锁，怎么避免死锁？有没有遇到死锁？](#4-什么是死锁怎么避免死锁有没有遇到死锁)auto        - [5. 如何查看死锁信息？](#5-如何查看死锁信息)auto        - [6. 发生死锁怎么办？怎么处理？](#6-发生死锁怎么办怎么处理)auto        - [7. MYISAM 和 InnoDB 是怎么支持并发插入的？](#7-myisam-和-innodb-是怎么支持并发插入的)auto        - [8. 怎么理解latch中的自旋锁？比较下Java中的自旋锁](#8-怎么理解latch中的自旋锁比较下java中的自旋锁)auto    - [Innodb](#innodb)auto        - [1. 什么是缓冲池？有什么用？](#1-什么是缓冲池有什么用)auto        - [2. 聊一聊LRU算法，InnoDB是怎么实现LRU的？](#2-聊一聊lru算法innodb是怎么实现lru的)auto        - [3. 聊一聊InnoDB架构，各组成部分有什么用？](#3-聊一聊innodb架构各组成部分有什么用)auto        - [4. 脏页刷盘机制是什么？](#4-脏页刷盘机制是什么)auto        - [5. 聊一下伙伴内存分配系统](#5-聊一下伙伴内存分配系统)auto        - [6. 聊一下InnoDB的关键特性](#6-聊一下innodb的关键特性)auto    - [Other fun question](#other-fun-question)auto        - [1.一条SQL语句执行得很慢的原因有哪些](#1一条sql语句执行得很慢的原因有哪些)auto        - [2.大表优化方案](#2大表优化方案)autoauto<!-- /TOC -->

# 并发

## 基础

### 1.线程进程含义&关系&区别&优缺点

### 2.并发与并行的区别

### 3.为何使用多线程 可能带来的问题

### 4.线程的生命周期和状态

### 5.什么是上下文切换

### 6.线程死锁？如何避免？

### 7.sleep()方法和wait()方法的区别/共同点

### 8.是否可以直接调用run()  不限start()再run()?

## synchronized

### 1.谈谈自己对于synchronized关键字的了解

### 2.谈谈自己是怎么使用此关键字

### 3.构造方法可以使用他修饰吗

### 4.谈下底层原理

### 5.谈下1.6后底层做了哪些优化,详细介绍一下

### 6.谈谈synchronized和ReentrantLock区别

## volatile

### 1.CPU缓存模型

### 2.讲一下JMM

### 3.并发编程的三个重要特性

### 4.介绍一下对此关键字的理解

### 5.synchronized 与volatile 的区别

## ThreadLocal

### 1.介绍一下是什么及原理

### 2.ThreadLocal 内存泄漏的问题

## 线程池

### 1.为什么要使用线程池

### 2.实现Runnable和Callable接口的区别

### 3.execute（） 与submit（） 区别

### 4.如何创建线程池

### 5.ThreadPoolExecutor类分析

### 6.谈下原理

## Atomic 原子类

### 1.介绍一下 ..

### 2.JUC包中的原子类是哪四类

### 3.讲讲AtomicInteger的使用

### 4.简单介绍一下AtomicInteger类的原理

## AQS

### 1.介绍一下AQS

### 2.AQS原理分析

### 3.组件

### 4.用过CountDownLatch吗 什么场景用的

## Reference

# Mysql

## 架构相关

### 1.结合MySQL架构，聊一下SQL的执行过程

### 2.缓存和缓冲

### 3.谈谈Mysql的储引擎

### 4.怎么理解Mysql对于sql的执行时基于成本模型的

### 5.优化器是怎么运行的,为什么会有错误的决定

## Schema

### 1.谈谈数据的范式,为什么需要范式

### 2.字段有哪些类型

### 3.为什么设定主键，选用什么类型

### 4.水平分表和垂直分表  解释一下？

## 索引

### 1.有哪些类型,逻辑分类和物理分类有哪些

### 2.为什么使用索引

### 3.索引采用了哪些数据结构,分别有什么特征

### 4.like查询可以走索引

### 5.不建议对哪些字段建索引

### 6.Mysql是如何建立索引的

### 7.哪些场景会导致索引失效

### 8.如何创建/使用高性能的索引

### 9.索引对null值是如何处理的

## 事务

### 1.隔离级别有哪些,分别会存在什么问题

### 2.事务的特征及实现

### 3.分布式事务解决方案

## 日志

### 1.redo log 和bin log 有什么区别

### 2.事务提交时，redo log和binlog的写入顺序是怎样的

### 3. redo log什么时候释放？undo log什么时候释放？

### 4. 什么是write-Ahead Log策略？

### 5. bin log记录日志有哪些方式？常用哪种？为什么？各有什么优劣势？

## 锁

### 1. 数据库中有哪些锁，有什么作用，有什么弊端？

### 2. latch 和 lock 有什么区别

### 3. RC 和 RR 在加锁方面有什么不同？

### 4. 什么是死锁，怎么避免死锁？有没有遇到死锁？

### 5. 如何查看死锁信息？

### 6. 发生死锁怎么办？怎么处理？

### 7. MYISAM 和 InnoDB 是怎么支持并发插入的？

### 8. 怎么理解latch中的自旋锁？比较下Java中的自旋锁

## Innodb

### 1. 什么是缓冲池？有什么用？

### 2. 聊一聊LRU算法，InnoDB是怎么实现LRU的？

### 3. 聊一聊InnoDB架构，各组成部分有什么用？

### 4. 脏页刷盘机制是什么？

### 5. 聊一下伙伴内存分配系统

### 6. 聊一下InnoDB的关键特性

## Other fun question

### 1.一条SQL语句执行得很慢的原因有哪些

### 2.大表优化方案

