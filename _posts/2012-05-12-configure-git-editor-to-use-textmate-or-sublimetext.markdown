---
author: marknadig
comments: true
date: 2012-05-12 18:39:36+00:00
layout: post
slug: configure-git-editor-to-use-textmate-or-sublimetext
title: Configure git editor to use TextMate or SublimeText
wordpress_id: 162
tags:
- git
---

To configure either of these for git commit message windows

SublimeText

    
    git config --global core.editor "subl -w -n"

TextMate

    
    git config --global core.editor "mate -w"

