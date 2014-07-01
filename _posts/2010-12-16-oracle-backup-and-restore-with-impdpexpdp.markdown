---
author: marknadig
comments: true
date: 2010-12-16 17:23:23+00:00
layout: post
slug: oracle-backup-and-restore-with-impdpexpdp
title: Oracle backup and restore with IMPDp/EXPDp
wordpress_id: 41
categories:
- Oracle
---

The word on the street is that all of these types of operations should be done from the SYSTEM user. 


## EXPDp 


EXPDP SYSTEM/Password1@HQ1DBDEV4 SCHEMAS=PMCompassDemo DIRECTORY=BACKUP_DIR DUMPFILE=PMCompassDemo.dmp 


This can be run from any machine with Oracle tools installed. The @HQ1DBDEV4 specifies a different machine to connect to when not local. This will create a PMCompassDemo.dmp on e:\Backups on HQ1DBDEV4. 


## IMPDp 


IMPDP SYSTEM/Password1@HQ1DBDEV4 REMAP_SCHEMA=PMCompassDemo:PMCompassDemoMark DIRECTORY=BACKUP_DIR DUMPFILE=PMCompassDemo.dmp LOGFILE=dmp.log 


This includes the REMAP_SCHEMA to restore the PMCompassDemo schema into the PMCompassDemoMark schema. 


If any warnings or errors appear, open SQLDeveloper and recompile any views/procedures that threw warnings. Also, the DeltekPackage is unique per user in Oracle. Since we have many dbs/users on the same server you will need to re-create the DeltekPackage. Open FW_Procedures_Oracle.sql and run the FW_Deltekpackage portion. 


## DIRECTORY 


Oracle needs to know where to put the dump (.dmp) file. By default 10g and higher ship with a directory 'DATA_PUMP_DIR'. 


SELECT directory_path
			FROM
			dba_directories
			WHERE
			directory_name = 'DATA_PUMP_DIR'; 
	

Alternatively, you can set up additional directories. Here's how: 


CREATE directory TEMP_DIR AS 'c:\users\MARKNA~1\AppData\Local\Temp';   
GRANT READ, WRITE ON directory dmpdir TO PMCompassDemo;  
	

Note: SYSTEM does not need explicit permission to the folder. 


 
 

Here's the whole process, creating a local copy of PMCompassDemo from HQ1DBDEV4. 


  1. From local command pompt run:  
EXPDP SYSTEM/Password1@HQ1DBDEV4 SCHEMAS=PMCompassDemo DIRECTORY=BACKUP_DIR DUMPFILE=PMCompassDemo.dmp
		
  2. Zip e:\backups\PMCompassDemo.dmp from HQ1DBDEV4 

  3. Copy zip to local %TEMP% folder and extract. This assumes the TEMP_DIR directory has been set up. 

  4. From SQLDeveloper logged into local SYSTEM  
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
GRANT CONNECT, RESOURCE, CREATE SESSION TO PMCompassDemo;  
GRANT CREATE VIEW TO PMCompassDemo;  
GRANT CREATE TRIGGER TO PMCompassDemo;  
GRANT CREATE ANY CONTEXT TO PMCompassDemo;  
/
		
  5. From local command prompt run:  
IMPDP SYSTEM/Password1 REMAP_SCHEMA=PMCompassDemo:PMCompassDemo DIRECTORY=TEMP_DIR DUMPFILE=PMCompassDemo.dmp LOGFILE=dmp.log
		
  6. From SQLDeveloper connect to local PMCompassDemo and run FW_DeltekPackage. Open Procedures and recompile CAM_INSERTWSTDCTVIEW, CAM_SETCONTEXTINFO, CAM_UNROTATECOLUMN. 


## FW_DeltekPackage 


Note: For reference only, please pull latest from FW_Procedures_Oracle.sql TFS. 


CREATE OR replace PACKAGE deltekpackage
			  
AS
			  
  PROCEDURE setsessionvalue(
			  
    varname  IN _VARCHAR2_,
			  
    varvalue IN _VARCHAR2_);
			  
END deltekpackage;
			  
  
/
			  
DECLARE
			  
    v_contextname _VARCHAR2_(50);
			  
    v_sqlstr      _LONG_;
			  
BEGIN
			  
    SELECT dbms_random.**String**('A', 5)
			INTO
			v_contextname
			FROM   dual;
			  
  
    v_sqlstr := 'create or replace package body DeltekPackage as' ||   
    ' procedure SetSessionValue(varName in varchar2,varValue in varchar2) is'
			  
                || ' begin dbms_session.set_context(''DeltekContext_'
			  
                || v_contextname
			  
                || ''', varName, varValue);'
			  
                || ' end SetSessionValue; end DeltekPackage;';
			  
  
    EXECUTE IMMEDIATE v_sqlstr;
			  
  
    v_sqlstr := 'create or replace context DeltekContext_'
			  
                || v_contextname
			  
                || ' using DeltekPackage';
			  
  
    EXECUTE IMMEDIATE v_sqlstr;
			  
END;
			  
/ 
