---
title: Java - equals() 和 hashCode() 方法
categories: 技术
date: 2018-11-23 14:53:22
tags: Java
---



>



### `hashCode()` 和 `equals()` 方法的作用？什么时候必须重写？

- `equals(Object obj)` 方法用来判断两个对象是否相等。
  - Indicates whether some other object is "equal to" this one.
- `hashCode()` 方法用来返回对象的哈希码。(哈希码作用是确定该对象在散列存储结构中的存储位置)
  - Returns a hash code value for the object.
- 这两个方法的规范：
  - 如果两个对象相同，`equals()` 方法一定返回`true` ，并且这两个对象的`hashCode()` 相同。
  - 如果两个对象的`hashCode()` 相同，不代表两个对象就相同。只能说明这两个对象在散列存储结构中，存放在同一个位置。

