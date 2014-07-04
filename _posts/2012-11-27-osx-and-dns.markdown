---
author: marknadig
comments: true
date: 2012-11-27 20:23:27+00:00
layout: post
slug: osx-and-dns
title: OSx and DNS
wordpress_id: 289
categories:
- OS X
---

A few ways I found to find out your dns server in OSx

    
    # Open preferences, select Network pane.
    # or
    nslookup www.kona.com
    
    # or 
    # list network services, 'Ethernet' may be one
    networksetup listallnetworkservices
    # Show DNS for specific service. Note: May show 'none' - see next
    networksetup -getdnsservers Ethernet
    
    # or
    cat /etc/resolv.conf | grep nameserver


and how to change the dns server (to google's public DNS):

    
    sudo networksetup -setdnsservers Wi-Fi 8.8.8.8 8.8.4.4


See [ServerFault](http://serverfault.com/questions/170591/how-to-append-new-dns-server-via-command-line) and this [blog](http://www.electrictoolbox.com/mac-osx-change-dns-servers-command-line/).
