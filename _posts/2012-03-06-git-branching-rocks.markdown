---
author: marknadig
comments: true
date: 2012-03-06 19:54:38+00:00
layout: post
slug: git-branching-rocks
title: git branching rocks
wordpress_id: 81
tags:
- git
---

# Why Git Rocks


Today, I'm 4 hours into a feature 'myfeat' for the current iteration when "the phone rings" (skype). PM has a customer reporting an issue on latest production code.

    
    git stash
    git checkout production


Now I'm looking at the production codez, can run and repro the issue. Create a topic branch off of production to hold my fix (so I can merge into both production and master):

    
    git checkout -b myfix


Now I write a failing test for the feature (TDD!). Fix the code and confirm the test passes. Time to make this available for deploy.

    
    git checkout production
    git merge myfix 
    git push origin production


Now merge hotfix back into master branch.

    
    git checkout master
    git merge myfix # master branch now all happy with hotfix
    
    # run tests again before push since master != production
    git put origin master 
    
    git checkout myfeat
    git stash apply # get my stashed changes back


back to work. As my friend Arthur would say 'mo-ney'
