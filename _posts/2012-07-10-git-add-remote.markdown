---
author: marknadig
comments: true
date: 2012-07-10 21:01:43+00:00
layout: post
slug: git-add-remote
title: git add remote
wordpress_id: 220
categories:
- git
---

A few times I've cloned a github repo and while local started tinkering. Now, I want to save my changes, but I can't push them up to origin. So, first I fork the repo and add my fork as a remote. I can now push my changes up there.

    
    git remote add [name] [uri]
    e.g.
     git remote add github git@github.com:digger69/pusher-phonegap-android.git


Then do this to pull down the branches from the new remote

    
    git fetch


And you can now push here

    
    git push github master
