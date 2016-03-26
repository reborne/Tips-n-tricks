# Tips-n-tricks
This repository can contain tips and trick that may come handy to you


Optimized JVM Runtime memory consumption.
=========================================

STS.ini (valid also for eclipse.ini)

This *.ini configuration allows your JVM use less than 1Gb RAM(in common around 650+ MB) memory 

#My Specs:
<ul>
 <li>Linux Ubuntu 14.04.4 LTS</li>
 <li>Spring Tool Suite 3.7.3.REALEASE</li>
</ul>

#Configuration
<code>
-startup
plugins/org.eclipse.equinox.launcher_1.3.200.v20151021-1308.jar
--launcher.library
plugins/org.eclipse.equinox.launcher.gtk.linux.x86_64_1.1.300.v20160105-0945
-product
org.springsource.sts.ide
--launcher.defaultAction
openFile
-vmargs
-Dosgi.requiredJavaVersion=1.8
-Xverify:none
-server
-Xms128m
-Xmx512m
-XX:ReservedCodeCacheSize=64m
-XX:+UseConcMarkSweepGC
-XX:+AggressiveOpts
-XX:+UseParNewGC
-XX:+CMSClassUnloadingEnabled
-XX:+CMSIncrementalMode
-XX:+CMSIncrementalPacing
-XX:CMSIncrementalDutyCycleMin=0
-XX:-TraceClassUnloading
-XX:+UseCodeCacheFlushing
-Dsun.io.useCanonCaches=false
-Djava.net.preferIPv4Stack=true
-Xverify:none
</code>
After editing *.ini file. make sure you save it and check memory consuption.

I hope it helped to you!
Happy Coding
