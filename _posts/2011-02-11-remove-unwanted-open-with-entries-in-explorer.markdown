---
author: marknadig
comments: true
date: 2011-02-11 22:05:01+00:00
layout: post
slug: remove-unwanted-open-with-entries-in-explorer
title: Remove unwanted "Open With" entries in Explorer
wordpress_id: 35
categories:
- Windows 7
---

As you know, if you right-click any file on your computer you will gain access to a menu where, among the other options available, you will also be able to find the famous “Open with…” feature. Basically, it lets you choose , from a list of recommended applications, the one you wish to use to open your files having X extension. Now, if you don’t like this service because you think that it could cause major issue to your computer  (above all if you don’t have a clue on what application or software to use to open a certain file), I have a nice hack which will let you ** turn off certain programs and applications from the “Open With” option in your right-click menu!**

  1. Click **Start.**


  2. In the Search field, type **regedit **and press **Enter.**


  3. Locate the following registry folder: HKEY_CURRENT_USER\ Software\ Microsoft\Windows\CurrentVersion \ Explorer\FileExts\


  4. The above registry folder contains subfolders for all the file extensions available you have in your computer such as: .sys, .txt, .doc, .zip etc.


  5. Let’s assume that you to modify the “Open With…” option for .zip files.


  6. Browse the FileExts folder and locate the .zip folder.


  7. Open it.


  8. Locate and open the** OpenWithList** subfolder.


  9. On the right-pane you will notice some registry keys labeled with letters.


  10. Look at them and see their descriptions. You will see that for each regitry key corresponds the name of a program under the data field. This means that the system will place  these programs in the “Open With” option and will show them once the user click  it.


  11. Let’s assume that you don’t want the system to show the Notepad program in the list of applications available.


  12. Locate in the OpenWithList the key which has, as Data description, the name of the Notepad (Notepad.exe).


  13. Right-click it and delete it.


  14. Restart your computer for  the change to take effect.

[http://www.webtlk.com/2010/07/13/how-to-remove-programs-from-the-open-with-option-in-windows-7-menu/](http://www.webtlk.com/2010/07/13/how-to-remove-programs-from-the-open-with-option-in-windows-7-menu/)

**Category:** Windows 7

**Published:** 2/11/2011 5:04 PM

