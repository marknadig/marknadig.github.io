---
author: marknadig
comments: true
date: 2012-07-12 16:18:22+00:00
layout: post
slug: diffmerge-as-git-mergetool
title: DiffMerge as git mergetool
wordpress_id: 225
categories:
- git
---

In my other [post](http://blog.nadigs.net/mark/2012/05/02/osx-file-compare/) discussed various file compare options for OSx.  Currently I'm trying to configure git to use diffmerge as its merge tool. First step is to add diffmerge to the path. Download dmg and run this from that (from the diffmerge readme):

    
    sudo cp Extras/diffmerge.sh /usr/bin/diffmerge
     sudo chmod 755 /usr/bin/diffmerge
     sudo cp Extras/diffmerge.1 /usr/share/man/man1/diffmerge.1
     sudo chmod 644 /usr/share/man/man1/diffmerge.1


Next

    
    git config --global merge.tool diffmerge
    git config --global mergetool.diffmerge.cmd "diffmerge --merge --result=\$MERGED \$LOCAL \$BASE \$REMOTE"
    git config --global mergetool.diffmerge.trustExitCode true


Source: [http://adventuresincoding.com/2010/04/how-to-setup-git-to-use-diffmerge/](http://adventuresincoding.com/2010/04/how-to-setup-git-to-use-diffmerge/)
