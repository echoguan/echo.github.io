---
title: 学习备忘 Tips
categories: 技术
date: 2019-04-22 08:47:29
tags:
---

#### Node.js

- TLS - Transport Layer Security(传输层安全协议)
  - 其前身是SSL(Secure Sockets Layer, 安全套接层)
  - 目的是为互联网通信提供安全及数据完整性保障。



#### Node.js ES6/CommonJS Module 模块机制

- exports 和 module.exports 的区别了：
  - module.exports 初始值为一个空对象 {}
  - exports 是指向的 module.exports 的引用
  - require() 返回的是 module.exports 而不是 exports



- [CommonJS是什么？](https://www.jianshu.com/p/0bd1ae24152d) 
- [Node 9下import/export的丝般顺滑使用](https://cnodejs.org/topic/5a0f2da5f9de6bb0542f090b) 
- [CommonJS规范](http://javascript.ruanyifeng.com/nodejs/module.html) 
- [Module 的加载实现](http://es6.ruanyifeng.com/#docs/module-loader) 



#### [JavaScript：变量提升和函数提升](https://www.cnblogs.com/liuhe688/p/5891273.html)

