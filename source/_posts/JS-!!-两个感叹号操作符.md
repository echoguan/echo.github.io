---
title: JS !! 两个感叹号操作符
categories: 技术
date: 2019-08-07 13:42:56
tags: [Java, Serialization, 序列化]
---

### 作用 

- 把一个元素转换为**其对应真正的布尔值** ，一般用来判断某个元素是否存在。

```javascript
// base:
!true = false;
!!true = true;

// extend:
  
!!"0" = true;
!!1 = true;

!!0 = false; 
!!"" = false; 
!!undefined = false;   
!!null = false; 
var a;  !!a = false;   
```

