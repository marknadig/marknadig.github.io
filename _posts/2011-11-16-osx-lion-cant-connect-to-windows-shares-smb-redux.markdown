---
author: marknadig
comments: true
date: 2011-11-16 04:26:16+00:00
layout: post
slug: osx-lion-cant-connect-to-windows-shares-smb-redux
title: OSx Lion can't connect to Windows Shares (SMB) - redux
wordpress_id: 22
categories:
- OS X
---

In my earlier blog post, outlined approach for mounting an SMB share in Lion (OSx):  

http://home.deltek.com/personal/marknadig/Blog/Lists/Posts/Post.aspx?ID=187  

  

Yesterday, I changed my windows network arround - and dorked someting... just changed the homegroup, but that dorks shares, and... anyway. Now, using the approach from the earlier post, I was getting 'mount_smbfs: server connection failed: Cannot allocate memory'. Thankfully, intertubes provided the answer:  

  

Change  

HKLM\SYSTEM\CurrentControlSet\Services\LanmanServer\Parameters\Size  

to 3 on the host 'server' (another windows 7 machine).  

  

http://alan.lamielle.net/2009/09/03/windows-7-nonpaged-pool-srv-error-2017

**Category:** OSx

**Published:** 11/15/2011 11:23 PM

