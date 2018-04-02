---
title: git stash 备忘录
categories: 技术
date: 2018-04-02 11:05:33
tags: git
---

- `git stash`可以用来暂存当前正在进行中的工作。
  - 比如想`pull`新的代码，但暂时不想加新的`commit`
  - 比如为了 fix 一个紧急的 bug，先`stash`，回到上一个`commit`的代码，改完之后再`git stash pop`，继续原来的工作。

- 常用命令：
  - `git stash` - save uncommitted changes
    - `git stash save "work in progress for A feature"`
  - `git stash pop` - apply last stash and remove it from the list
    - `git stash apply stash@{1}`
  - `git stash list` - list stashed changes in this git
  - `git stash --help`
  - `git show stash@{0}` - show the last stash
