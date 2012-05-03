---
layout: post
title: "attr attr_accessor attr_accessible attr_protected"
date: 2012-05-02 21:39
comments: true
categories: ruby
---

attr_accessor是Ruby提供的方法，相当于帮你生产读写方法，同时兼备 attr_reader attr_writer 的作用

attr_reader 相当于生产读方法

attr_writer 相当于生产写方法

attr 只能带一个符号参数，第二个参数是一个 bool 参数，用于指示是否为头一个符号参数产生写方法。它的默认值是 false , 不产生写方法。

attr_accessible是rals的提供的方法，指的是能某些字段可以通过前端来赋值

attr_protected是rals的提供的方法，作用恰好和attr_accessible相反，指定某些字段不能够前端来赋值