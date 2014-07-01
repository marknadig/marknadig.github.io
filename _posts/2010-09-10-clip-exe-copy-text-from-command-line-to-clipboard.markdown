---
author: marknadig
comments: true
date: 2010-09-10 19:24:37+00:00
layout: post
slug: clip-exe-copy-text-from-command-line-to-clipboard
title: CLIP.EXE – copy text from command line to clipboard
wordpress_id: 61
categories:
- Windows 7
---

Copy Output from Command Line Applications to the Clipboard


To copy text from a command to the clipboard, we'll just pipe it into the clip command, like this:


| clip


For example, if you wanted to output from the echo command into the clipboard, you could do this:


![](/personal/marknadig/Blog/Lists/Photos/091010_1924_CLIPEXEcopy1.png)
		

You can also use redirection to send a text file directly into the clip utility, like this:


clip < filename.txt


In this example I'm gonna put the contents of the single.php file onto the clipboard:


![](/personal/marknadig/Blog/Lists/Photos/091010_1924_CLIPEXEcopy2.png)
		

Of course, you could also use the type command and then pipe it to the clipboard like so:


![](/personal/marknadig/Blog/Lists/Photos/091010_1924_CLIPEXEcopy3.png)
		

(source [howtogeek](http://www.howtogeek.com/howto/28473/how-to-copy-output-text-from-the-command-line-to-the-windows-clipboard/))

**Category:** Windows 7

**Published:** 9/10/2010 3:24 PM

