---
title: Windows+Ubuntu双系统安装
date: 2020-07-18 21:56:04
updated: 2020-07-18 21:56:04
tags:
 - linux
 - ubuntu
 - windows
 - 双系统
categories: 经验教程
---

## 所需工具

- Windows10
- U盘≥4G 推荐8G
- Rufus刻录软件 http://rufus.ie/
- Ubuntu镜像文件(建议20.04) https://ubuntu.com/#download-content

## 准备工作

### 创建未分配分区

<!-- more -->

在Win10中打开`磁盘管理器` 找一个磁盘分区，右键`压缩卷`压缩一部分空间给Ubuntu使用，建议压缩≥50G出来，压缩出来的硬盘应处于未分配状态。

![1](D:\xiemei\source\images\WindowsUbuntu\drive.png)

### 制作启动盘

插入U盘，打开`Rufus`选择镜像位置 其他选项请对照下图 然后点击确定开始制作启动盘

![2](D:\xiemei\source\images\WindowsUbuntu\Rufus.png)

![](D:\xiemei\source\images\WindowsUbuntu\install.png)

## 开始安装

从USB启动系统这个相信的大家都会 插入U盘，开机，进入BIOS（我的是按住F2），更改启动引导，将U盘排在第一，退出并保存。
出现安装引导界面，可以先选择体验Ubuntu系统，进入桌面后双击左上角Installer，开始安装流程

![4](D:\xiemei\source\images\WindowsUbuntu\one.png)

![5](D:\xiemei\source\images\WindowsUbuntu\two.png)

![6](D:\xiemei\source\images\WindowsUbuntu\three.png)

然后来到最重要的一步，选择`安装类型`
最好`不要选择`第一项与`Windows共存`，因为这样系统会自动进行磁盘分区，还需要在Windows下用easyBCD添加引导然后才能启动Windows。
所以推荐选`其他选项`，进行磁盘分区

![7](D:\xiemei\source\images\WindowsUbuntu\4.jpg)

选中`空闲`点击加号，依次添加2个分区：

- /，主分区，Ext4，越多越好
- swap，逻辑分区，交换空间，4G （Linux不会像Windows那样频繁读写虚拟内存所以不需要分太多）

下边安装启动引导器的设备选择`/主分区`(/dev/sda3)即可，点击现在安装。

![8](D:\xiemei\source\images\WindowsUbuntu\5.jpg)

![9](D:\xiemei\source\images\WindowsUbuntu\6.jpg)

## 安装完成

到此大功告成 等待5-10分钟即可安装完成

![10](D:\xiemei\source\images\WindowsUbuntu\7.jpg)

![11](D:\xiemei\source\images\WindowsUbuntu\8.jpg)