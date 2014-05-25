---
layout: post
status: publish
published: true
title: Hating Oracle
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 415
wordpress_url: http://martijndashorst.com/blog/2009/01/29/hating-oracle/
date: '2009-01-29 12:49:30 +0100'
date_gmt: '2009-01-29 11:49:30 +0100'
categories:
- technology
tags: []
comments:
- id: 57460
  author: Jasdeep
  author_email: jsbhangra@gmail.com
  author_url: http://jasdeepsingh.wordpress.com/
  date: '2009-01-29 13:32:55 +0100'
  date_gmt: '2009-01-29 12:32:55 +0100'
  content: "+1 with you.\r\n\r\nI guess that why they make dollars cause it really
    needs a dedicated person to handle that scary thing ."
- id: 57461
  author: Jörn Zaefferer
  author_email: joern.zaefferer@gmail.com
  author_url: http://bassistance.de
  date: '2009-01-29 14:02:19 +0100'
  date_gmt: '2009-01-29 13:02:19 +0100'
  content: "I usually end up setting a breakpoint for the thrown exception, then going
    back up the stack to try and find the variable which indicates the invalid column.\r\n\r\nOf
    course, that doesn't help at all when all you have is the log file from a production
    server...\r\n\r\nIBM's DB at least provides some context, but no actual error
    message, instead only an error code that you have to lookup somewhere else. I'm
    not sure whats worse."
- id: 57462
  author: James Iry
  author_email: jamesiry@gmail.com
  author_url: http://james-iry.blogspot.com
  date: '2009-01-29 15:28:44 +0100'
  date_gmt: '2009-01-29 14:28:44 +0100'
  content: "Right complaint, wrong victim.  As far as I can tell, the Oracle RDBMS
    product does tell you which column is invalid. If you paste your query into sqlplus
    (or whatever your dba tool of choice is) then you can see it.    \r\n\r\nSQL&gt;
    select cow_face from user_table;\r\nselect cow_face from user_table\r\n       *\r\nERROR
    at line 1:\r\nORA-00904: \"COW_FACE\": invalid identifier\r\n\r\nThe one that
    needs to be shot appears to be the JDBC driver because it's throwing away very
    useful information."
- id: 57463
  author: Gabriel K.
  author_email: gabriel.kastenbaum@gmail.com
  author_url: http://blog.oxiane.com
  date: '2009-01-29 17:20:24 +0100'
  date_gmt: '2009-01-29 16:20:24 +0100'
  content: "Nice complaint! \r\nBut you can also complaint about :\r\n- the \"data
    truncation\" on jtds driver (for sql server) that does not give you the name of
    the column where the data is truncated.\r\n-  Worse, much much worse, I had -
    and I still have -t lots of fights with jsf that throws an exception but does
    not say ANYTHING! Not a word!"
- id: 57464
  author: Jan
  author_email: herkule9s@yahoo.com
  author_url: http://jan.baresovi.cz
  date: '2009-01-29 21:09:57 +0100'
  date_gmt: '2009-01-29 20:09:57 +0100'
  content: For DB2 you can use retrieveMessagesFromServerOnGetMessage property.
- id: 57465
  author: Mike
  author_email: info@mhaller.de
  author_url: http://www.mhaller.de/
  date: '2009-01-29 23:04:22 +0100'
  date_gmt: '2009-01-29 22:04:22 +0100'
  content: So right, Oracle's JDBC sucks. We lost values due to BigDecimal+Java5 bug
    in Oracle drivers. And if you try to put too large values into columns, you just
    get a "Value too large" without the column name or the datatype or anything.
- id: 57470
  author: James
  author_email: jlaw@umich.edu
  author_url: ''
  date: '2009-02-01 03:16:04 +0100'
  date_gmt: '2009-02-01 02:16:04 +0100'
  content: "Yeah, oracle is certainly like MS aren't they? They can not improve but
    still be on top... \r\n\r\nJames"
- id: 57497
  author: Antony Stubbs
  author_email: antony.stubbs@gmail.com
  author_url: http://www.stubbisms.com
  date: '2009-02-17 04:34:53 +0100'
  date_gmt: '2009-02-17 03:34:53 +0100'
  content: Ahmen brother.
