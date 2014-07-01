---
author: marknadig
comments: true
date: 2013-03-01 16:23:34+00:00
layout: post
slug: global-gitignore-for-ide-specific-ignores
title: Global .gitignore for IDE specific exclusions
wordpress_id: 332
categories:
- git
---

I work in a team with disperate IDEs. So, when we start a new project, each of us ends up adding our IDE specifics to the project's .gitignore; e.g. for WebStorm, RubyMine:

    
    .idea/


For sublime text 2:

    
    /*.sublime-project
    *.sublime-workspace


Not a big deal, but a bit tiresome. I also found myself adding these as step 1 of submitting a PR to an OSS project. This is bad because it muddies the .gitignore. Thankfully, on a  recent PR a maintainer clued me into global gitignore. Read up on them on [github](https://help.github.com/articles/ignoring-files). But it works just like you'd imagine, I can add my IDE specific excludes to _my_ global gitignore and never have to muddy another project's .gitignore again.
