---
author: marknadig
comments: true
date: 2012-06-27 16:33:29+00:00
layout: post
slug: sublime-text-2-preferences
title: Sublime Text 2 preferences
wordpress_id: 202
categories:
- Coding
---

Preferences.sublime-settings

    
    {
     "save_on_focus_lost": true,
     "tab_size": 2,
     "translate_tabs_to_spaces": true
    }


Default (OSX).sublime-keymap

    
    [
    // open anything
    { "keys": ["super+shift+n"], "command": "show_overlay", "args": {"overlay": "goto", "show_files": true}}, 
    // reveal in sidebar
    { "keys": ["alt+f1"], "command": "reveal_in_side_bar" }, 
    // goto line
    { "keys": ["super+l"], "command": "show_overlay", "args": {"overlay": "goto", "text": ":"} }
    ]


more
