---
author: marknadig
comments: true
date: 2013-07-26 17:10:10+00:00
layout: post
slug: mountain-lion-git-command-not-found
title: 'Mountain Lion - git “Command Not Found” '
wordpress_id: 491
tags:
- git
- OS X
---

Upgraded to OSx 10.8.4 (Mountain Lion) this morning and after the 2 reboots, started up terminal to get to work and

    
        $ git checkout -b workingbranch
        -bash: git: command not found


bah!  Thankfully, internets to the rescue and this [post](http://www.hongkiat.com/blog/mountain-lion-git-fix/) pointed me to 1. install XCode (already installed) and 2. install command line tools from XCode (FTW).
