---
author: marknadig
comments: true
date: 2010-10-15 16:40:16+00:00
layout: post
slug: identify-and-recompile-invalid-objects-in-oracle
title: Identify and recompile invalid objects in Oracle
wordpress_id: 49
categories:
- Oracle
---




One at at time:  
ALTER VIEW CAM_PROGRAM COMPILE; 




etc.  




Script to find all and recompile: 




SET SERVEROUTPUT ON SIZE 1000000   
BEGIN   
FOR cur_rec IN (SELECT owner, object_name, object_type FROM dba_objects   
                WHERE object_type IN ('PROCEDURE', 'FUNCTION', 'VIEW', 'TRIGGER')   
                  AND status != 'VALID')   
LOOP   
BEGIN   
   EXECUTE IMMEDIATE 'ALTER ' || cur_rec.object_type || ' "' || cur_rec.owner || '"."' || cur_rec.object_name || '" COMPILE'; 




   EXCEPTION   
   WHEN OTHERS THEN   
      DBMS_OUTPUT.put_line(cur_rec.object_type || ' : ' || cur_rec.owner || ' : ' || cur_rec.object_name);   
END;   
END LOOP;   
END;   
/   








   




source: [http://www.oracle-base.com/articles/misc/RecompilingInvalidSchemaObjects.php](http://www.oracle-base.com/articles/misc/RecompilingInvalidSchemaObjects.php)




**Category:** Oracle




**Published:** 10/15/2010 12:34 PM



