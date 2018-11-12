---
title: Blog - hexo + yilia 博客访问量统计显示
categories: 技术
date: 2018-11-12 15:06:18
tags: hexo
---



#### 网站访问量显示 

- 效果

  - 图1

- 实现

  - 使用 **[不蒜子](http://ibruce.info/)** ，可以看官方介绍。

  - 在 `themes/yilia/layout/_partial/footer.ejs` 中加入如下代码：

    - 图2

  - ```js
    <!-- 根据个人喜好在相应位置添加以下代码 -->
    <div calss="count-span">
        <span id="busuanzi_container_site_pv">
        总访问量: <span id="busuanzi_value_site_pv"></span>|
        </span>
        <span id="busuanzi_container_site_uv">
        总访客: <span id="busuanzi_value_site_uv"></span>
        </span>
    </div>
    <!-- 根据个人喜好在相应位置添加以上代码 -->
    
    <script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
    ```

  - 然后重新部署发布博客即可。


