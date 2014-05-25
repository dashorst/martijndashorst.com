---
layout: post
status: publish
published: true
title: Eclipse 3.4 with openjdk 6 on OS X 32-bit CoreDuo
author: Martijn Dashorst
author_login: admin
author_email: martijn.dashorst@gmail.com
author_url: http://martijndashorst.com
wordpress_id: 435
wordpress_url: http://martijndashorst.com/blog/?p=435
date: '2009-06-02 09:55:24 +0200'
date_gmt: '2009-06-02 08:55:24 +0200'
categories:
- java
- general
- os x
tags:
- eclipse
- os x
- java
comments:
- id: 57621
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2009-06-02 10:51:20 +0200'
  date_gmt: '2009-06-02 09:51:20 +0200'
  content: "I do get into troubles rather quickly, so this is not for the faint of
    heart... For example:\r\n\r\n#\r\n# An unexpected error has been detected by Java
    Runtime Environment:\r\n#\r\n#  SIGSEGV (0xb) at pc=0x9240f336, pid=24654, tid=2953121792\r\n#\r\n#
    Java VM: OpenJDK Server VM (11.0-b17 mixed mode bsd-x86)\r\n# Problematic frame:\r\n#
    C  [CoreGraphics+0x3d336]  CGFontGetGlyphIdentifiers+0x8d\r\n#\r\n# An error report
    file with more information is saved as:\r\n# /Users/dashorst/bin/hs_err_pid24654.log\r\n#\r\n#
    If you would like to submit a bug report, please visit:\r\n#   http://java.sun.com/webapps/bugreport/crash.jsp\r\n#
    The crash happened outside the Java Virtual Machine in native code.\r\n# See problematic
    frame for where to report the bug.\r\n#"
- id: 57622
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2009-06-02 11:00:06 +0200'
  date_gmt: '2009-06-02 10:00:06 +0200'
  content: "And this one came along two times already:\r\n\r\n2009-06-02 11:58:52.573
    java[24801:113] An uncaught exception was raised\r\n2009-06-02 11:58:52.575 java[24801:113]
    objc_object* -[WebView initWithFrame:frameName:groupName:](WebView*, objc_selector*,
    NSRect, NSString*, NSString*) was called from a secondary thread\r\n2009-06-02
    11:58:52.576 java[24801:113] *** Terminating app due to uncaught exception 'WebKitThreadingException',
    reason: 'objc_object* -[WebView initWithFrame:frameName:groupName:](WebView*,
    objc_selector*, NSRect, NSString*, NSString*) was called from a secondary thread'\r\n2009-06-02
    11:58:52.576 java[24801:113] Stack: (\r\n    2480050347,\r\n    2521951803,\r\n
    \   2480049803,\r\n    2480049866,\r\n    2488113267,\r\n    2464832318,\r\n    1462886474,\r\n
    \   30205098\r\n)"
- id: 57623
  author: Martijn Dashorst
  author_email: martijn.dashorst@gmail.com
  author_url: http://martijndashorst.com
  date: '2009-06-02 11:08:42 +0200'
  date_gmt: '2009-06-02 10:08:42 +0200'
  content: As this happens when a code-completion box pops up, I'm reverting back
    to Java 5... darn... I really liked the idea of not living in 2005 anymore...
- id: 57820
  author: MM
  author_email: memorymakersorg@gmail.com
  author_url: http://Offtopic--butwouldappreciateanyhelp
  date: '2009-11-22 03:55:21 +0100'
  date_gmt: '2009-11-22 02:55:21 +0100'
  content: "Hi,\r\n\r\nI'll be happy if I can get eclipse with the stock jdk but I
    keep getting\r\nThe project cannot be built until build path errors are resolved\t\r\nUnknown\tJava
    Problem\r\nUnbound classpath container: 'JRE System Library [OSGi/Minimum-1.2]'
    in project 't'\tt\t\tBuild path\tBuild Path Problem\r\n\r\n---------\r\nI'm trying
    to run eclipse on my Core 2 Duo MacBook Pro:\r\n 10.0.0 Darwin Kernel Version
    10.0.0: Fri Jul 31 22:47:34 PDT 2009; root:xnu-1456.1.25~1/RELEASE_I386 i386\r\n\r\nJava:\r\njava
    version \"1.6.0_15\"\r\nJava(TM) SE Runtime Environment (build 1.6.0_15-b03-219)\r\nJava
    HotSpot(TM) Client VM (build 14.1-b02-90, mixed mode)\r\n\r\nEclipse:\r\nVersion
    3.5.1.R35x_v20090910-9gEeG1_FthkNDSP2odXdThaOu9GFDPn83DGB7\r\nBuild id: M20090917-0800"
