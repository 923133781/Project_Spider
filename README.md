# Project_Spider

[TOC]



## 一、需求

自动抓取网络资源的软件

（1）资源：网页、图片、音乐、视频等

（2）自动抓取：一旦开始运行，就不再需要其它过多的操作

## 二、总体设计

**互联网**- ----> **爬虫系统** ------> **数据库**

总体的设计流程是：

（1）首先得到爬取的种子(URL)

（2）根据爬取种子下载资源（页面）

（3）解析页面，然后提取更多的URL信息

（4）对页面进行持久化操作

（5）根据提取的URL再进行下载操作

（6）重复（2）-（5）



## 三、系统设计

1. 系统总体设计

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200613114854927.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDQ3MDQ0Mw==,size_16,color_FFFFFF,t_70)

2. 控制器的设计

![image-20200613112730754](/home/wch/Software/Spider/Program_Spider/md_picture/image-20200613112730754.png)

控制器由四个模块组成

（1）配置文件处理模块：从配置文件读取配置项，提起配置项的提取接口

（2）URL维护模块：负责维护URL库，提供如下的功能

​		a) 输入新的URL

​		b) 输出一个未被抓取的URL

​		c) 负责维护URL的抓取状态

（3）任务调度模块

​		a) 负责协调控制器的流程

​		b) 负责调用其它的模块完成工作

（4）维护URL列表的数据结构
