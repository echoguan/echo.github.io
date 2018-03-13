---
title: Hexo+GitHub基本安装与部署
categories: 技术
tags:
  - hexo
  - blog
date: 2017-10-18 22:34:31
---

> 使用Hexo+GitHub搭建个人博客（免费+方便）

## 一、安装Hexo
#### 安装前提
1. Node.js
2. Git

#### QuickStart

<!--more-->

- 使用`npm`安装Hexo: `npm install -g hexo`
- 安装完成后，在你想要放置个人博客文件的目录下（例如`E:\Hexo`），执行`hexo init`
- 安装依赖包：在`E:\Hexo`下，执行命令`npm install`。这样Hexo博客就搭好了。
- 接下来在本地预览一下博客吧。在博客目录（`E:\Hexo`）下执行

```
  hexo g
  hexo s
```

- 然后就可以访问 http://localhost:4000/ ，在本地看到你的博客了，当然别人是看不到的，所以接下来需要部署到GitHub上。

#### Hexo常见命令
	hexo g/generate	#生成静态文件  
	hexo s/server	#启动服务器，可本地预览
	hexo d/deploy	#将本地文件发布到服务器上(github/Coding)
	hexo n/new	#新建文章
	hexo h/help	#查看帮助


## 二、创建对应GitHub Pages仓库
- 在GitHub上创建一个新的仓库，用于存放Hexo博客，命名必须为**username.github.io**（username是你GitHub账号名)
- 编辑`E:\Hexo`下的`_config.yml`文件，添加或修改如下配置

```
# Deployment
## Docs: https://hexo.io/docs/deployment.html
deploy:
  type: git
  repo: Repository的SSH地址（可从GitHub相应Repository复制。eg:https://github.com/echoguan/echoguan.github.io.git,master）
  branch: master
```

> Tips:
> * .yml配置文件中任何':'后面都必须空一个空格。
> * GitHub没有配置过SSH的，可能需要配置下。

- 安装hexo-deployer-git这个模块

```
npm install hexo-deployer-git --save
```

- 执行以下命令完成部署

```
hexo g
hexo d
```

- 之后访问username.github.io，就可以看到你的博客啦

## Hexo简单写作
### 发表一篇文章
- 执行下列命令生成新文章

```
$ hexo new "新文章"
```

- 关于草稿

```
$ hexo new draft "新草稿"	#生成一篇新草稿，默认不会发布
$ hexo publish "草稿名"	#发布草稿
```

> 参考
> * 嘟嘟MD - [hexo干货系列：（一）hexo+gitHub搭建个人独立博客](http://tengj.top/2016/02/22/hexo1/)
> * CrazyMilk - [GitHub Pages + Hexo搭建博客](http://crazymilk.github.io/2015/12/28/GitHub-Pages-Hexo%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2/)
