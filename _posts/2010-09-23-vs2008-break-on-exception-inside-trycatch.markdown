---
author: marknadig
comments: true
date: 2010-09-23 22:29:42+00:00
layout: post
slug: vs2008-break-on-exception-inside-trycatch
title: VS2008 break on exception inside try/catch
wordpress_id: 57
tags:
- Work
---

(I always forget this... writing down where I won't)

Ctrl-Alt-E to bring up the exceptions window and tick the **Thrown** checkbox on Common Language Runtime Exceptions

That will stop the execution, open the source code where the exception was thrown, and tell you with a message window what error it is, pointing at the line it was thrown.
