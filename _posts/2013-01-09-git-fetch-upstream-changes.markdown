---
author: marknadig
comments: true
date: 2013-01-09 22:31:01+00:00
layout: post
slug: git-fetch-upstream-changes
title: Git fetch upstream changes
wordpress_id: 317
tags:
- git
- OSS
---

I have been trying to contribute where I can w/ the AngularJS project. The workflow is very well documented [here](http://docs.angularjs.org/misc/contribute).

As documented in this [post](http://gitready.com/intermediate/2009/02/12/easily-fetching-upstream-changes.html), you first need to create a remote known as 'upstream':

    
    git remote add upstream git://github.com/user/repo.git


Then run these commands to get the latest for master and upstream and merge into the current branch:

    
    git fetch origin -v; 
    git fetch upstream -v; 
    git merge upstream/master


The original post has a handy tip to put this in an alias.
