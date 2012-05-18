---
layout: post
title: "install rmagick fail on macbook lion"
date: 2012-05-18 17:59
comments: true
categories: ruby
---
错误信息

```
$ gem install rmagick
Buildingnative extensions.  This could take a while...ERROR:  Error installing rmagick:        ERROR:Failed to build gem native extension.        /Users/dhiemstra/.rvm/rubies/ruby-1.9.3-head/bin/ruby extconf.rb
checking forRuby version >=1.8.5... yes
extconf.rb:128:UseRbConfig instead of obsolete and deprecated Config.checking for clang... yes
checking forMagick-config... yes
checking forImageMagick version >=6.4.9... yes
checking for HDRI disabled version of ImageMagick... yes
checking for stdint.h...*** extconf.rb failed ***Couldnot create Makefile due to some reason, probably lack of
necessary libraries and/or headers.  Check the mkmf.log file for more
details.  You may need configuration options.Provided configuration options:        --with-opt-dir
        --without-opt-dir
        --with-opt-include
        --without-opt-include=${opt-dir}/include
        --with-opt-lib
        --without-opt-lib=${opt-dir}/lib
        --with-make-prog
        --without-make-prog
        --srcdir=.        --curdir
        --ruby=/Users/dhiemstra/.rvm/rubies/ruby-1.9.3-head/bin/ruby
/Users/dhiemstra/.rvm/rubies/ruby-1.9.3-head/lib/ruby/1.9.1/mkmf.rb:381:in`try_do': The compiler failed to generate an executable file. (RuntimeError)
```

需要卸载了，重新安装

```
brew uninstall imagemagick
brew install imagemagick --disable-openmp
```