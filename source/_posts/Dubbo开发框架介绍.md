---
title: Dubbo开发框架介绍
date: 2016-05-25 15:25:04
tags: work
---

## Dubbo框架的层级结构与调用关系：

![此处输入图片的描述][1]

<!-- more -->

## 具体说明：

 - util：公共的函数方法，比如DateUtil
 - dao：数据持久层，操作数据库
 - common：公共逻辑模块，包括业务类通用Util类和通用模型，枚举类型,对外暴露的常量等
 - service-consumer：调用远程服务的服务消费方, 接口集的适配，不做业务层实现
 - biz：具体实际的业务逻辑实现
 - service-provider：暴露服务的服务提供方，浅封装
 - test：集成测试
 - service-api： 对外暴露的接口声明，包括序列化的实体对象BO
 - web：暴露的http，https请求，restful接口等，可以调用provider和biz，不可以直接调用dao

> 对外只能暴露api,其他的不可以 
每个bundle可以有对应的单元测试，mock


  [1]: https://dn-shimo-image.qbox.me/xIPwEpNud8guq5rt.png!thumbnail