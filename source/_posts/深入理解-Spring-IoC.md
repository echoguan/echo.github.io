---
title: 深入理解 Spring IoC
categories: 技术
date: 2018-08-05 16:38:00
tags: Spring
---

#### IOC 理论

- IoC 全称为 `InversionofControl`，翻译为 “控制反转”，它还有一个别名为 DI（ `DependencyInjection`），即依赖注入。
- **所谓 IOC ，就是由 Spring IOC 容器来负责对象的生命周期和对象之间的关系。**
- IoC 的理念就是**让别人为你服务。**



1. **谁控制谁**：在传统的开发模式下，我们都是采用直接 new 一个对象的方式来创建对象，也就是说你依赖的对象直接由你自己控制，但是有了 IOC 容器后，则直接由 IoC 容器来控制。所以“谁控制谁”，当然是 IoC 容器控制对象。
2. **控制什么**：控制对象。
3. **为何是反转**：没有 IoC 的时候我们都是在自己对象中主动去创建被依赖的对象，这是正转。但是有了 IoC 后，所依赖的对象直接由 IoC 容器创建后注入到被注入的对象中，依赖的对象由原来的主动获取变成被动接受，所以是反转。
4. **哪些方面反转了**：所依赖对象的获取被反转了。



- IOC Service Provider 为被注入对象提供被依赖对象也有如下几种方式：**构造器注入**、**setter 注入**、**接口注入**。



> [【死磕 Spring】----- IOC 之深入理解 Spring IoC](https://mp.weixin.qq.com/s/nCvZ9NbNQeD_FtJyho4owg)