---
<p>With the invaluable <a href="http://greensopinion.blogspot.com/2008/08/eclipse-ganymede-on-soylatte.html">help of David Green</a>, I was able to run Eclipse on openjdk 6 on my first gen MacBook Pro (you know, those left behind by Apple, running on a 32 bit CoreDuo processor... good to know that Apple supports the early adapters).</p>
<p>With this script that I adapted from David's blog I was able to start Eclipse 3.4 (Version: 3.4.2<br />
Build id: M20090211-1700) with <a href="http://landonf.bikemonkey.org/2009/05/17#OpenJDK6_MacPorts.20090516">Landon Fullers openjdk 6 build</a>:</p>
<pre>
export JAVA_HOME=/Developer/Java/openjdk6-b16-24_apr_2009-r1
export PATH=$JAVA_HOME/bin:$PATH

java -server -Djava.library.path=$HOME/bin/jnilib -Dswt.library.path=$HOME/bin/jnilib -Xms128m -Xmx768m \
    -XX:MaxPermSize=192m -Dosgi.requiredJavaVersion=1.5 -Dorg.eclipse.swt.internal.carbon.smallFonts \
    -cp /Applications/eclipse/Eclipse.app/Contents/MacOS/../../../plugins/org.eclipse.equinox.launcher_1.0.101.R34x_v20081125.jar \
    org.eclipse.equinox.launcher.Main -os macosx -ws carbon -arch x86 -showsplash \
    -launcher /Applications/eclipse/Eclipse.app/Contents/MacOS/eclipse -name Eclipse \
    --launcher.library /Applications/eclipse/Eclipse.app/Contents/MacOS/../../../plugins/org.eclipse.equinox.launcher.carbon.macosx_1.0.101.R34x_v20080731 \
    -startup /Applications/eclipse/Eclipse.app/Contents/MacOS/../../../plugins/org.eclipse.equinox.launcher_1.0.101.R34x_v20081125.jar \
    -launcher /Applications/eclipse/Eclipse.app/Contents/MacOS/eclipse \
    -keyring $HOME.eclipse_keyring -consoleLog -showlocation -vm $JAVA_HOME
</pre>
<p>The script misses the <a href="http://en.wikipedia.org/wiki/Shebang_(Unix)">shebang</a>, since my hosting provider thinks that I'm trying to execute some serverside exploit...<br />
You'll have to extract a couple of shared libraries that are packaged in your Eclipse distribution:</p>
<pre>jar xfv /Applications/eclipse/plugins/org.eclipse.swt.carbon.macosx_3.4.1.v3452b.jar
jar xfv /Applications/eclipse/plugins/org.eclipse.core.filesystem.macosx_*.jar os/macosx/liblocalfile_1_0_0.jnilib</pre>
<p>You'll have to rename all those libraries to give them a <tt>*.dylib</tt> extension.</p>
<p>Finally I had to point /System/Library/Frameworks/JavaVM.framework/Versions/1.6/Home to the openjdk 6 directory:</p>
<pre>sudo mv /System/Library/Frameworks/JavaVM.framework/Versions/1.6/Home /System/Library/Frameworks/JavaVM.framework/Versions/1.6/Home.old
sudo ln -s LOCATION_OF_OPENJDK /System/Library/Frameworks/JavaVM.framework/Versions/1.6/Home</pre>
