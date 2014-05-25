---
layout: post
status: publish
published: true
title: Why exception messages suck
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 329
wordpress_url: http://martijndashorst.com/blog/2007/12/13/why-exception-messages-suck/
date: '2007-12-13 14:43:45 +0100'
date_gmt: '2007-12-13 13:43:45 +0100'
categories:
- java
tags: []
comments: []
---
<p>One of my pet peeves is that library builders take special care to check for errors or exception conditions, but fail miserably to communicate <em>what</em> is wrong and how to fix it. The case today: json-lib (2.1).</p>
<p>I'm trying to use it to serialize a bean to JSON format and to compare it to a JSON serialized bean (it is easier to check text instead of the debugger trees). But the json-lib tells me that there is a cycle in the bean.</p>
<pre>Caused by: net.sf.json.JSONException: There is a cycle in the hierarchy!
	at net.sf.json.util.CycleDetectionStrategy$StrictCycleDetectionStrategy.handleRepeatedReferenceAsObject(CycleDetectionStrategy.java:73)
	at net.sf.json.JSONObject._fromBean(JSONObject.java:658)
	at net.sf.json.JSONObject.fromObject(JSONObject.java:182)
	at net.sf.json.JSONObject._processValue(JSONObject.java:2426)
	at net.sf.json.JSONObject._setInternal(JSONObject.java:2447)
	at net.sf.json.JSONObject.setValue(JSONObject.java:1189)
	at net.sf.json.JSONObject._fromBean(JSONObject.java:725)
	at net.sf.json.JSONObject.fromObject(JSONObject.java:182)
	at net.sf.json.JSONObject._processValue(JSONObject.java:2426)
	at net.sf.json.JSONObject._setInternal(JSONObject.java:2447)
	at net.sf.json.JSONObject.setValue(JSONObject.java:1189)
	at net.sf.json.JSONObject._fromBean(JSONObject.java:725)
	at net.sf.json.JSONObject.fromObject(JSONObject.java:182)
	at net.sf.json.JSONObject._processValue(JSONObject.java:2426)
	at net.sf.json.JSONObject._setInternal(JSONObject.java:2447)
	at net.sf.json.JSONObject.setValue(JSONObject.java:1189)
	at net.sf.json.JSONObject._fromBean(JSONObject.java:725)
	at net.sf.json.JSONObject.fromObject(JSONObject.java:182)
	at net.sf.json.JSONObject._processValue(JSONObject.java:2426)
	at net.sf.json.JSONObject._setInternal(JSONObject.java:2447)
	at net.sf.json.JSONObject.setValue(JSONObject.java:1189)
	at net.sf.json.JSONObject._fromBean(JSONObject.java:725)
	at net.sf.json.JSONObject.fromObject(JSONObject.java:182)
	at net.sf.json.JSONObject.fromObject(JSONObject.java:145)
</pre>
<p>Very informative stack trace indeed.</p>
