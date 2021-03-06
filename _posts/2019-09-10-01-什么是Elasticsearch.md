---
layout:     post
title:      01-什么是Elasticsearch
subtitle:   用大白话告诉你什么是Elasticsearch
date:       2019-09-10
author:     yukai.bai
header-img: img/post-bg-kuaidi.jpg
catalog: true
tags:
    - Elasticsearch
    - Java
    - 分布式
---

## 一、前言

### 1、 本博客主要内容
* 什么是搜索
* 如果用数据库做搜索会怎样
* 什么是全文索引、倒排索引和Lucene
* 什么是Elasticsearch

## 二、正文

### 1、 什么是搜索
我们提到搜索的一印象就是百度搜索，我们可以通过百度来查找书，电影等，这只是搜索的一种。百度！=搜索  

垂直搜索（站内搜索）  

互联网的搜索：电商网站，招聘网站，新闻网站，各种app  

IT系统的搜索：OA软件，办公自动化软件，会议管理，日程管理，项目管理，员工管理，搜索“张三”，“张三儿”，“张小三”；有个电商网站，卖家，后台管理系统，搜索“牙膏”，订单，“牙膏相关的订单”  

搜索：就是在任何场景下，找寻你想要的信息，这个时候会输入一段你要搜索的关键字，然后就期望找到这个关键字相关的信息。  

### 2、如果使用数据库做搜索会怎样？

做软件开发的话，或者对IT、计算机有一定的了解的话，都知道，数据都是存储在数据库里面的，比如说电商网站的商品信息，招聘网站的职位信息，新闻网站的新闻信息，等等吧。所以说，很自然的一点，如果说从技术的角度去考虑，如何实现如说，电商网站内部的搜索功能的话，就可以考虑，去使用数据库去进行搜索。  
（1）比方说，每条记录的指定字段的文本，可能会很长，比如说“商品描述”字段的长度，有长达数千个，甚至数万个字符，这个时候，每次都要对每条记录的所有文本进行扫描，懒判断说，你包不包含我指定的这个关键词（比如说“牙膏”）  
（2）还不能将搜索词拆分开来，尽可能去搜索更多的符合你的期望的结果，比如输入“生化机”，就搜索不出来“生化危机”  
受到数据索引，等的限制，用数据库来实现搜索，是不太靠谱的。通常来说，性能会很差的。   
如图：![101](https://github.com/nanaonikaikai/nanaonikaikai.github.io/blob/master/img/101.jpg?raw=true)  

### 3、什么是全文检索和Lucene

（1）全文检索，倒排索引  
如图：![102](https://raw.githubusercontent.com/nanaonikaikai/nanaonikaikai.github.io/master/img/102.jpg)

（2）lucene，就是一个jar包，里面包含了封装好的各种建立倒排索引，以及进行搜索的代码，包括各种算法。我们就用java开发的时候，引入lucene jar，然后基于lucene的api进行去进行开发就可以了。用lucene，我们就可以去将已有的数据建立索引，lucene会在本地磁盘上面，给我们组织索引的数据结构。另外的话，我们也可以用lucene提供的一些功能和api来针对磁盘上   

### 4、什么是Elasticsearch

![103](https://github.com/nanaonikaikai/nanaonikaikai.github.io/blob/master/img/103.jpg?raw=true)
