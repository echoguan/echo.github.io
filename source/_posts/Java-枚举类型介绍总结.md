---
title: Java - 枚举类型介绍总结
categories: 技术
date: 2018-10-14 21:18:14
tags:
   - Interview
   - 枚举类型
---



- 枚举类型（`enum type`）是指由一组固定的常量组成合法的类型。

  ```java
  public enum Season {
      SPRING, SUMMER, AUTUMN, WINTER;
  }
  ```


- 特点：

  - 使用关键字`enum` 
  - 类型名称，如`Season` 
  - 一串允许的值（`SPRING, SUMMER, AUTUMN, WINTER`）
  - 枚举可以单独定义在一个文件中，也可以嵌在其它 `Java类` 中。
  - `枚举类型` 可以实现一个或多个接口
  - 可以定义新的变量
  - 可以定义新的方法
  - 可以定义根据具体枚举值而相异的类

- 应用举例：

  > [Hollis - Java的枚举类型用法介绍](http://www.hollischuang.com/archives/195) 

