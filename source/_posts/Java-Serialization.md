---
title: Java 序列化
categories: 技术
date: 2019-05-27 15:07:47
tags: [Java, Serialization, 序列化]
---

> 序列化是一种 **对象** 持久化的手段。普遍应用在网络传输、RMI（远程方法调用）等场景中。

本篇主要会涉及以下几个方面：

> - 序列化与反序列化
> - Java 对象的序列化与反序列化
>   - 用途
>   - 示例代码
> - 相关接口与类
> - `Transient` 关键字
> - 序列化 ID `SerialVersionUID` 

### 序列化与反序列化 

- 序列化（Serialization）是指，将 **对象的状态信息** 转化为 **可以存储或传输的形式** 的过程。
- 与上述相反的过程称为反序列化。

### Java 对象的序列化与反序列化

- Java 平台允许我们在内存中创建可以复用的 Java 对象，但一般情况下，只有当 JVM 处于运行状态时，这些对象才存在。
- 而在实际应用中，就可能要求在 JVM 停止运行之后仍然能够保存（持久化）指定的对象，并在将来重新读取被保存的对象。
- Java 的对象序列化就是为了方便我们实现该功能。

#### 序列化的用途

- 想把内存中的 **对象状态** ，保存到一个 **文件或者数据库** 中的时候。
- 想把对象 **通过网络进行传播** 的时候。

#### 示例代码

如何对 Java 对象进行序列化和反序列化？

- 在 Java 中只要一个类实现了 `java.io.Serializable` 接口，那么它就可以被序列化。（[该接口并没有方法和字段，为什么只有实现了该接口的类的对象才能被序列化呢？](http://www.hollischuang.com/archives/1140#What Serializable Did)）
- 当试图对一个对象进行序列化时，如果遇到了没有实现 Serializable 接口的对象。就会抛出 `NotSerializableException` 异常。
- 如果要序列化的对象的类有父类，并且想要同时将在父类中定义过的变量持久化下来。那么父类也要实现 `java.io.Serializable` 接口。

### 相关接口与类

- `java.io.Serializable` 
- `java.io.Externalizable` 
- `ObjectOutput` 
- `ObjectInput` 
- `ObjectOutputStream` 
- `ObjectInputStream` 



> WIP
>
> <https://www.hollischuang.com/archives/1140>
>
> <https://www.hollischuang.com/archives/1150>
>
> <https://www.hollischuang.com/archives/1144>
>
> <http://www.hollischuang.com/archives/205>
>
> <http://blademastercoder.github.io/2015/01/29/java-Serializable.html>
>
> <https://www.runoob.com/java/java-serialization.html>





> REFERENCES
>
> - [hollis - 深入分析 Java 的序列化与反序列化](https://www.hollischuang.com/archives/1140) 
> - [hollis - Java 对象的序列化与反序列化](https://www.hollischuang.com/archives/1150) 