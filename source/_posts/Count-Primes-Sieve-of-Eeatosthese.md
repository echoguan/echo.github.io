---
title: 计数质数 - 厄拉多塞筛法
categories: 技术
date: 2019-05-24 13:47:01
tags: [算法, LeetCode, Primes]
---

> 题目：204. 计数质数（统计所有小于非负整数 n 的质数的数量）

质数：又称素数，指在大于 1 的自然数中，除了1和该数自身外，无法被其他自然数整除的数。

### 思路一

#### 具体思路

- 遍历数字 n 是否能被从 2 到 sqrt(n) 之间的质数整除。

#### [代码（JAVA）](<https://github.com/echoguan/LeetCode/blob/master/src/com/echo/easy/_204/CountPrimes.java>) 

### 思路二：厄拉多塞筛法

#### 具体思路

- 先将 `2-n` 的各个数字放入表中。
- 在 2 的上面画一个圆圈；然后划去其它所有 2 的倍数的数字。
- 接下来第一个未画圈又没有被划去的数字是 3，将它画圈；然后再划去 3 的倍数。
- 接下来第一个未画圈又没有被划去的数字是 5，将它画圈；然后再划去 5 的倍数。
- ...... 以此类推；直到所有小于或者等于 n 的数字都被画圈或者划掉为止。
  - 其实，当你要画圈的数字的平方大于 n 时，那么后面没有被划掉的数字都是质数，不需要继续往后判断了。
- 这时表中所有画了圈和未被划去的数字就是小于等于 n 的质数。

#### 图示

![iterm2](/images/Sieve_of_Eratosthenes_animation.gif)   

#### [代码（JAVA）](<https://github.com/echoguan/LeetCode/blob/master/src/com/echo/easy/_204/CountPrimesEeatosthese.java>) 

### 思路比较

- 思路一比较容易想到，但思路二效率会高很多。

> REFERENCES
>
> - [__Daniel - 厄拉多塞筛法](<https://blog.csdn.net/u013291076/article/details/45575967>)