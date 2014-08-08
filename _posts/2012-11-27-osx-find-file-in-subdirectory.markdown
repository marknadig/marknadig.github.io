---
author: marknadig
comments: true
date: 2012-11-27 18:42:43+00:00
layout: post
slug: osx-find-file-in-subdirectory
title: OSx find file in subdirectory
wordpress_id: 283
tags:
- OS X
---

Love SO/superuser - writing the answer down here... How in OSx can you find files in sub-folders based on filename; e.g. for DOS

    
    DIR *.mp3 /s
    DIR \path\to\search\*.mp3 /s


OSx terminal (bash):

    
    find . -name *.mp3 
    find /path/to/search -name *.mp3


man page [here](http://ss64.com/osx/find.html) and on [Apple developer](https://developer.apple.com/library/mac/#documentation/Darwin/Reference/ManPages/man1/find.1.html).


