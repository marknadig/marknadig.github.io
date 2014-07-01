---
author: marknadig
comments: true
date: 2010-12-08 00:23:03+00:00
layout: post
slug: visual-studio-showing-all-projects-are-checked-out
title: Visual Studio showing all projects are checked out!??
wordpress_id: 44
categories:
- TFS
---

Since last week, Visual Studio started showing that all the projects in my solution were checked out by someone else, or somewhere else. Opening Source Control Explorer confirmed they weren't. Turns out this is a known bug:

[http://blogs.infosupport.com/blogs/marcelv/archive/2007/12/03/Team-Foundation-Server-2008-shows-incorrect-version-control-status-in-team-explorer-.aspx](http://blogs.infosupport.com/blogs/marcelv/archive/2007/12/03/Team-Foundation-Server-2008-shows-incorrect-version-control-status-in-team-explorer-.aspx)

I had a shelveset that had all the projects checked out (for VS2010 migration) and this was tripping up VS/TFS.

**Category:** TFS

**Published:** 12/7/2010 7:20 PM

