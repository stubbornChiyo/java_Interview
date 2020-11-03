# java_Interview

看目录自己面试，答案在下边,会慢慢补充。

* [并发](#%E5%B9%B6%E5%8F%91)
  * [基础](#%E5%9F%BA%E7%A1%80)
    * [1\.线程进程含义&amp;关系&amp;区别&amp;优缺点](#1%E7%BA%BF%E7%A8%8B%E8%BF%9B%E7%A8%8B%E5%90%AB%E4%B9%89%E5%85%B3%E7%B3%BB%E5%8C%BA%E5%88%AB%E4%BC%98%E7%BC%BA%E7%82%B9)
    * [2\.并发与并行的区别](#2%E5%B9%B6%E5%8F%91%E4%B8%8E%E5%B9%B6%E8%A1%8C%E7%9A%84%E5%8C%BA%E5%88%AB)
    * [3\.为何使用多线程 可能带来的问题](#3%E4%B8%BA%E4%BD%95%E4%BD%BF%E7%94%A8%E5%A4%9A%E7%BA%BF%E7%A8%8B-%E5%8F%AF%E8%83%BD%E5%B8%A6%E6%9D%A5%E7%9A%84%E9%97%AE%E9%A2%98)
    * [4\.线程的生命周期和状态](#4%E7%BA%BF%E7%A8%8B%E7%9A%84%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F%E5%92%8C%E7%8A%B6%E6%80%81)
    * [5\.什么是上下文切换](#5%E4%BB%80%E4%B9%88%E6%98%AF%E4%B8%8A%E4%B8%8B%E6%96%87%E5%88%87%E6%8D%A2)
    * [6\.线程死锁？如何避免？](#6%E7%BA%BF%E7%A8%8B%E6%AD%BB%E9%94%81%E5%A6%82%E4%BD%95%E9%81%BF%E5%85%8D)
    * [7\.sleep()方法和wait()方法的区别/共同点](#7sleep%E6%96%B9%E6%B3%95%E5%92%8Cwait%E6%96%B9%E6%B3%95%E7%9A%84%E5%8C%BA%E5%88%AB%E5%85%B1%E5%90%8C%E7%82%B9)
    * [8\.是否可以直接调用run()  不限start()再run()?](#8%E6%98%AF%E5%90%A6%E5%8F%AF%E4%BB%A5%E7%9B%B4%E6%8E%A5%E8%B0%83%E7%94%A8run--%E4%B8%8D%E9%99%90start%E5%86%8Drun)
  * [synchronized](#synchronized)
    * [1\.谈谈自己对于synchronized关键字的了解](#1%E8%B0%88%E8%B0%88%E8%87%AA%E5%B7%B1%E5%AF%B9%E4%BA%8Esynchronized%E5%85%B3%E9%94%AE%E5%AD%97%E7%9A%84%E4%BA%86%E8%A7%A3)
    * [2\.谈谈自己是怎么使用此关键字](#2%E8%B0%88%E8%B0%88%E8%87%AA%E5%B7%B1%E6%98%AF%E6%80%8E%E4%B9%88%E4%BD%BF%E7%94%A8%E6%AD%A4%E5%85%B3%E9%94%AE%E5%AD%97)
    * [3\.构造方法可以使用他修饰吗](#3%E6%9E%84%E9%80%A0%E6%96%B9%E6%B3%95%E5%8F%AF%E4%BB%A5%E4%BD%BF%E7%94%A8%E4%BB%96%E4%BF%AE%E9%A5%B0%E5%90%97)
    * [4\.谈下底层原理](#4%E8%B0%88%E4%B8%8B%E5%BA%95%E5%B1%82%E5%8E%9F%E7%90%86)
    * [5\.谈下1\.6后底层做了哪些优化,详细介绍一下](#5%E8%B0%88%E4%B8%8B16%E5%90%8E%E5%BA%95%E5%B1%82%E5%81%9A%E4%BA%86%E5%93%AA%E4%BA%9B%E4%BC%98%E5%8C%96%E8%AF%A6%E7%BB%86%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8B)
    * [6\.谈谈synchronized和ReentrantLock区别](#6%E8%B0%88%E8%B0%88synchronized%E5%92%8Creentrantlock%E5%8C%BA%E5%88%AB)
  * [volatile](#volatile)
    * [1\.CPU缓存模型](#1cpu%E7%BC%93%E5%AD%98%E6%A8%A1%E5%9E%8B)
    * [2\.讲一下JMM](#2%E8%AE%B2%E4%B8%80%E4%B8%8Bjmm)
    * [3\.并发编程的三个重要特性](#3%E5%B9%B6%E5%8F%91%E7%BC%96%E7%A8%8B%E7%9A%84%E4%B8%89%E4%B8%AA%E9%87%8D%E8%A6%81%E7%89%B9%E6%80%A7)
    * [4\.介绍一下对此关键字的理解](#4%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8B%E5%AF%B9%E6%AD%A4%E5%85%B3%E9%94%AE%E5%AD%97%E7%9A%84%E7%90%86%E8%A7%A3)
    * [5\.synchronized 与volatile 的区别](#5synchronized-%E4%B8%8Evolatile-%E7%9A%84%E5%8C%BA%E5%88%AB)
  * [ThreadLocal](#threadlocal)
    * [1\.介绍一下是什么及原理](#1%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8B%E6%98%AF%E4%BB%80%E4%B9%88%E5%8F%8A%E5%8E%9F%E7%90%86)
    * [2\.ThreadLocal 内存泄漏的问题](#2threadlocal-%E5%86%85%E5%AD%98%E6%B3%84%E6%BC%8F%E7%9A%84%E9%97%AE%E9%A2%98)
  * [线程池](#%E7%BA%BF%E7%A8%8B%E6%B1%A0)
    * [1\.为什么要使用线程池](#1%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E4%BD%BF%E7%94%A8%E7%BA%BF%E7%A8%8B%E6%B1%A0)
    * [2\.实现Runnable和Callable接口的区别](#2%E5%AE%9E%E7%8E%B0runnable%E5%92%8Ccallable%E6%8E%A5%E5%8F%A3%E7%9A%84%E5%8C%BA%E5%88%AB)
    * [3\.execute（） 与submit（） 区别](#3execute-%E4%B8%8Esubmit-%E5%8C%BA%E5%88%AB)
    * [4\.如何创建线程池](#4%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BA%E7%BA%BF%E7%A8%8B%E6%B1%A0)
    * [5\.ThreadPoolExecutor类分析](#5threadpoolexecutor%E7%B1%BB%E5%88%86%E6%9E%90)
    * [6\.谈下原理](#6%E8%B0%88%E4%B8%8B%E5%8E%9F%E7%90%86)
  * [Atomic 原子类](#atomic-%E5%8E%9F%E5%AD%90%E7%B1%BB)
    * [1\.介绍一下 \.\.](#1%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8B-)
    * [2\.JUC包中的原子类是哪四类](#2juc%E5%8C%85%E4%B8%AD%E7%9A%84%E5%8E%9F%E5%AD%90%E7%B1%BB%E6%98%AF%E5%93%AA%E5%9B%9B%E7%B1%BB)
    * [3\.讲讲AtomicInteger的使用](#3%E8%AE%B2%E8%AE%B2atomicinteger%E7%9A%84%E4%BD%BF%E7%94%A8)
    * [4\.简单介绍一下AtomicInteger类的原理](#4%E7%AE%80%E5%8D%95%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8Batomicinteger%E7%B1%BB%E7%9A%84%E5%8E%9F%E7%90%86)
  * [AQS](#aqs)
    * [1\.介绍一下AQS](#1%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8Baqs)
    * [2\.AQS原理分析](#2aqs%E5%8E%9F%E7%90%86%E5%88%86%E6%9E%90)
    * [3\.组件](#3%E7%BB%84%E4%BB%B6)
    * [4\.用过CountDownLatch吗 什么场景用的](#4%E7%94%A8%E8%BF%87countdownlatch%E5%90%97-%E4%BB%80%E4%B9%88%E5%9C%BA%E6%99%AF%E7%94%A8%E7%9A%84)
  * [Reference](#reference)
* [Mysql](#mysql)
  * [架构相关](#%E6%9E%B6%E6%9E%84%E7%9B%B8%E5%85%B3)
    * [1\.结合MySQL架构，聊一下SQL的执行过程](#1%E7%BB%93%E5%90%88mysql%E6%9E%B6%E6%9E%84%E8%81%8A%E4%B8%80%E4%B8%8Bsql%E7%9A%84%E6%89%A7%E8%A1%8C%E8%BF%87%E7%A8%8B)
    * [2\.缓存和缓冲](#2%E7%BC%93%E5%AD%98%E5%92%8C%E7%BC%93%E5%86%B2)
    * [3\.谈谈Mysql的储引擎](#3%E8%B0%88%E8%B0%88mysql%E7%9A%84%E5%82%A8%E5%BC%95%E6%93%8E)
    * [4\.怎么理解Mysql对于sql的执行时基于成本模型的](#4%E6%80%8E%E4%B9%88%E7%90%86%E8%A7%A3mysql%E5%AF%B9%E4%BA%8Esql%E7%9A%84%E6%89%A7%E8%A1%8C%E6%97%B6%E5%9F%BA%E4%BA%8E%E6%88%90%E6%9C%AC%E6%A8%A1%E5%9E%8B%E7%9A%84)
    * [5\.优化器是怎么运行的,为什么会有错误的决定](#5%E4%BC%98%E5%8C%96%E5%99%A8%E6%98%AF%E6%80%8E%E4%B9%88%E8%BF%90%E8%A1%8C%E7%9A%84%E4%B8%BA%E4%BB%80%E4%B9%88%E4%BC%9A%E6%9C%89%E9%94%99%E8%AF%AF%E7%9A%84%E5%86%B3%E5%AE%9A)
  * [Schema](#schema)
    * [1\.谈谈数据的范式,为什么需要范式](#1%E8%B0%88%E8%B0%88%E6%95%B0%E6%8D%AE%E7%9A%84%E8%8C%83%E5%BC%8F%E4%B8%BA%E4%BB%80%E4%B9%88%E9%9C%80%E8%A6%81%E8%8C%83%E5%BC%8F)
    * [2\.字段有哪些类型](#2%E5%AD%97%E6%AE%B5%E6%9C%89%E5%93%AA%E4%BA%9B%E7%B1%BB%E5%9E%8B)
    * [3\.为什么设定主键，选用什么类型](#3%E4%B8%BA%E4%BB%80%E4%B9%88%E8%AE%BE%E5%AE%9A%E4%B8%BB%E9%94%AE%E9%80%89%E7%94%A8%E4%BB%80%E4%B9%88%E7%B1%BB%E5%9E%8B)
    * [4\.水平分表和垂直分表  解释一下？](#4%E6%B0%B4%E5%B9%B3%E5%88%86%E8%A1%A8%E5%92%8C%E5%9E%82%E7%9B%B4%E5%88%86%E8%A1%A8--%E8%A7%A3%E9%87%8A%E4%B8%80%E4%B8%8B)
  * [索引](#%E7%B4%A2%E5%BC%95)
    * [1\.有哪些类型,逻辑分类和物理分类有哪些](#1%E6%9C%89%E5%93%AA%E4%BA%9B%E7%B1%BB%E5%9E%8B%E9%80%BB%E8%BE%91%E5%88%86%E7%B1%BB%E5%92%8C%E7%89%A9%E7%90%86%E5%88%86%E7%B1%BB%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [2\.为什么使用索引](#2%E4%B8%BA%E4%BB%80%E4%B9%88%E4%BD%BF%E7%94%A8%E7%B4%A2%E5%BC%95)
    * [3\.索引采用了哪些数据结构,分别有什么特征](#3%E7%B4%A2%E5%BC%95%E9%87%87%E7%94%A8%E4%BA%86%E5%93%AA%E4%BA%9B%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E5%88%86%E5%88%AB%E6%9C%89%E4%BB%80%E4%B9%88%E7%89%B9%E5%BE%81)
    * [4\.like查询可以走索引](#4like%E6%9F%A5%E8%AF%A2%E5%8F%AF%E4%BB%A5%E8%B5%B0%E7%B4%A2%E5%BC%95)
    * [5\.不建议对哪些字段建索引](#5%E4%B8%8D%E5%BB%BA%E8%AE%AE%E5%AF%B9%E5%93%AA%E4%BA%9B%E5%AD%97%E6%AE%B5%E5%BB%BA%E7%B4%A2%E5%BC%95)
    * [6\.Mysql是如何建立索引的](#6mysql%E6%98%AF%E5%A6%82%E4%BD%95%E5%BB%BA%E7%AB%8B%E7%B4%A2%E5%BC%95%E7%9A%84)
    * [7\.哪些场景会导致索引失效](#7%E5%93%AA%E4%BA%9B%E5%9C%BA%E6%99%AF%E4%BC%9A%E5%AF%BC%E8%87%B4%E7%B4%A2%E5%BC%95%E5%A4%B1%E6%95%88)
    * [8\.如何创建/使用高性能的索引](#8%E5%A6%82%E4%BD%95%E5%88%9B%E5%BB%BA%E4%BD%BF%E7%94%A8%E9%AB%98%E6%80%A7%E8%83%BD%E7%9A%84%E7%B4%A2%E5%BC%95)
    * [9\.索引对null值是如何处理的](#9%E7%B4%A2%E5%BC%95%E5%AF%B9null%E5%80%BC%E6%98%AF%E5%A6%82%E4%BD%95%E5%A4%84%E7%90%86%E7%9A%84)
  * [事务](#%E4%BA%8B%E5%8A%A1)
    * [1\.隔离级别有哪些,分别会存在什么问题](#1%E9%9A%94%E7%A6%BB%E7%BA%A7%E5%88%AB%E6%9C%89%E5%93%AA%E4%BA%9B%E5%88%86%E5%88%AB%E4%BC%9A%E5%AD%98%E5%9C%A8%E4%BB%80%E4%B9%88%E9%97%AE%E9%A2%98)
    * [2\.事务的特征及实现](#2%E4%BA%8B%E5%8A%A1%E7%9A%84%E7%89%B9%E5%BE%81%E5%8F%8A%E5%AE%9E%E7%8E%B0)
    * [3\.分布式事务解决方案](#3%E5%88%86%E5%B8%83%E5%BC%8F%E4%BA%8B%E5%8A%A1%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88)
  * [日志](#%E6%97%A5%E5%BF%97)
    * [1\.redo log 和bin log 有什么区别](#1redo-log-%E5%92%8Cbin-log-%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB)
    * [2\.事务提交时，redo log和binlog的写入顺序是怎样的](#2%E4%BA%8B%E5%8A%A1%E6%8F%90%E4%BA%A4%E6%97%B6redo-log%E5%92%8Cbinlog%E7%9A%84%E5%86%99%E5%85%A5%E9%A1%BA%E5%BA%8F%E6%98%AF%E6%80%8E%E6%A0%B7%E7%9A%84)
    * [3\. redo log什么时候释放？undo log什么时候释放？](#3-redo-log%E4%BB%80%E4%B9%88%E6%97%B6%E5%80%99%E9%87%8A%E6%94%BEundo-log%E4%BB%80%E4%B9%88%E6%97%B6%E5%80%99%E9%87%8A%E6%94%BE)
    * [4\. 什么是write\-Ahead Log策略？](#4-%E4%BB%80%E4%B9%88%E6%98%AFwrite-ahead-log%E7%AD%96%E7%95%A5)
    * [5\. bin log记录日志有哪些方式？常用哪种？为什么？各有什么优劣势？](#5-bin-log%E8%AE%B0%E5%BD%95%E6%97%A5%E5%BF%97%E6%9C%89%E5%93%AA%E4%BA%9B%E6%96%B9%E5%BC%8F%E5%B8%B8%E7%94%A8%E5%93%AA%E7%A7%8D%E4%B8%BA%E4%BB%80%E4%B9%88%E5%90%84%E6%9C%89%E4%BB%80%E4%B9%88%E4%BC%98%E5%8A%A3%E5%8A%BF)
  * [锁](#%E9%94%81)
    * [1\. 数据库中有哪些锁，有什么作用，有什么弊端？](#1-%E6%95%B0%E6%8D%AE%E5%BA%93%E4%B8%AD%E6%9C%89%E5%93%AA%E4%BA%9B%E9%94%81%E6%9C%89%E4%BB%80%E4%B9%88%E4%BD%9C%E7%94%A8%E6%9C%89%E4%BB%80%E4%B9%88%E5%BC%8A%E7%AB%AF)
    * [2\. latch 和 lock 有什么区别](#2-latch-%E5%92%8C-lock-%E6%9C%89%E4%BB%80%E4%B9%88%E5%8C%BA%E5%88%AB)
    * [3\. RC 和 RR 在加锁方面有什么不同？](#3-rc-%E5%92%8C-rr-%E5%9C%A8%E5%8A%A0%E9%94%81%E6%96%B9%E9%9D%A2%E6%9C%89%E4%BB%80%E4%B9%88%E4%B8%8D%E5%90%8C)
    * [4\. 什么是死锁，怎么避免死锁？有没有遇到死锁？](#4-%E4%BB%80%E4%B9%88%E6%98%AF%E6%AD%BB%E9%94%81%E6%80%8E%E4%B9%88%E9%81%BF%E5%85%8D%E6%AD%BB%E9%94%81%E6%9C%89%E6%B2%A1%E6%9C%89%E9%81%87%E5%88%B0%E6%AD%BB%E9%94%81)
    * [5\. 如何查看死锁信息？](#5-%E5%A6%82%E4%BD%95%E6%9F%A5%E7%9C%8B%E6%AD%BB%E9%94%81%E4%BF%A1%E6%81%AF)
    * [6\. 发生死锁怎么办？怎么处理？](#6-%E5%8F%91%E7%94%9F%E6%AD%BB%E9%94%81%E6%80%8E%E4%B9%88%E5%8A%9E%E6%80%8E%E4%B9%88%E5%A4%84%E7%90%86)
    * [7\. MYISAM 和 InnoDB 是怎么支持并发插入的？](#7-myisam-%E5%92%8C-innodb-%E6%98%AF%E6%80%8E%E4%B9%88%E6%94%AF%E6%8C%81%E5%B9%B6%E5%8F%91%E6%8F%92%E5%85%A5%E7%9A%84)
    * [8\. 怎么理解latch中的自旋锁？比较下Java中的自旋锁](#8-%E6%80%8E%E4%B9%88%E7%90%86%E8%A7%A3latch%E4%B8%AD%E7%9A%84%E8%87%AA%E6%97%8B%E9%94%81%E6%AF%94%E8%BE%83%E4%B8%8Bjava%E4%B8%AD%E7%9A%84%E8%87%AA%E6%97%8B%E9%94%81)
  * [Innodb](#innodb)
    * [1\. 什么是缓冲池？有什么用？](#1-%E4%BB%80%E4%B9%88%E6%98%AF%E7%BC%93%E5%86%B2%E6%B1%A0%E6%9C%89%E4%BB%80%E4%B9%88%E7%94%A8)
    * [2\. 聊一聊LRU算法，InnoDB是怎么实现LRU的？](#2-%E8%81%8A%E4%B8%80%E8%81%8Alru%E7%AE%97%E6%B3%95innodb%E6%98%AF%E6%80%8E%E4%B9%88%E5%AE%9E%E7%8E%B0lru%E7%9A%84)
    * [3\. 聊一聊InnoDB架构，各组成部分有什么用？](#3-%E8%81%8A%E4%B8%80%E8%81%8Ainnodb%E6%9E%B6%E6%9E%84%E5%90%84%E7%BB%84%E6%88%90%E9%83%A8%E5%88%86%E6%9C%89%E4%BB%80%E4%B9%88%E7%94%A8)
    * [4\. 脏页刷盘机制是什么？](#4-%E8%84%8F%E9%A1%B5%E5%88%B7%E7%9B%98%E6%9C%BA%E5%88%B6%E6%98%AF%E4%BB%80%E4%B9%88)
    * [5\. 聊一下伙伴内存分配系统](#5-%E8%81%8A%E4%B8%80%E4%B8%8B%E4%BC%99%E4%BC%B4%E5%86%85%E5%AD%98%E5%88%86%E9%85%8D%E7%B3%BB%E7%BB%9F)
    * [6\. 聊一下InnoDB的关键特性](#6-%E8%81%8A%E4%B8%80%E4%B8%8Binnodb%E7%9A%84%E5%85%B3%E9%94%AE%E7%89%B9%E6%80%A7)
  * [Other fun question](#other-fun-question)
    * [1\.一条SQL语句执行得很慢的原因有哪些](#1%E4%B8%80%E6%9D%A1sql%E8%AF%AD%E5%8F%A5%E6%89%A7%E8%A1%8C%E5%BE%97%E5%BE%88%E6%85%A2%E7%9A%84%E5%8E%9F%E5%9B%A0%E6%9C%89%E5%93%AA%E4%BA%9B)
    * [2\.大表优化方案](#2%E5%A4%A7%E8%A1%A8%E4%BC%98%E5%8C%96%E6%96%B9%E6%A1%88)
* [Redis](#redis)
    * [应用场景及数据结构算法](#%E5%BA%94%E7%94%A8%E5%9C%BA%E6%99%AF%E5%8F%8A%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E7%AE%97%E6%B3%95)
      * [1\.简述缓存的基本思想](#1%E7%AE%80%E8%BF%B0%E7%BC%93%E5%AD%98%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%80%9D%E6%83%B3)
      * [2\.为什么要用分布式缓存 \- 不直接用本地缓存](#2%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E7%94%A8%E5%88%86%E5%B8%83%E5%BC%8F%E7%BC%93%E5%AD%98---%E4%B8%8D%E7%9B%B4%E6%8E%A5%E7%94%A8%E6%9C%AC%E5%9C%B0%E7%BC%93%E5%AD%98)
      * [3\.简单介绍一下redis](#3%E7%AE%80%E5%8D%95%E4%BB%8B%E7%BB%8D%E4%B8%80%E4%B8%8Bredis)
      * [4\.redis和memcached的区别和共同点](#4redis%E5%92%8Cmemcached%E7%9A%84%E5%8C%BA%E5%88%AB%E5%92%8C%E5%85%B1%E5%90%8C%E7%82%B9)
      * [5\.为什么要用缓存/为什么要用redis](#5%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E7%94%A8%E7%BC%93%E5%AD%98%E4%B8%BA%E4%BB%80%E4%B9%88%E8%A6%81%E7%94%A8redis)
      * [6\.redis给缓存数据设置过期时间有啥用](#6redis%E7%BB%99%E7%BC%93%E5%AD%98%E6%95%B0%E6%8D%AE%E8%AE%BE%E7%BD%AE%E8%BF%87%E6%9C%9F%E6%97%B6%E9%97%B4%E6%9C%89%E5%95%A5%E7%94%A8)
      * [7\.redis可以实现事务吗？如何实现的](#7redis%E5%8F%AF%E4%BB%A5%E5%AE%9E%E7%8E%B0%E4%BA%8B%E5%8A%A1%E5%90%97%E5%A6%82%E4%BD%95%E5%AE%9E%E7%8E%B0%E7%9A%84)
      * [8\.如何利用Redis实现乐观锁？](#8%E5%A6%82%E4%BD%95%E5%88%A9%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E4%B9%90%E8%A7%82%E9%94%81)
      * [9\.了解Redis的管道吗？有什么好处？](#9%E4%BA%86%E8%A7%A3redis%E7%9A%84%E7%AE%A1%E9%81%93%E5%90%97%E6%9C%89%E4%BB%80%E4%B9%88%E5%A5%BD%E5%A4%84)
      * [10\.谈一下缓存穿透](#10%E8%B0%88%E4%B8%80%E4%B8%8B%E7%BC%93%E5%AD%98%E7%A9%BF%E9%80%8F)
      * [11\.谈一下缓存击穿](#11%E8%B0%88%E4%B8%80%E4%B8%8B%E7%BC%93%E5%AD%98%E5%87%BB%E7%A9%BF)
      * [12\.谈一下缓存雪崩](#12%E8%B0%88%E4%B8%80%E4%B8%8B%E7%BC%93%E5%AD%98%E9%9B%AA%E5%B4%A9)
      * [13\.Redis有一个分布式锁，有什么弊端？怎么解决？](#13redis%E6%9C%89%E4%B8%80%E4%B8%AA%E5%88%86%E5%B8%83%E5%BC%8F%E9%94%81%E6%9C%89%E4%BB%80%E4%B9%88%E5%BC%8A%E7%AB%AF%E6%80%8E%E4%B9%88%E8%A7%A3%E5%86%B3)
      * [14\.如何保证缓存和数据库数据的一致性？](#14%E5%A6%82%E4%BD%95%E4%BF%9D%E8%AF%81%E7%BC%93%E5%AD%98%E5%92%8C%E6%95%B0%E6%8D%AE%E5%BA%93%E6%95%B0%E6%8D%AE%E7%9A%84%E4%B8%80%E8%87%B4%E6%80%A7)
      * [15\.Redis中，big key有哪些危害？怎么避免？](#15redis%E4%B8%ADbig-key%E6%9C%89%E5%93%AA%E4%BA%9B%E5%8D%B1%E5%AE%B3%E6%80%8E%E4%B9%88%E9%81%BF%E5%85%8D)
      * [16\.常见数据结构及使用场景](#16%E5%B8%B8%E8%A7%81%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E5%8F%8A%E4%BD%BF%E7%94%A8%E5%9C%BA%E6%99%AF)
      * [17\.为什么Redis选择使用跳表而不是红黑树来实现有序集合？](#17%E4%B8%BA%E4%BB%80%E4%B9%88redis%E9%80%89%E6%8B%A9%E4%BD%BF%E7%94%A8%E8%B7%B3%E8%A1%A8%E8%80%8C%E4%B8%8D%E6%98%AF%E7%BA%A2%E9%BB%91%E6%A0%91%E6%9D%A5%E5%AE%9E%E7%8E%B0%E6%9C%89%E5%BA%8F%E9%9B%86%E5%90%88)
      * [18\.聊一下ziplist、quicklist、intset](#18%E8%81%8A%E4%B8%80%E4%B8%8Bziplistquicklistintset)
      * [19\.聊一下Hyperloglog](#19%E8%81%8A%E4%B8%80%E4%B8%8Bhyperloglog)
      * [20\.什么是一致性哈希算法？什么是哈希槽？](#20%E4%BB%80%E4%B9%88%E6%98%AF%E4%B8%80%E8%87%B4%E6%80%A7%E5%93%88%E5%B8%8C%E7%AE%97%E6%B3%95%E4%BB%80%E4%B9%88%E6%98%AF%E5%93%88%E5%B8%8C%E6%A7%BD)
      * [21\.keys \* 有什么风险？该怎么解决？](#21keys--%E6%9C%89%E4%BB%80%E4%B9%88%E9%A3%8E%E9%99%A9%E8%AF%A5%E6%80%8E%E4%B9%88%E8%A7%A3%E5%86%B3)
      * [22\.如何用Redis实现一个延时队列？](#22%E5%A6%82%E4%BD%95%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E4%B8%80%E4%B8%AA%E5%BB%B6%E6%97%B6%E9%98%9F%E5%88%97)
      * [23\.如何用Redis实现购物车功能？](#23%E5%A6%82%E4%BD%95%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E8%B4%AD%E7%89%A9%E8%BD%A6%E5%8A%9F%E8%83%BD)
      * [24\.如何用Redis实现微信微博点赞功能？](#24%E5%A6%82%E4%BD%95%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E5%BE%AE%E4%BF%A1%E5%BE%AE%E5%8D%9A%E7%82%B9%E8%B5%9E%E5%8A%9F%E8%83%BD)
      * [25\.如何用Redis实现微博关注功能中，你可能认识的人？你和他的共同好友？](#25%E5%A6%82%E4%BD%95%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E5%BE%AE%E5%8D%9A%E5%85%B3%E6%B3%A8%E5%8A%9F%E8%83%BD%E4%B8%AD%E4%BD%A0%E5%8F%AF%E8%83%BD%E8%AE%A4%E8%AF%86%E7%9A%84%E4%BA%BA%E4%BD%A0%E5%92%8C%E4%BB%96%E7%9A%84%E5%85%B1%E5%90%8C%E5%A5%BD%E5%8F%8B)
      * [26\.如何利用Redis实现微信抽奖功能？一次抽奖抽出六个人 或 多次抽奖包含三等奖、二等奖、一等奖](#26%E5%A6%82%E4%BD%95%E5%88%A9%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E5%BE%AE%E4%BF%A1%E6%8A%BD%E5%A5%96%E5%8A%9F%E8%83%BD%E4%B8%80%E6%AC%A1%E6%8A%BD%E5%A5%96%E6%8A%BD%E5%87%BA%E5%85%AD%E4%B8%AA%E4%BA%BA-%E6%88%96-%E5%A4%9A%E6%AC%A1%E6%8A%BD%E5%A5%96%E5%8C%85%E5%90%AB%E4%B8%89%E7%AD%89%E5%A5%96%E4%BA%8C%E7%AD%89%E5%A5%96%E4%B8%80%E7%AD%89%E5%A5%96)
      * [27\.如何利用Redis实现微博热搜？](#27%E5%A6%82%E4%BD%95%E5%88%A9%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E5%BE%AE%E5%8D%9A%E7%83%AD%E6%90%9C)
      * [28\.如何利用Redis实现电商中，根据各个标签筛选商品？一个商品可能涉及多个标签](#28%E5%A6%82%E4%BD%95%E5%88%A9%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E7%94%B5%E5%95%86%E4%B8%AD%E6%A0%B9%E6%8D%AE%E5%90%84%E4%B8%AA%E6%A0%87%E7%AD%BE%E7%AD%9B%E9%80%89%E5%95%86%E5%93%81%E4%B8%80%E4%B8%AA%E5%95%86%E5%93%81%E5%8F%AF%E8%83%BD%E6%B6%89%E5%8F%8A%E5%A4%9A%E4%B8%AA%E6%A0%87%E7%AD%BE)
      * [29\.如何利用Redis实现附近的人？](#29%E5%A6%82%E4%BD%95%E5%88%A9%E7%94%A8redis%E5%AE%9E%E7%8E%B0%E9%99%84%E8%BF%91%E7%9A%84%E4%BA%BA)
      * [30\.Redis中有一个限流模块，了解过吗？谈一下几大限流算法](#30redis%E4%B8%AD%E6%9C%89%E4%B8%80%E4%B8%AA%E9%99%90%E6%B5%81%E6%A8%A1%E5%9D%97%E4%BA%86%E8%A7%A3%E8%BF%87%E5%90%97%E8%B0%88%E4%B8%80%E4%B8%8B%E5%87%A0%E5%A4%A7%E9%99%90%E6%B5%81%E7%AE%97%E6%B3%95)
      * [31\.怎么设计一套秒杀系统？](#31%E6%80%8E%E4%B9%88%E8%AE%BE%E8%AE%A1%E4%B8%80%E5%A5%97%E7%A7%92%E6%9D%80%E7%B3%BB%E7%BB%9F)
    * [工作机制](#%E5%B7%A5%E4%BD%9C%E6%9C%BA%E5%88%B6)
      * [1\.缓存读写模式及更新策略](#1%E7%BC%93%E5%AD%98%E8%AF%BB%E5%86%99%E6%A8%A1%E5%BC%8F%E5%8F%8A%E6%9B%B4%E6%96%B0%E7%AD%96%E7%95%A5)
        * [Read/Write Through Pattern（读写穿透）](#readwrite-through-pattern%E8%AF%BB%E5%86%99%E7%A9%BF%E9%80%8F)
        * [Write Behind Pattern（异步缓存写入）](#write-behind-pattern%E5%BC%82%E6%AD%A5%E7%BC%93%E5%AD%98%E5%86%99%E5%85%A5)
      * [2\.为什么redis选择单线程模型](#2%E4%B8%BA%E4%BB%80%E4%B9%88redis%E9%80%89%E6%8B%A9%E5%8D%95%E7%BA%BF%E7%A8%8B%E6%A8%A1%E5%9E%8B)
      * [3\.缓存淘汰机制了解吗？有什么算法？](#3%E7%BC%93%E5%AD%98%E6%B7%98%E6%B1%B0%E6%9C%BA%E5%88%B6%E4%BA%86%E8%A7%A3%E5%90%97%E6%9C%89%E4%BB%80%E4%B9%88%E7%AE%97%E6%B3%95)
      * [4\.谈一下Redis的内存回收机制](#4%E8%B0%88%E4%B8%80%E4%B8%8Bredis%E7%9A%84%E5%86%85%E5%AD%98%E5%9B%9E%E6%94%B6%E6%9C%BA%E5%88%B6)
      * [5\.如何判断数据是否过期的及过期数据的删除策略](#5%E5%A6%82%E4%BD%95%E5%88%A4%E6%96%AD%E6%95%B0%E6%8D%AE%E6%98%AF%E5%90%A6%E8%BF%87%E6%9C%9F%E7%9A%84%E5%8F%8A%E8%BF%87%E6%9C%9F%E6%95%B0%E6%8D%AE%E7%9A%84%E5%88%A0%E9%99%A4%E7%AD%96%E7%95%A5)
      * [6\.主从架构中，怎么执行删除过期key的？](#6%E4%B8%BB%E4%BB%8E%E6%9E%B6%E6%9E%84%E4%B8%AD%E6%80%8E%E4%B9%88%E6%89%A7%E8%A1%8C%E5%88%A0%E9%99%A4%E8%BF%87%E6%9C%9Fkey%E7%9A%84)
      * [7\.怎么保证redis挂掉之后再重启数据可以进行恢复（redis的持久化）](#7%E6%80%8E%E4%B9%88%E4%BF%9D%E8%AF%81redis%E6%8C%82%E6%8E%89%E4%B9%8B%E5%90%8E%E5%86%8D%E9%87%8D%E5%90%AF%E6%95%B0%E6%8D%AE%E5%8F%AF%E4%BB%A5%E8%BF%9B%E8%A1%8C%E6%81%A2%E5%A4%8Dredis%E7%9A%84%E6%8C%81%E4%B9%85%E5%8C%96)
      * [7\.谈一下AOF中，AOF重写的目的](#7%E8%B0%88%E4%B8%80%E4%B8%8Baof%E4%B8%ADaof%E9%87%8D%E5%86%99%E7%9A%84%E7%9B%AE%E7%9A%84)
      * [8\.Redis是怎么实现RDB的？聊一下fork子进程的工作过程](#8redis%E6%98%AF%E6%80%8E%E4%B9%88%E5%AE%9E%E7%8E%B0rdb%E7%9A%84%E8%81%8A%E4%B8%80%E4%B8%8Bfork%E5%AD%90%E8%BF%9B%E7%A8%8B%E7%9A%84%E5%B7%A5%E4%BD%9C%E8%BF%87%E7%A8%8B)
      * [9\.RDB中，save 和 bgsave有啥区别？](#9rdb%E4%B8%ADsave-%E5%92%8C-bgsave%E6%9C%89%E5%95%A5%E5%8C%BA%E5%88%AB)
      * [10\.能解释下什么是RESP？有什么特点？Redis是怎么用的？](#10%E8%83%BD%E8%A7%A3%E9%87%8A%E4%B8%8B%E4%BB%80%E4%B9%88%E6%98%AFresp%E6%9C%89%E4%BB%80%E4%B9%88%E7%89%B9%E7%82%B9redis%E6%98%AF%E6%80%8E%E4%B9%88%E7%94%A8%E7%9A%84)
    * [集群](#%E9%9B%86%E7%BE%A4)
      * [1\.redis主从怎么复制的？有哪些方案？](#1redis%E4%B8%BB%E4%BB%8E%E6%80%8E%E4%B9%88%E5%A4%8D%E5%88%B6%E7%9A%84%E6%9C%89%E5%93%AA%E4%BA%9B%E6%96%B9%E6%A1%88)
      * [2\.从节点挂掉之后重新启动，怎么跟主节点保持一致？会有什么问题吗？](#2%E4%BB%8E%E8%8A%82%E7%82%B9%E6%8C%82%E6%8E%89%E4%B9%8B%E5%90%8E%E9%87%8D%E6%96%B0%E5%90%AF%E5%8A%A8%E6%80%8E%E4%B9%88%E8%B7%9F%E4%B8%BB%E8%8A%82%E7%82%B9%E4%BF%9D%E6%8C%81%E4%B8%80%E8%87%B4%E4%BC%9A%E6%9C%89%E4%BB%80%E4%B9%88%E9%97%AE%E9%A2%98%E5%90%97)
      * [3\.谈一下Redis集群方式。sentinel工作原理？Redis cluster工作原理？](#3%E8%B0%88%E4%B8%80%E4%B8%8Bredis%E9%9B%86%E7%BE%A4%E6%96%B9%E5%BC%8Fsentinel%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86redis-cluster%E5%B7%A5%E4%BD%9C%E5%8E%9F%E7%90%86)
      * [4\.谈一下 CAP，Redis符合哪些？为什么？](#4%E8%B0%88%E4%B8%80%E4%B8%8B-capredis%E7%AC%A6%E5%90%88%E5%93%AA%E4%BA%9B%E4%B8%BA%E4%BB%80%E4%B9%88)
      * [5\.sentinel 和 Redis cluster对比一下，有哪些优缺点？](#5sentinel-%E5%92%8C-redis-cluster%E5%AF%B9%E6%AF%94%E4%B8%80%E4%B8%8B%E6%9C%89%E5%93%AA%E4%BA%9B%E4%BC%98%E7%BC%BA%E7%82%B9)
      * [6\.谈一下Redis cluster中槽位是怎么转移的？](#6%E8%B0%88%E4%B8%80%E4%B8%8Bredis-cluster%E4%B8%AD%E6%A7%BD%E4%BD%8D%E6%98%AF%E6%80%8E%E4%B9%88%E8%BD%AC%E7%A7%BB%E7%9A%84)
      * [7\.Redis cluster中，\-MOVED 和 \-asking的区别？](#7redis-cluster%E4%B8%AD-moved-%E5%92%8C--asking%E7%9A%84%E5%8C%BA%E5%88%AB)
      * [8\.Redis cluster中，客户端会缓存一份槽位信息映射表。当槽位发生变化后，客户端是怎么感知的？](#8redis-cluster%E4%B8%AD%E5%AE%A2%E6%88%B7%E7%AB%AF%E4%BC%9A%E7%BC%93%E5%AD%98%E4%B8%80%E4%BB%BD%E6%A7%BD%E4%BD%8D%E4%BF%A1%E6%81%AF%E6%98%A0%E5%B0%84%E8%A1%A8%E5%BD%93%E6%A7%BD%E4%BD%8D%E5%8F%91%E7%94%9F%E5%8F%98%E5%8C%96%E5%90%8E%E5%AE%A2%E6%88%B7%E7%AB%AF%E6%98%AF%E6%80%8E%E4%B9%88%E6%84%9F%E7%9F%A5%E7%9A%84)
      * [9\.集群节点变更后，客户端是怎么感知的？](#9%E9%9B%86%E7%BE%A4%E8%8A%82%E7%82%B9%E5%8F%98%E6%9B%B4%E5%90%8E%E5%AE%A2%E6%88%B7%E7%AB%AF%E6%98%AF%E6%80%8E%E4%B9%88%E6%84%9F%E7%9F%A5%E7%9A%84)
      * [10\.Redis cluster是怎么处理网络抖动的？](#10redis-cluster%E6%98%AF%E6%80%8E%E4%B9%88%E5%A4%84%E7%90%86%E7%BD%91%E7%BB%9C%E6%8A%96%E5%8A%A8%E7%9A%84)
      * [11\.谈一下Redis cluster中的 GOSIP 协议](#11%E8%B0%88%E4%B8%80%E4%B8%8Bredis-cluster%E4%B8%AD%E7%9A%84-gosip-%E5%8D%8F%E8%AE%AE)

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

# Redis

## 应用场景及数据结构算法

### 1.简述缓存的基本思想

- 可以提高系统性能以及减少请求响应时间。基本思想是空间换时间,cpu缓存的是内存数据-用于解决CPU运算速度和内存读写速度不匹配的问题 内存缓存的是硬盘的数据 用于解决硬盘访问速度过慢的问题 操作系统在页表方案基础上引入快表加速虚拟地址到物理地址的转换 那么块表可以理解为一种特殊的高速缓冲存储器。从业务的角度,为了避免用户在请求数据时获取速度过于缓慢，在数据库之上增加了缓存

### 2.为什么要用分布式缓存 - 不直接用本地缓存

- 本地缓存对分布式架构支持不友好 - 本地缓存只在当前机器上 同一个相同服务部署在多台服务器上，各个服务之间的缓存无法共享
- 本地缓存容量受服务器部署所在的机器限制 - 如果当前系统服务耗费的内存多，本地缓存可用的容量就很少

使用分布式缓存后，缓存部署在一台单独的服务器上，即使同一份服务部署在多台服务器上，使用的是同一份缓存。单独分布式缓存服务的性能 容量和提供的功能都要强大

### 3.简单介绍一下redis

c语言开发的数据库,数据是存放在内存中的，所以读写速度非常快。被广泛用于缓存方向，除此之外 经常被用来用分布式锁/消息队列等 提供了多种数据类型来支持不同的业务场景，支持事务/持久化/Lua脚本/多种集群方案

### 4.redis和memcached的区别和共同点

https://github.com/Snailclimb/JavaGuide/blob/master/docs/database/Redis/redis-all.md

### 5.为什么要用缓存/为什么要用redis

### 6.redis给缓存数据设置过期时间有啥用

### 7.redis可以实现事务吗？如何实现的

### 8.如何利用Redis实现乐观锁？

### 9.了解Redis的管道吗？有什么好处？

### 10.谈一下缓存穿透

### 11.谈一下缓存击穿

### 12.谈一下缓存雪崩

### 13.Redis有一个分布式锁，有什么弊端？怎么解决？

### 14.如何保证缓存和数据库数据的一致性？

### 15.Redis中，big key有哪些危害？怎么避免？

### 16.常见数据结构及使用场景

### 17.为什么Redis选择使用跳表而不是红黑树来实现有序集合？

### 18.聊一下ziplist、quicklist、intset

### 19.聊一下Hyperloglog

### 20.什么是一致性哈希算法？什么是哈希槽？

### 21.keys * 有什么风险？该怎么解决？

### 22.如何用Redis实现一个延时队列？

### 23.如何用Redis实现购物车功能？

### 24.如何用Redis实现微信微博点赞功能？

### 25.如何用Redis实现微博关注功能中，你可能认识的人？你和他的共同好友？

### 26.如何利用Redis实现微信抽奖功能？一次抽奖抽出六个人 或 多次抽奖包含三等奖、二等奖、一等奖

### 27.如何利用Redis实现微博热搜？

### 28.如何利用Redis实现电商中，根据各个标签筛选商品？一个商品可能涉及多个标签

### 29.如何利用Redis实现附近的人？

### 30.Redis中有一个限流模块，了解过吗？谈一下几大限流算法

### 31.怎么设计一套秒杀系统？

## 工作机制

### 1.缓存读写模式及更新策略

- Cache Aside Pattern（旁路缓存模式）

写：更新 DB，然后直接删除 cache 。

读：从 cache 中读取数据，读取到就直接返回，读取不到的话，就从 DB 中取数据返回，然后再把数据放到 cache 中。

Cache Aside Pattern 中服务端需要同时维系 DB 和 cache，并且是以 DB 的结果为准。另外，Cache Aside Pattern 有首次请求数据一定不在 cache 的问题，对于热点数据可以提前放入缓存中。

**Cache Aside Pattern 是我们平时使用比较多的一个缓存读写模式，比较适合读请求比较多的场景。**

- ####  Read/Write Through Pattern（读写穿透）

Read/Write Through 套路是：服务端把 cache 视为主要数据存储，从中读取数据并将数据写入其中。cache 服务负责将此数据读取和写入 DB，从而减轻了应用程序的职责。

1. 写（Write Through）：先查 cache，cache 中不存在，直接更新 DB。 cache 中存在，则先更新 cache，然后 cache 服务自己更新 DB（**同步更新 cache 和 DB**）。
2. 读(Read Through)： 从 cache 中读取数据，读取到就直接返回 。读取不到的话，先从 DB 加载，写入到 cache 后返回响应。

Read-Through Pattern 实际只是在 Cache-Aside Pattern 之上进行了封装。在 Cache-Aside Pattern 下，发生读请求的时候，如果 cache 中不存在对应的数据，是由客户端自己负责把数据写入 cache，而 Read Through Pattern 则是 cache 服务自己来写入缓存的，这对客户端是透明的。

和 Cache Aside Pattern 一样， Read-Through Pattern 也有首次请求数据一定不再 cache 的问题，对于热点数据可以提前放入缓存中。

- #### Write Behind Pattern（异步缓存写入）

Write Behind Pattern 和 Read/Write Through Pattern 很相似，两者都是由 cache 服务来负责 cache 和 DB 的读写。

但是，两个又有很大的不同：**Read/Write Through 是同步更新 cache 和 DB，而 Write Behind Caching 则是只更新缓存，不直接更新 DB，而是改为异步批量的方式来更新 DB。**

**Write Behind Pattern 下 DB 的写性能非常高，尤其适合一些数据经常变化的业务场景比如说一篇文章的点赞数量、阅读数量。** 往常一篇文章被点赞 500 次的话，需要重复修改 500 次 DB，但是在 Write Behind Pattern 下可能只需要修改一次 DB 就可以了。

但是，这种模式同样也给 DB 和 Cache 一致性带来了新的考验，很多时候如果数据还没异步更新到 DB 的话，Cache 服务宕机就 gg 了。

### 2.为什么redis选择单线程模型

https://draveness.me/whys-the-design-redis-single-thread/

### 3.缓存淘汰机制了解吗？有什么算法？

（LRU+贪心算法）

### 4.谈一下Redis的内存回收机制

（数据页）

### 5.如何判断数据是否过期的及过期数据的删除策略

### 6.主从架构中，怎么执行删除过期key的？

### 7.怎么保证redis挂掉之后再重启数据可以进行恢复（redis的持久化）

### 7.谈一下AOF中，AOF重写的目的

### 8.Redis是怎么实现RDB的？聊一下fork子进程的工作过程

### 9.RDB中，save 和 bgsave有啥区别？

### 10.能解释下什么是RESP？有什么特点？Redis是怎么用的？

## 集群

### 1.redis主从怎么复制的？有哪些方案？

### 2.从节点挂掉之后重新启动，怎么跟主节点保持一致？会有什么问题吗？

### 3.谈一下Redis集群方式。sentinel工作原理？Redis cluster工作原理？

### 4.谈一下 CAP，Redis符合哪些？为什么？

### 5.sentinel 和 Redis cluster对比一下，有哪些优缺点？

### 6.谈一下Redis cluster中槽位是怎么转移的？

### 7.Redis cluster中，-MOVED 和 -asking的区别？

### 8.Redis cluster中，客户端会缓存一份槽位信息映射表。当槽位发生变化后，客户端是怎么感知的？

### 9.集群节点变更后，客户端是怎么感知的？

### 10.Redis cluster是怎么处理网络抖动的？

### 11.谈一下Redis cluster中的 GOSIP 协议