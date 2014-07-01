---
author: marknadig
comments: true
date: 2010-11-02 18:58:08+00:00
layout: post
slug: case-insensitive-in-sqldeveloper
title: Case insensitive in SQLDeveloper
wordpress_id: 50
categories:
- Oracle
---

Rather than typing 


ALTER SESSION SET NLS_COMP = LINGUISTIC;  
ALTER SESSION SET NLS_SORT = BINARY_CI;


For every new worksheet in SQLDeveloper, you can set this as the default under Preferences: Database: NLS for both Sort and Comparison:


![](/images/broken_image.jpg)
