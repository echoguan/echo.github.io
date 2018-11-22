---
title: Blog - hexo + yilia 博客访问量统计显示
categories: 技术
date: 2018-11-12 15:06:18
tags: hexo
---



#### 1. 网站访问量显示 

- 效果

  - 见博客底部

- 实现

  - 使用 **[不蒜子](http://ibruce.info/)** ，可以看官方介绍。

  - 在 `themes/yilia/layout/_partial/footer.ejs` 中加入如下代码：

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



#### 2. 网站 IP 访问量显示(友盟) 

- 使用[友盟](http://www.umeng.com/) 

- 首先注册一个帐号->进入个人中心->展开全部产品->选择**U-Web网站统计**->点击**立即使用**->**添加站点**

- 然后在`站点设置` 里选择`获取代码` ，我这里选择的是 `横排数据显示` 。

- 然后把自己的代码加到 `footer.ejs` 中

- 可在`友盟`上查看最近的**访问量**和**数据** 。


#### 3. 文章访问量统计 

- 下面这段代码添加在`/themes/yilia/layout/_partial/article.ejs` 的header的日期后面：

```ejs
// 添加判断，如果首页则不显示访问量
<% if ( !index ){ %>
    <span class="archive-article-date">
        阅读量 <span id="busuanzi_value_page_pv"></span>
    </span>
<% } %>
```





> [Hexo + yilia 搭建博客可能会遇到的所有疑问](https://meetes.top/2018/01/31/Hexo%20+%20yilia%20%E6%90%AD%E5%BB%BA%E5%8D%9A%E5%AE%A2%E5%8F%AF%E8%83%BD%E4%BC%9A%E9%81%87%E5%88%B0%E7%9A%84%E6%89%80%E6%9C%89%E7%96%91%E9%97%AE/) 
>
> [hexo yilia主题添加文章访问量统计](http://www.lookk.cn/2017/12/09/hexo-yilia%E4%B8%BB%E9%A2%98%E6%B7%BB%E5%8A%A0%E6%96%87%E7%AB%A0%E8%AE%BF%E9%97%AE%E9%87%8F%E7%BB%9F%E8%AE%A1/) 