---
layout: post
status: publish
published: true
title: Eclipse has specific junit/guava knowledge in code analysis
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 526
wordpress_url: http://martijndashorst.com/blog/?p=526
date: '2013-08-19 12:58:28 +0200'
date_gmt: '2013-08-19 11:58:28 +0200'
categories:
- java
tags: []
comments: []
---
<p>While checking my work project for warnings I noticed that Eclipse spotted some dead code after a JUnit <code>assertNotNull</code>. Some testing and discussion on twitter with Roy van Rijn led me to tinker a bit with Eclipse's dead code analysis. First the code in question:</p>
<pre lang="java" line="1">    Appointment appointment1 = null;
    Appointment appointment2 = null;
    for(Appointment appointment : appointments) {
        if(appointment.getSomething() == 1)
            appointment1 = appointment;
        if(appointment.getSomething() == 2)
            appointment2 = appointment;
    }
    assertNotNull(appointment1);
    assertNotNull(appointment2);
    if(appointment1 == null || appointment2 == null) {
        throw IllegalStateException();
    }</pre>
<p>Eclipse generates a warning on line 11 stating that both appointment1 and appointment2 are both never null at that point. This led me to believe that Eclipse has specific knowledge of JUnit, a point that Roy contests.</p>
<p>Roy's assertion was that Eclipse did a full code path analysis of the call sequence, as JUnit ultimately throws an exception in this case, which could be proven by static analysis.</p>
<p>A short test shows that in fact Eclipse does treat <code>assertNotNull</code> as a special case, and does not perform a full call sequence analysis:</p>
<pre lang="java" line="1">import static org.junit.Assert.assertNotNull;
import static org.junit.Assert.fail;

public class Test {
    public void deadCodeAfterAssertNotNull() {
        assertNotNull(null);
        fail("");
    }

    public void noDeadCodeAfterFail() {
        fail("");
        assertNotNull(null);
    }
}</pre>
<p>Eclipse generates a warning for dead code at line 7, but not at line 12, however <code>assertNotNull</code> ultimately calls <code>fail(String)</code>. Thus my conclusion that Eclipse does in fact have a special case for detecting <code>assertNotNull</code>.</p>
<p><b>Update:</b> It appears that the static analysis checker also has built in support for Guava's <code>Preconditions</code>:</p>
<pre lang="java" line="1">public void deadCodeAfterGuavaAssertion() {
    Preconditions.checkNotNull(null);
    System.out.println("Dead code");
}</pre>
<p>The compiler flags line 3 as dead code. However:</p>
<pre lang="java" line="1">public void noDeadCodeAfterMyFail() {
    myFail();
    System.out.println("No dead code");
}

private final void myFail() {
    throw new RuntimeException();
}</pre>
<p>Does not make Eclipse's compiler conclude that line 3 is dead code.</p>