- id: 57567
  author: Matt
  author_email: mshannon@gmail.com
  author_url: ''
  date: '2009-05-14 06:22:10 +0200'
  date_gmt: '2009-05-14 05:22:10 +0200'
  content: http://www.oracle.com/technology/tech/java/sqlj_jdbc/pdf/11.1%20logging%20white%20paper.pdf
- id: 57568
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2009-05-14 08:42:13 +0200'
  date_gmt: '2009-05-14 07:42:13 +0200'
  content: "@Matt: great, now we can log stuff. How does that improve the *#$@#$ exception?"
- id: 57569
  author: Matt
  author_email: mshannon@gmail.com
  author_url: ''
  date: '2009-05-15 01:03:50 +0200'
  date_gmt: '2009-05-15 00:03:50 +0200'
  content: "Command line invoked :-\r\njava -classpath .;ojdbc14_g.jar -Djava.util.logging.config.file=log.properties
    -Doracle.jdbc.Trace=true Test\r\n\r\nlog.properties :-\r\n\r\noracle.jdbc.driver.level=INFO\r\noracle.jdbc.driver.handlers=java.util.logging.ConsoleHandler\r\njava.util.logging.ConsoleHandler.formatter
    = java.util.logging.SimpleFormatter\r\n\r\n\r\n\r\nTest.java:-\r\n\r\nimport java.sql.ResultSet;\r\nimport
    java.sql.SQLException;\r\nimport java.sql.Statement;\r\n\r\nimport oracle.jdbc.OracleConnection;\r\nimport
    oracle.jdbc.pool.OracleDataSource;\r\n\r\npublic class Test\r\n{\r\n public static
    void main(String[] args)\r\n {\r\n    String url = \"jdbc:oracle:thin:@//test:1521/orcl\";\r\n
    \   String user = \"scott\";\r\n    String password = \"tiger\";\r\n\r\n    try\r\n
    \   {\r\n        OracleDataSource ods = new OracleDataSource();\r\n        ods.setURL(url);\r\n
    \       ods.setUser(user);\r\n        ods.setPassword(password);\r\n\r\n        OracleConnection
    conn = (OracleConnection) ods.getConnection();\r\n        Statement stmt = conn.createStatement();\r\n
    \       ResultSet rs = stmt.executeQuery(\"select * from session_roles\");\r\n\r\n
    \       while (rs.next())\r\n        {\r\n          System.out.println(rs.getString(\"role\"));\r\n
    \         System.out.println(rs.getString(\"invalidcolumn\"));\r\n        }\r\n
    \       rs.close();\r\n        stmt.close();\r\n\r\n    }\r\n    catch (SQLException
    se)   {  throw new RuntimeException(se);   }\r\n  }\r\n}\r\n\r\nOutput :-\r\n\r\nRESOURCE\r\n15/05/2009
    10:03:22 oracle.jdbc.driver.PhysicalConnection setAutoCommit\r\nINFO: PhysicalConnection.setAutoCommit(autoCommit=true)\r\n15/05/2009
    10:03:22 oracle.jdbc.driver.PhysicalConnection setAutoCommit\r\nINFO: PhysicalConnection.setAutoCommit(autoCommit):
    return\r\n15/05/2009 10:03:22 oracle.jdbc.driver.PhysicalConnection getDefaultFixedString\r\nINFO:
    PhysicalConnection.getDefaultFixedString() returning false\r\n15/05/2009 10:03:22
    oracle.jdbc.driver.OracleStatement executeQuery\r\nINFO: OracleStatement.executeQuery(sql)
    needToPrepareDefineBuffer = true\r\n15/05/2009 10:03:23 oracle.jdbc.driver.T4CStatement
    allocateTmpByteArray\r\nSEVERE: oracle.jdbc.driver.T4CStatement.allocateTmpByteArray
    : Re-allocate byte array of size : 120\r\n15/05/2009 10:03:23 oracle.jdbc.driver.OracleResultSetImpl
    findColumn\r\nINFO: OracleResultSetImpl.findColumn(columnName=role)\r\n15/05/2009
    10:03:23 oracle.jdbc.driver.OracleResultSetImpl getString\r\nINFO: OracleResultSetImpl.getString(columnIndex=1)\r\n15/05/2009
    10:03:23 oracle.jdbc.driver.OracleResultSetImpl findColumn\r\nINFO: OracleResultSetImpl.findColumn(columnName=invalidcolumn)\r\n15/05/2009
    10:03:23 oracle.jdbc.driver.DatabaseError findMessage\r\nWARNING: DatabaseError.findMessage(errNum,
    obj): returned Invalid column name"
- id: 57583
  author: SwitchBL8
  author_email: switchbl8@gmail.com
  author_url: http://www.rare-it.com/blog/
  date: '2009-05-21 12:19:33 +0200'
  date_gmt: '2009-05-21 11:19:33 +0200'
  content: 'How about "ORA-01461: can bind a LONG value only for insert into a LONG
    column"? Got this when inserting more characters than the column-width allowed.
    Then PLEASE tell me the column-width is too small, or my variable too large, and
    don''t give me such a crap errormessage.'
- id: 57824
  author: yetii
  author_email: yetiicom@wp.pl
  author_url: ''
  date: '2009-11-29 01:37:39 +0100'
  date_gmt: '2009-11-29 00:37:39 +0100'
  content: It look like some sort of a PostgreSQL promlem I had few months ago. I
    lokalized issue in my c3p0 and Hibernate configuration. May you should look there
    before you change all the code.
- id: 60162
  author: Alexander Zagniotov
  author_email: azagniotov@gmail.com
  author_url: http://javabeans.asia
  date: '2011-02-10 07:51:32 +0100'
  date_gmt: '2011-02-10 06:51:32 +0100'
  content: "My 5 cents: \r\nSame scenario ... I could not figure it out what is happening.
    \r\nThe generated query worked fine RDBMS, while my test case was giving me \"Caused
    by: java.sql.SQLException: Invalid column name ...\" \r\n\r\nFinally I got it:
    My problem was that I was selecting \"select pu.user_id from ...\". The moment
    I changed to \"select pu.* from ..\" it worked ..."
---
<p>Oracle is a decent product but there are some things I <strong>loathe</strong> about it. The biggest gripe I have with Oracle, and it is a BIG issue I have with it is the following:</p>
<pre>Caused by: java.sql.SQLException: Invalid column name
    at oracle.jdbc.driver.SQLStateMapping.newSQLException(SQLStateMapping.java:70)
    at oracle.jdbc.driver.DatabaseError.newSQLException(DatabaseError.java:112)
    at oracle.jdbc.driver.DatabaseError.throwSqlException(DatabaseError.java:173)
    at oracle.jdbc.driver.DatabaseError.throwSqlException(DatabaseError.java:229)
    at oracle.jdbc.driver.DatabaseError.throwSqlException(DatabaseError.java:403)
    at oracle.jdbc.driver.OracleStatement.getColumnIndex(OracleStatement.java:3366)
    at oracle.jdbc.driver.OracleResultSetImpl.findColumn(OracleResultSetImpl.java:2009)
    at oracle.jdbc.driver.OracleResultSet.getString(OracleResultSet.java:494)
    at com.mchange.v2.c3p0.impl.NewProxyResultSet.getString(NewProxyResultSet.java:3342)
    at org.hibernate.type.StringType.get(StringType.java:18)
    at org.hibernate.type.NullableType.nullSafeGet(NullableType.java:163)
    at org.hibernate.type.NullableType.nullSafeGet(NullableType.java:189)
    at org.hibernate.loader.custom.CustomLoader$ScalarResultColumnProcessor.extract(CustomLoader.java:474)
    at org.hibernate.loader.custom.CustomLoader$ResultRowProcessor.buildResultRow(CustomLoader.java:420)
    at org.hibernate.loader.custom.CustomLoader.getResultColumnOrRow(CustomLoader.java:317)
    at org.hibernate.loader.Loader.getRowFromResultSet(Loader.java:606)
    at org.hibernate.loader.Loader.doQuery(Loader.java:701)
    at org.hibernate.loader.Loader.doQueryAndInitializeNonLazyCollections(Loader.java:236)
    at org.hibernate.loader.Loader.doList(Loader.java:2220)
    ... 46 more
</pre>
<p>Can someone please put the guy that crafted this error message to the wall and shoot him? If you discover an invalid column name, then TELL me which one that was. Queries can span 100+ column names, and it is neigh impossible to figure out which one is invalid.</p>
<p>
	And this is not the only place where Oracle really is subpar in its error messages. Any of the invalid identifier messages doesn't provide you with context. A multi-thousand dollar license product that can't give me decent error messages is not worth a penny in my opinion. Oracle should be ashamed of itself and make a public apologie for billions lost revenue of their customers. Now go and stand in the corner!</p>
