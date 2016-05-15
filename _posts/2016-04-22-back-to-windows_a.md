---
author: marknadig
comments: true
date: 2016-04-22 11:55:01-0600
layout: post
slug: back-to-windows
title: Back to Windows
---


I've been coming back to Visual Studio and Windows development after a 5 year stint with web developement on OSX. Definitely feeling some friction in Windows:
* cmd window doesn't resize or copy/paste, can't clear with shortcut.
* no package manager [not sold on chocolately]
* Visual Studio is big and heavy
* TFS is slow and merging across branches loses history.

So, here's some things I've found that make the transition a bit better.

### Visual Studio Plugins:
[Fix File Encoding](vlasovstudio.com/fix-file-encoding/) - automatically strip UTF-8 signature from html/js   
[Code Compare](https://www.devart.com/codecompare/) - a better code compare   
[File Nesting](https://visualstudiogallery.msdn.microsoft.com/3ebde8fb-26d8-4374-a0eb-1e4e2665070c) - handy for managing partials by nesting them under their 'parent' in a VS project/solution.
[Build Monitor](https://visualstudiogallery.msdn.microsoft.com/b0c87e47-f4ee-4935-9a59-f2c81ce692ab) - Show how long builds take   
[Web Analyzier](https://github.com/madskristensen/WebAnalyzer) - Incorporate ESLint, TSLint into Visual Studio   


### Windows apps:
[Diffmerge](https://sourcegear.com/diffmerge/) - great for comparing files/folder   
[ConEmu](https://github.com/Maximus5/ConEmu) - great command shell replacement (supports, cmd, bash, etc.)   
[AstroGrp](http://astrogrep.sourceforge.net/download/) - FOSS gui grep   
[AutoHotkey](https://autohotkey.com/) - swiss army knife for windows keyboard shortcuts. I currently have shortcuts for volume up/down and found a [script](http://superuser.com/questions/585238/clear-windows-command-prompt-screen-using-keyboard-shortcuts) that lets me Ctrl+L to clear cmd!   
[Launchy](http://www.launchy.net/) - Like Spotlight/Alfred   
[Robocopy](https://technet.microsoft.com/en-us/library/cc733145.aspx) - built in windows command for better, restartable copies. There's a [GUI](https://technet.microsoft.com/en-us/magazine/2009.04.utilityspotlight.aspx) to help navigate all the knobs.   
[LICECAP](http://www.cockos.com/licecap/) - cross platform animated gif screen capture.    
