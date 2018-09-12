---
title: 'JDK,JRE,JVM简介'
categories: 技术
date: 2018-09-09 14:01:59
tags:
  - JDK
  - JRE
  - JVM
---

#### JDK(Java Development ToolKit) - Java 开发工具包

- `JDK` 是整个 Java 的**核心**。
- 包括：
  - **JRE** - Java 运行环境
  - **Java API** - Java 基础的**类库**
  - 一堆` Java 工具`（javac/java/jdb等）



#### JRE(Java Runtime Environment) - Java 运行时环境

- 所有的 Java 程序都必须在 `JRE` 下才能**运行**。

- 包括：
  - JVM
  - Java 核心类库
  - 支持文件



#### JVM(Java Virtual Mechinal) - Java 虚拟机

- `JVM` 是 `JRE` 的一部分。
- 它是一个虚构出来的计算机。
- `JVM` 有自己完善的硬件架构，如处理器、堆栈、寄存器等，还具有相应的指令系统。
- `JVM` 的主要工作是，解释自己的编码集，并映射到本地 CPU 的指令集或 OS 的系统调用。
- Java 语言的跨平台特性，其实就是不同的操作系统，使用不同的 JVM 映射规则。



![JDK JRE JVM 关系](../../images/JDKJREJVM关系.gif)