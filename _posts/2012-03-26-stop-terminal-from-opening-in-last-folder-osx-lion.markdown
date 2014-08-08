---
author: marknadig
comments: true
date: 2012-03-26 14:55:15+00:00
layout: post
slug: stop-terminal-from-opening-in-last-folder-osx-lion
title: 'Stop terminal from opening in last folder - OSx Lion '
wordpress_id: 118
tags:
- OS X
---

Lion has a new 'resume' feature that will open applications in the same state they were in. I found this particularly annoying w/ Terminal as cd'ing into my source folder was bypassing my rvm hooks. Initially I turned off the resume feature system-wide: [http://www.macrumors.com/2011/07/20/how-to-disable-lions-resume-feature/](http://www.macrumors.com/2011/07/20/how-to-disable-lions-resume-feature/). However, it still would open in the last folder :/... This morning I found the way to disable resume on a per-application basis [http://osxdaily.com/2011/08/01/turn-off-resume-per-app-in-mac-os-x-lion/](http://osxdaily.com/2011/08/01/turn-off-resume-per-app-in-mac-os-x-lion/)

`defaults write com.apple.Terminal NSQuitAlwaysKeepsWindows -bool false`

