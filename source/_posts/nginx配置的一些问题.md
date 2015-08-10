title: nginx配置的一些问题
date: 2015-08-03 14:59:08
tags: [nginx, ci]
categories: 杂七杂八
---
今天小学弟问了些关于nginx和ci配置的问题，主要就是去掉index.php后可以正常访问，但是加上index.php后居然不能正常访问，而且重定向到了welcome/index页面，最后的最后，还是小学弟找到了解决方法=.=

<!-- more -->

先上链接
1. [http://blog.sina.com.cn/s/blog_48d40b7a0100saqh.html](http://blog.sina.com.cn/s/blog_48d40b7a0100saqh.html)
2. [http://www.chenyudong.com/archives/codeigniter-in-nginx-and-url-rewrite.html](http://www.chenyudong.com/archives/codeigniter-in-nginx-and-url-rewrite.html)
3. [http://blog.csdn.net/ei__nino/article/details/8599304](http://blog.csdn.net/ei__nino/article/details/8599304)

目前还不知道什么原因，先看看前后nginx配置的不同
先前的配置：
<img src="/images/lionheart/nginx_conf_old.png"/>
后来的配置：
<img src="/images/lionheart/nginx_conf_new.png"/>

但是为什么要这样配置呢... 还不清楚
