---
title: "mysql优化修复表数据库"
date: 2020-07-12 12:10:58
updated: 2020-07-12 12:10:58
tags:
 - mysql
categories: 经验教程
---

OPTIMIZE TABLE `table_name` 优化表

<!-- more -->

---

###### 

OPTIMIZE [LOCAL | NO_WRITE_TO_BINLOG] TABLEtbl_name[,tbl_name] … 

OPTIMIZE TABLE 用于回收闲置的数据库空间，当表上的数据行被删除时，所占据的磁盘空间并没有立即被回收，使用了OPTIMIZE TABLE命令后这些空间将被回收，并且对磁盘上的数据行进行重排（注意：是磁盘上，而非数据库）。

REPAIR TABLE `table_name` 修复表

数据库运行时间过长可能会因为硬盘坏道，死机等众多因素造成数据损坏，可以使用此命令进行修复 



