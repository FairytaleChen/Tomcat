Tomcat
======
Tomcat將Log輸出機制轉換為Log4j 
  -http://tomcat.apache.org/tomcat-7.0-doc/logging.html#Using_Log4j

將Tomcat的cache機制關閉 
  -將Tomcat/conf/context.xml中的Context改為如下 
  -將Tomcat\work\Catalina\localhost下的東西刪除，否則會留下之前cache的東西
