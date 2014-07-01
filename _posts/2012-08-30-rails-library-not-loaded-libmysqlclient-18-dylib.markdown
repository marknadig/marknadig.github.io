---
author: marknadig
comments: true
date: 2012-08-30 03:02:58+00:00
layout: post
slug: rails-library-not-loaded-libmysqlclient-18-dylib
title: 'Rails - Library not loaded: libmysqlclient.18.dylib'
wordpress_id: 238
categories:
- OS X
- Ruby on Rails
---

After [switching](http://blog.nadigs.net/mark/2012/08/29/going-from-macports-to-homebrew/) from MacPorts to Homebrew (and re-isntalling mysql) I was getting an error running my rails server:

    
    .../gems/mysql2-0.3.11/lib/mysql2/mysql2.bundle, 9): Library not loaded: libmysqlclient.18.dylib (LoadError)


Per [StackOverflow](http://stackoverflow.com/questions/4546698/library-not-loaded-libmysqlclient-16-dylib-error-when-trying-to-run-rails-serv) was a simple fix:

    
    ln -s /usr/local/mysql/lib/libmysqlclient.18.dylib /usr/lib/libmysqlclient.18.dylib


Oh, also had to update database.yml to point to /tmp/mysql.sock from /opt/local.var/run/mysql5/mysqld.sock
