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

This produces a log line like this:

```
2023-05-13T19:15:16.673-0400 INFO [org.apache.catalina.startup.Catalina start] Server startup in [935] milliseconds
```



## Datadog Pipeline Configuration

```
tomcat1 %{date("yyyy-MM-dd'T'HH:mm:ss.SSSZ"):timestamp}\s+%{word:status}\s+\[%{data:java.class}\s+%{word:java.method}\]\s+%{data:msg}

date_msg_status %{date("yyyy-MM-dd'T'HH:mm:ss.SSSZ"):timestamp}\s+%{word:status}\s+%{data:msg}

date_message %{date("yyyy-MM-dd'T'HH:mm:ss.SSSZ"):timestamp}\s+%{data:msg}

message_default %{data:msg}
```





