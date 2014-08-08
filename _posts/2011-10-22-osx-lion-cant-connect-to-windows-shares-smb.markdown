---
author: marknadig
comments: true
date: 2011-10-22 17:29:20+00:00
layout: post
slug: osx-lion-cant-connect-to-windows-shares-smb
title: OSx Lion can't connect to Windows Shares (SMB)
wordpress_id: 24
tags:
- OS X
---

Not sure if it's been like this all along with Lion, or just after an update. However, all of a sudden, I can no longer access my windows shares on my home network.
  

- Launch Terminal  

- Create a folder, for my test I created a desktop folder  

   mkdir ~/Desktop/MyMedia  

- Command Line Format to mount the SMB share:  

   mount -t smbfs //Username@ServerOrIP/Media ~/Desktop/MyMedia  

- A prompt will ask for your password  

  

source: https://discussions.apple.com/thread/3196311?start=60&tstart=0
