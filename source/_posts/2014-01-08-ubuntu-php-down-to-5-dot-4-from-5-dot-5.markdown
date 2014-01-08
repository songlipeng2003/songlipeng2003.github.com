---
layout: post
title: "ubuntu php down to 5.4 from 5.5"
date: 2014-01-08 22:14:52 +0800
comments: true
categories: ubuntu php
---

http://superuser.com/questions/662824/downgrade-php-from-5-5-3-to-5-4-x-in-ubuntu-13-10

```
# upgrade system, so you can add to ignore all updates later
sudo apt-get update
sudo apt-get upgrade

# remove your php, apache, etc
sudo apt-get purge apache2 php5 libapache2-mod-php5 # add here your server packages

# change repositories to raring  (with backup)
sudo sed -i.bak "s/saucy/raring/g" /etc/apt/sources.list

# update and install server packages
sudo apt-get update
sudo apt-get install apache2 php5 libapache2-mod-php5 phpmyadmin #add here packages you need and make sure you install php5.4 and apache2.2

# change repositories back to saucy
sudo sed -i "s/raring/saucy/g" /etc/apt/sources.list

# ignore all current upgrades (package hold)
sudo apt-mark hold `aptitude -F%p --disable-columns search ~U` 
```