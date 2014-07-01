---
author: marknadig
comments: true
date: 2013-12-17 01:17:20+00:00
layout: post
slug: git-cherry-pick-from-remote-branch
title: Git cherry pick from remote branch
wordpress_id: 659
categories:
- git
---

I wanted to pull in a specific [PR](https://github.com/dustacio/ri_cal/commit/c25430e3defbf100529335cbc25a20a762327717) from a repo that is no longer maintained into my fork.

Local repo is KonaTeam/ri_cal and PR was https://github.com/dustacio/ri_cal/.

`
$ git remote add dustacio https://github.com/dustacio/ri_cal/
$ git fetch dustacio
$ git cherry-pick -c c25430e3defbf1005
$ # resolve any conflicts and commit
`

source:[ http://www.miek.nl/blog/archives/2011/12/13/cherry-picking_remote_branches/index.html](http://www.miek.nl/blog/archives/2011/12/13/cherry-picking_remote_branches/index.html)
