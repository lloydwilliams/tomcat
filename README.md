# Tomcat
This repository has configurations for Tomcat with Datadog.

For this Datadog sample, I used 

conf/logging.properties

```
java.util.logging.SimpleFormatter.format=%1$tFT%1$tH:%1$tM:%1$tS.%1$tL%1tz %4$s [%2$s] %5$s%6$s%n
```

notice:

```
1catalina.org.apache.juli.AsyncFileHandler.formatter = java.util.logging.SimpleFormatter
```

