---
layout: post
title: "git revert and reset"
date: 2012-04-28 11:44
comments: true
categories: git
---
git revert 是撤销某次操作，此次操作之前的commit都会被保留

git reset 是撤销某次提交，但是此次之后的修改都会被退回到暂存区

Git的一些常用的撤销提交版本的的命令：

{% codeblock%}
git revert HEAD                ＃撤销前一次 commit
git revert HEAD^               ＃撤销前前一次 commit
＃撤销指定的版本，撤销也会作为一次提交进行保存。
git revert commit 7de3c367b8ee77e27371f8f6761b8f5909fcce43 
{% endcodeblock %}


**相关内容**

[Git Community Book](http://book.git-scm.com/4_undoing_in_git_-_reset,_checkout_and_revert.html)

[非常好的git - 简易指南](http://rogerdudler.github.com/git-guide/index.zh.html)

[Git revert 撤销某个提交版本](http://blog.microsuncn.com/?p=1559)
