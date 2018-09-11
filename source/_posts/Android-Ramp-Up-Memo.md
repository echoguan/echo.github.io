---
title: Android Ramp Up Memo
categories: 技术
date: 2018-09-11 10:40:21
tags:
---

#### MVP Pattern

- Model-View-Presenter
- 是由 `MVC` 演变而来。在 `MVP` 中：
  - `View` 更加专注于处理数据可视化和页面交互
  - `Model` 更加专注于数据的处理
  - `Presenter` 则提供 `View` 和 `Model` 之间数据的纽带，用于交互和数据传输
- **`View`不直接与`Model`交互**

> [MVP 设计模式理解，实战理解MVP](https://blog.csdn.net/u011418943/article/details/69840880)
>
> [Android MVP 详解（上）](https://www.jianshu.com/p/9a6845b26856)



#### RxJava/RxAndroid

- `RxJava` 的本质可以压缩为**异步**这一个词。说到根上，它就是一个实现异步操作的库，而别的定语都是基于这之上的。

- 优势：**简洁**

- `RxJava` 的异步实现，是通过一种扩展的**观察者模式**来实现的。

- `RxJava` 有四个基本概念：**Observable** (可观察者，即被观察者)、 **Observer** (观察者)、**subscribe** (订阅)、**事件**。

- `RxJava` 的观察者模式大致如下图：

  ![img](https://upload-images.jianshu.io/upload_images/2405826-1b43cf8a80bfca3f.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/599/format/webp)

> [Rxjava、RxAndroid系列](https://www.jianshu.com/p/10d4d7c69345)



#### Retrofit

- `Retrofit` 是 Square 的一个著名的**网络请求库**。
- `Retrofit` 除了提供了传统的 Callback 形式的 `API`，还有 `RxJava` 版本的 Observable 形式 `API`。



#### Robolectric



#### Android

- `Activity`