---
author: marknadig
comments: true
date: 2010-09-16 16:53:21+00:00
layout: post
slug: backuprestore-oracle
title: Backup/restore Oracle
wordpress_id: 43
categories:
- Oracle
---

I have XE installed locally and wanted to pull a backup from Oracle on another server. From a command-line:

CD c:\oraclexe\app\oracle\product\10.2.0\server\BIN
EXP PMCompassDemo/PMCompassDemo@FTCDEVDB7 OWNER=PMCompassDemo FILE=%temp%\PMCompassDemo.dmp STATISTICS=none

This pulls down the backup to my temp folder. Note: This was very slow, so I found it must faster to RDP into FTCDevDB7 and run it 'local' then zip and copy the dmp. The @ syntax uses the name from TNSNames.

To restore, first drop and recreate the tablespace and user:

DROP TABLESPACE PMCompassDemo INCLUDING CONTENTS AND DATAFILES;
/ 

CREATE TABLESPACE PMCompassDemo
  DATAFILE 'C:\ORACLEXE\ORADATA\XE\PMCompassDemo.dbf'   
  SIZE 32m   
  AUTOEXTEND ON   
  NEXT 32m   
  MAXSIZE 2048m;  
/

DROP USER PMCompassDemo CASCADE;
/

CREATE USER PMCompassDemo IDENTIFIED BY PMCompassDemo
DEFAULT TABLESPACE PMCompassDemo   
QUOTA UNLIMITED ON PMCompassDemo  
TEMPORARY TABLESPACE Temp;  
GRANT CONNECT, RESOURCE, CREATE SESSION TO PMCompassDemo;  
GRANT CREATE VIEW TO PMCompassDemo;  
GRANT CREATE TRIGGER TO PMCompassDemo;  
/ 

Now, ready to import:

IMP PMCompassDemo/PMCompassDemo@XE FILE=%temp%\PMCompassDemo.dmp FROMUSER=PMCompassDemo TOUSER=PMCompassDemo

Note: Often some of the views will fail on importing. Re-running IMP will resolve or this [recompile trick](/personal/marknadig/Blog/Lists/Posts/ViewPost.aspx?ID=160).

Thanks Tim/Dave for helping me with this syntax.

EXP HELP=YES to get help.
