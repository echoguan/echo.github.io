---
title: Issue - 部署到Github Pages不生效的解决方法
categories: 技术
tags:
  - hexo
  - blog
  - issue
date: 2017-10-19 14:14:06
---
# 部署之后，页面不生效

### issue描述：
修改博客之后，页面文件没有更新，页面不生效

### 解决方案
Please run these commands before hexo deploy:
```
$ hexo clean  #清除缓存
$ rm -r -f .deploy_git
```
