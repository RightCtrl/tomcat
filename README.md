# docker-tomcat8-snapshot
#docker-compose.yml
```
version: '2'
services:
  tomcatSSL:
    image: rightctrl/tomcat:https
#    volumes:
#     - ./webapps:/opt/tomcat/webapps
#     - ./logs:/opt/tomcat/logs
    environment:
       CATALINA_OPTS: "$CATALINA_OPTS   -Dfile.encoding=UTF-8 -Djavax.servlet.request.encoding=UTF-8"
       ADMIN_PASS: "RC123456"
       CERT_PASS: "RC987654"
       TIMEZONE: 'Asia/Tokyo'
       DNAME: 'CN=www.rightctrl.com, OU=MarketPlace, O=RightCtrl, C=IN'
    ports:
      - "8080:8080"
      - "8443:8443"
    mem_limit: 3g
    cpuset: 0,1
    restart: always
    ulimits:
     nproc: 65535
     core: 0
     nofile:
      soft: 20000
      hard: 40000
```
