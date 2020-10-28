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

