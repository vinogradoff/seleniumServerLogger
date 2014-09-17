seleniumServerLogger
====================

Simple patch to change the output format of Selenium 2 standalone server to include date to the timestamp e.g.

    2014-09-17 17:26:55.452 INFO - Launching a standalone server
    2014-09-17 17:26:55.619 INFO - Java: Oracle Corporation 24.45-b08
    2014-09-17 17:26:55.619 INFO - OS: Mac OS X 10.9.4 x86_64
    2014-09-17 17:26:55.717 INFO - v2.43.1, with Core v2.43.1. Built from revision 5163bce
    2014-09-17 17:26:55.957 INFO - Default driver org.openqa.selenium.ie.InternetExplorerDriver registration is skipped: registration capabilities Capabilities [{platform=WINDOWS, ensureCleanSession=true, browserName=internet explorer, version=}] does not match with current platform: MAC
    2014-09-17 17:26:56.129 INFO - RemoteWebDriver instances should connect to: http://127.0.0.1:4444/wd/hub
    2014-09-17 17:26:56.131 INFO - Version Jetty/5.1.x

instead of

    17:26:55.452 INFO - Launching a standalone server
    17:26:55.619 INFO - Java: Oracle Corporation 24.45-b08
    17:26:55.619 INFO - OS: Mac OS X 10.9.4 x86_64
    17:26:55.717 INFO - v2.43.1, with Core v2.43.1. Built from revision 5163bce
    17:26:55.957 INFO - Default driver org.openqa.selenium.ie.InternetExplorerDriver registration is skipped: registration capabilities Capabilities [{platform=WINDOWS, ensureCleanSession=true, browserName=internet explorer, version=}] does not match with current platform: MAC
    17:26:56.129 INFO - RemoteWebDriver instances should connect to: http://127.0.0.1:4444/wd/hub
    17:26:56.131 INFO - Version Jetty/5.1.x
    
usage
====================
download the selenium-datelogger_fix.jar, put it in the same folder with the selenium-server-standalone-2.x.y.jar

then run (Linux,Mac)

    java -cp "./selenium-datelogger_fix.jar:./selenium-server-standalone-2.x.y.jar" org.openqa.grid.selenium.GridLauncher [options]

or in Windows

    java -cp "./selenium-datelogger_fix.jar;./selenium-server-standalone-2.x.y.jar" org.openqa.grid.selenium.GridLauncher [options]

instead of

    java -jar selenium-server-standalone-2.x.y.jar [options]
    
If you want to make your own date/time format, just change the line

    timestampFormatter = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss.SSS");
    
compile, pack to the jar and off it goes!


