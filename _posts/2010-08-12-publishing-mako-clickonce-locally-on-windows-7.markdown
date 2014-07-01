---
author: marknadig
comments: true
date: 2010-08-12 22:45:21+00:00
layout: post
published: false
slug: publishing-mako-clickonce-locally-on-windows-7
title: Publishing Mako ClickOnce locally on Windows 7
wordpress_id: 64
categories:
- Windows 7
---


 

  1. Create a MakoClient folder under Web. Configure as Application in IIS (not just virtual dir).

  2. Add read permissions to local IIS user to this folder. Note: This step seemed a little tricky. Sometimes it seemed to work and others not. I would get a 401 unauthorized error when HDM tried to download the zip. Finally, I granted myself full control over that folder as well as IIS user with read access and it still would flake out. Then, I found that I was updating the zip in the MakoClient folder which seemed to wonk the permissions. If I update the zip in Web\Client and then copy over to MakoClient it is fine.

  3. Change Web\Client\DeltekMako.* to read-write. You cannot check these files out as TFS will lock for checkout regardless.

  4. Open DeltekMako.sln, open properties for project and remove Sign property checkbox (under signing tab). Exclude TXTextControl class and all TX references.

  5. Publish to local folder c:\Development\Deltek .Net Mako\Main\Web\MakoClient

  6. Zip up everything in Web\Client and then remove:  
Deltek.Framework.Deployment.Client.dll  
Deltek.Framework.Controls.Client.dll  
Deltek.Framework.Errors.Common.dll  
Deltek.Framework.Frame.Client.dll  
Deltek.Framework.Globals.Common.dll  
Deltek.Framework.Globals.Common.XmlSerializers.dll  
Deltek.Framework.Lookup.Common.dll  
Deltek.Framework.Lookup.Common.XmlSerializers.dll  
Deltek.Mako.Controls.Client.dll  
Deltek.Mako.Frame.Client.dll  
Deltek.Mako.Globals.Common.dll  
Deltek.Product.Enumerations.Common.dll  
EPM.Security.Toolkit.dll  
Ionic.Utils.Zip.dll  
Microsoft.mshtml.dll  
Microsoft.ReportingServices.Interfaces.dll  
CompressionChannel.dll  
TX*.dll  
DeltekMako.*

  7. Rename zip DeltekMakoClient.zip and put in Web\MakoClient

  8. Copy DeploymentManifest.xml and DeltekMakoClient_frFR.zip from [\\hq1apdev64vm\Mako\WebClient](///\\hq1apdev64vm\Mako\WebClient) into MakoClient folder.


You should now be able to navigate to [http://localhost/MakoClient](http://localhost/MakoClient) and launch clickonce.


As you make code changes, copy the affected dlls back into ZIP. Run **mage –cc **to from a command prompt to clear clickonce cache.





**Category:** Windows 7




**Published:** 8/12/2010 6:45 PM



