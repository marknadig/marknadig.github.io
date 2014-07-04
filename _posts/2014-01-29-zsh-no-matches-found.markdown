---
author: marknadig
comments: true
date: 2014-01-29 00:01:22+00:00
layout: post
slug: zsh-no-matches-found
title: 'zsh: no matches found:...'
wordpress_id: 705
categories:
- zsh
---

I've been on zshell (via oh-my-zsh) for some time and have loved most of it. One of my nits was 'no matches found' when running various rake tasks; e.g.

    
    $ rake parallel:spec[4]
    > zsh: no matches found: parallel:spec[4]


I was a bit fuddled on the root cause, but today I found the solution and the cause. The root cause was zshell's substitutions http://zsh.sourceforge.net/Guide/zshguide05.html and the solution was to add

    
    alias rake="noglob rake"


to my ~/.zshrc


