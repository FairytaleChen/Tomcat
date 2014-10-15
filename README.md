Tomcat
======
- Tomcat將Log輸出機制轉換為Log4j 
  - http://tomcat.apache.org/tomcat-7.0-doc/logging.html#Using_Log4j

- 將Tomcat的靜態檔案cache機制關閉 
  - 將Tomcat/work/Catalina/localhost下的東西刪除，否則會留下之前cache的東西
  - 將Tomcat/conf/context.xml中的Context改為如下 
  ```sh
  <Context cacheMaxSize ="0" cacheTTL="1" cachingAllowed="false" antiResourceLocking="false">
  ```
- 將Tomcat的Log顯現出來，可以透過網路access的到
  - 以command line的方式下如下的指令
  ```sh
  mklink /d "C:\Program Files\Apache Software Foundation\Tomcat 7.0\webapps\logs" "C:\Program Files\Apache Software Foundation\Tomcat 7.0\logs"
  ```
此指令是將第二個參數的路徑建立一個Symbolic Link至第一個參數的路徑位置。
這樣我們才可用網頁的方式access
  - 在"C:\Program Files\Apache Software Foundation\Tomcat 7.0\conf"中的web.xml
  有一部份
  ```sh
        <init-param>
            <param-name>listings</param-name>
            <param-value>false</param-value>
        </init-param>
  ```
  預設為false，請將其改為true。
  ```sh
        <init-param>
            <param-name>listings</param-name>
            <param-value>true</param-value>
        </init-param>
  ```
  此設定為是否Tomcat的目錄可否列表出來。
- 同一台電腦啟動多個Tomcat
  - 將server.xml中的8080 8005 8009這個port number改為不一樣

