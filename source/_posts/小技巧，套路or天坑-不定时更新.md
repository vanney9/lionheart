title: 小技巧，套路or天坑...不定时更新
date: 2015-08-06 11:22:05
tags: detail
categories: 心得
---
####记录下一些小技巧或是走过的坑...####

<!-- more -->

1. 运用apt-cache搜索不知全名的包
比如你要apt-get安装一个貌似叫做libmemcache什么的包的时候，可以通过一下命令搜索：
		sudo apt-cache search libmemcache | grep memcache
于是就会出现下面的结果：
<img src="/images/lionheart/apt-cache.png"/>
图中的libmemcached-dev或许就会是你要的结果。
