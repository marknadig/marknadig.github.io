---
author: marknadig
comments: true
date: 2010-12-13 15:55:29+00:00
layout: post
published: false
slug: publishing-pm-compass-clickonce-locally-on-windows-7
title: Publishing PM Compass ClickOnce locally on Windows 7
wordpress_id: 42
---

  1. In Windows Explorer (WE), create a MakoClient folder under Web. In IIS create a new Application in IIS (not just virtual dir) pointing to this new folder.. 
			
  2. Add read permissions to local IIS user to this folder. In WE, right-click on the new MakoClient folder and select Properties. Click Security tab and Edit button. Click add and select IIS_IUSRS.1
				
			
  3. Change Web\Client\DeltekPMCompass.* to read-write. You cannot check these files out as TFS will lock for checkout regardless. 
			
  4. Open Client\Main\DeltekPMCompass.vbproj, open properties for project.
				

    1. Remove Sign property checkbox (under signing tab). 
					
    2. Open Publish: Application Files dialog and click Show All and explicitly include any PDBs for framework files automatically included in the boostrap app and DeltekPMCompass.pdb. These are excluded by default for clickonce.
					
    3. Exclude TXTextControl class and all TX references. 
					
  5. Publish to local _folder_ c:\Development\Deltek .Net Mako\Main\Web\MakoClient . Note: Do not publish to url, rather use file path. 
			
  6. Zip up everything in Web\Client and then remove:  
Deltek.Framework.Controls.Client.dll  
Deltek.Framework.Deployment.Client.dll  
Deltek.Framework.Errors.Common.dll  
Deltek.Framework.Frame.Client.dll  
Deltek.Framework.Globals.Common.dll  
Deltek.Framework.Globals.Common.XmlSerializers.dll  
Deltek.Framework.Lookup.Common.dll  
Deltek.Framework.Lookup.Common.XmlSerializers.dll  
Deltek.PMCompass.Controls.Client.dll  
Deltek.PMCompass.Frame.Client.dll  
Deltek.PMCompass.Globals.Common.dll  
Deltek.Product.Enumerations.Common.dll  
EPM.Security.Toolkit.dll  
Ionic.Utils.Zip.dll  
Microsoft.mshtml.dll  
Microsoft.ReportingServices.Interfaces.dll  
CompressionChannel.dll  
TX*.dll  
DeltekPMCompass.* 
			
  7. Rename zip DeltekPMCompassClient.zip and put in Web\MakoClient 
			
  8. Copy DeploymentManifest.xml and DeltekPMCompassClient_frFR.zip from [\\hq1apdev64vm\Mako\WebClient into MakoClient folder. ](///\\hq1apdev64vm\Mako\WebClient)
			

You should now be able to navigate to [http://localhost/MakoClient/DeltekPMCompass.application  and launch clickonce. 
	

As you make code changes, copy the affected dlls back into ZIP _in the Client folder_ and then re-copy it over to the MakoClient folder. Run mage –cc to from a command prompt to clear clickonce cache. 
		

1 Note: This step seemed a little tricky. Sometimes it seemed to work and others not. I would get a 401 unauthorized error when HDM tried to download the zip. Finally, I granted myself full control over that folder as well as IIS user with read access and it still would flake out. Then, I found that I was updating the zip in the MakoClient folder which seemed to wonk the permissions. If I update the zip in Web\Client and then copy over to MakoClient it is fine.
		



