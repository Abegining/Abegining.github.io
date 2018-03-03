---
layout:     post
title:      zookeeper 学习笔记
subtitle:   浅谈 zookeeper
date:       2018-03-03
author:     Faster
header-img: img/post-bg-universe.jpg
catalog: true
tags:
    - 分布式
---
## 前言
去年用到了kafka，对里面的zookeeper组件一直不是太了解，最近有空学习了一下，写这篇博客，以加深理解。
## zookeeper介绍
ZooKeeper是一个集中服务，用于维护配置信息，命名，提供分布式同步和提供组服务。
所有这些类型的服务都以某种形式被分布式应用程序使用。但是在每次部署分布式应用程序的时候，都会遇到一些错误或者是竞争条件。

1.设计目的
ZooKeeper旨在将这些不同服务的精髓提炼成一个非常简单的集中式协调服务接口。该服务本身是分布式的并且高度可靠。协商一致，组管理和在线协议将由服务实施，以便应用程序不需要自行实施。。ZooKeeper的目标就是封装好容易出错的关键服务，将简单易用的接口和性能高效、功能稳定的系统提供给用户。

1.最终一致性：client不论连接到哪个Server，展示给它都是同一个视图，这是zookeeper最重要的性能。

2 .可靠性：具有简单、健壮、良好的性能，如果消息m被到一台服务器接受，那么它将被所有的服务器接受。

3 .实时性：Zookeeper保证客户端将在一个时间间隔范围内获得服务器的更新信息，或者服务器失效的信息。但由于网络延时等原因，Zookeeper不能保证两个客户端能同时得到刚更新的数据，如果需要最新数据，应该在读数据之前调用sync()接口。

4 .等待无关（wait-free）：慢的或者失效的client不得干预快速的client的请求，使得每个client都能有效的等待。

5.原子性：更新只能成功或者失败，没有中间状态。

6 .顺序性：包括全局有序和偏序两种：全局有序是指如果在一台服务器上消息a在消息b前发布，则在所有Server上消息a都将在消息b前被发布；偏序是指如果一个消息b在消息a后被同一个发送者发布，a必将排在b前面。

ZooKeeper包含一个简单的原语集，提供Java和C的接口。




## 




##参考文档
- [分布式服务框架 Zookeeper -- 管理分布式环境中的数据](https://www.ibm.com/developerworks/cn/opensource/os-cn-zookeeper/)
- https://www.cnblogs.com/cnmenglang/p/6230488.html


