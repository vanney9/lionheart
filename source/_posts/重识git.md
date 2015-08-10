title: 重识git
date: 2015-07-28 19:18:44
tags: git
categories: 杂七杂八
---

　　今天，在[coding.net](www.coding.net)上面，自己见了一个项目来熟悉git的基本操作。并没有用到github，主要使用的是coding.net来托管代码。
　　最主要的参考资料是阮一峰大神的一篇博客：[Git远程操作详解](http://www.ruanyifeng.com/blog/2014/06/git_remote.html)
　　下面对今天的一系列操作做个记录，以便以后使用。
<!-- more -->

#### 在coding.net上面新建项目 ####
1. 在coding.net上面添加ssh公钥
		$ cd ~/.ssh
    	$ ssh-keygen
将生成的id_rsa.pub复制，添加到coding.net，参考[ 将公钥部署到远程Git仓库（coding.net）](http://segmentfault.com/a/1190000002737818)
2. 新建项目

#### 本地拷贝远程仓库 ####
		$ git clone https://git.coding.net/xxx/xxx.git

#### 本地添加代码，并提交到coding ####
1. 在本地新建一个文档，(example:README.md)，由于远程仓库是空的，所以进行第一次提交时，需要执行：
		$ git add README.md
        $ git commit -m 'first commit'
        $ git push origin master #git push <远程主机名> <本地分支>:<远程分支>
这样就完成了第一次提交，也在本地和远端都建立了一个master分支
2. 将本地和远程的相同分支建立追踪：
		$ git branch --set-upstream-to=origin/master master
这样以后只需要执行：
		$ git pull OR git push
而不用执行如下繁琐命令：
		$ git pull <远程主机> <远程分支>:<本地分支> OR git push <远程主机> <本地分支>:<远程分支>
注意： 上述繁琐语句中的冒号后面的内容一般可以省略，因为远程分支和本地分支一般名字相同
3. 每次pull或是push是都需要输入username和密码，可以在.git文件夹下面修改config文件。
		url = https://[your username]:[your password]@git.coding.net/xxx/xxx.git

#### 新建分支 ####
*  在coding.net上面新建一个dev分支，与当前的master一致，在本地通过如下代码将其拷贝下来：
		$ git branch dev  //新建本地dev分支
        $ git checkout dev //切换到本地dev分支
        $ git pull origin dev //拷贝远程dev分支到本地dev分支
        $ git branch --set-upstream-to=origin/dev dev //建立dev分支追踪
通过这种方式实现本地dev分支和远端dev分支的同步；并且，由于建了追踪的原因，之后在dev分支下面的pull和push操作也只需要git pull和git push就行。



