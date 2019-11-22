---
title: 冒泡排序（Bubble Sort）
categories: 技术
date: 2019-05-17 11:01:46
tags: [算法, 排序, 冒泡]
---

### 算法步骤（从小到大）

- 比较相邻两个元素，如果前一个比后一个大，就交换它们。
- 从最后的元素开始，对每一对相邻元素做同样的工作，从最后一对到开头第一对。之后最前面的元素是最小的数。

- 重复上一步，除了已经排好的最小的数。

### 动画演示

![iterm2](/images/Bubble-Sort.gif)  

动画出自 五分钟学算法 公众号，链接见最后引用。

### [代码实现（JAVA）](<https://github.com/echoguan/LeetCode/blob/master/src/com/echo/sort/BubbleSort.java>) 

### 复杂度

* Time complexity: O(n^2)
* Space complexity: O(1)



> REFERENCES
>
> - [五分钟学算法 - 十大经典排序算法动画与解析，看我就够了！（配代码完全版）](<https://mp.weixin.qq.com/s/vn3KiV-ez79FmbZ36SX9lg>) 