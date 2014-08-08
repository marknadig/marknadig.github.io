---
author: marknadig
comments: true
date: 2012-12-03 21:39:00+00:00
layout: post
slug: share-windows-7-printer-w-osx
title: Share Windows 7 printer w/ OSx
wordpress_id: 297
tags:
- OS X
---

**Mac OS X v10.5 or later**


  1. Choose **System Preferences** from the **Apple** menu.

	
  2. Choose **Print & Fax** from the **View** menu.

	
  3. Click the **+** button to add a printer.

	
  4. Press the Control key while clicking the "Default" icon (or any other icon on the toolbar), then choose Customize Toolbar from the contextual menu that appears.

	
  5. Drag the Advanced (gear) icon to the toolbar.

	
  6. Click Done.

	
  7. Click the Advanced icon that was added to the toolbar.

	
  8. Choose Windows from the Type pop-up menu.

	
  9. In the URL field, type the printer's address in one of the following formats:

smb://workgroup/server/sharename
smb://server/sharename

**Note**: "workgroup" is the name of the Windows workgroup that the computer sharing the printer belongs to. "server" is the name of the computer sharing the printer (or its IP address). "sharename" is the shared Windows printer's share name. If the share name contains spaces, replace each space with "%20" (without quotation marks).

**Tip**: You don't need a "workgroup" when specifying the IP address of the computer (such as when the printer is on a different subnet), or if your Mac belongs to the same Windows (SMB) workgroup.

	
  10. In the Name field, type the name you would like to use for this printer in Mac OS X.

	
  11. Choose the appropriate PPD or printer driver from the "Print Using" pop-up menu.

	
  12. Click Add.


Source [http://support.apple.com/kb/HT3049](http://support.apple.com/kb/HT3049)


