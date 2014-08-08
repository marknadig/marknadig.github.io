---
author: marknadig
comments: true
date: 2012-05-01 20:42:06+00:00
layout: post
slug: simple-web-server-on-osx
title: Simple web server on OSx
wordpress_id: 124
tags:
- OS X
---

Today, needed to spin up a simple web server to test out a demo for a js microframework  (nod [http://collectiveidea.com/blog/archives/2012/04/01/walken-on-rails/](http://collectiveidea.com/blog/archives/2012/04/01/walken-on-rails/)). OSx comes w/ Apache, but that seemed  a bit overkill. Found this [http://www.macworld.com/article/1140370/pythonserver.html](http://www.macworld.com/article/1140370/pythonserver.html) today.

python -m SimpleHTTPServer

Will spin up a... simple http server :)... default port is 8000 and can be overridden by adding a parameter to the end.

Here's a write up on configuring apache on Osx. [http://en.wikibooks.org/wiki/Mac_OS_X_Tiger/Using_your_Mac_as_a_Web_Server](http://en.wikibooks.org/wiki/Mac_OS_X_Tiger/Using_your_Mac_as_a_Web_Server)
