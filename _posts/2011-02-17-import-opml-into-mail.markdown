---
author: marknadig
comments: true
date: 2011-02-17 16:50:45+00:00
layout: post
slug: import-opml-into-mail
title: Import OPML into Mail
wordpress_id: 33
categories:
- OS X
---

1. Export an OPML file from your feed reader.  

2. Open Terminal and execute the following command:  

     perl -lne 'print $1 if /"(http.*?)"/' google-reader-subscriptions.xml | pbcopy  

3.  Open Apple Mail.app and do the following:  

      Go to File » Add RSS Feeds...  

      Choose the Specify a custom feed URL radio button  

      Click in the text box and hit Command-V to paste the feed URLs  

      Click the Add button   

  

http://www.cpuug.org/index.php?topic=135.0
