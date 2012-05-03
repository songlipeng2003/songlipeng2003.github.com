---
layout: post
title: "use capistrano to deploy"
date: 2012-04-25 13:09
comments: true
categories: ruby 
---
一直在寻找一个好的部署工具，以前用java的时候，经常过maven，ant，更多是用来构建，而不是部署。

前一段使用cakephp一直也想找一个这样的工具，也是没有找到。

开始学习RoR的开发，在ruby-china的代码中发现了[capistrano](https://github.com/capistrano/capistrano) 这个工具，看了一下介绍，感觉就是我理想中工具

支持多服务器，服务器重启，自定义任务，版本切换，版本管理工具支持，可以连接ssh，对服务器操作

而且还有很多第三方扩展：

[cakephp扩展-capcake](https://github.com/jadb/capcake)

[play扩展](http://www.playframework.org/modules/capistrano)


{% codeblock %}
ssh-keygen -p
cd ~/.ssh
cp id_rsa.pub authorized_keys
scp -p ~/.ssh/authorized_keys hrothgar:.ssh/
{% endcodeblock %}