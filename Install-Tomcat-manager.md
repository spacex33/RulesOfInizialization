Если нет приложения `manager`, установить:

    wget -O tomcat.tar.gz http://apache.volia.net/tomcat/tomcat-7/v7.0.65/bin/apache-tomcat-7.0.65.tar.gz
    tar -xzvf tomcat.tar.gz
    cp -avr apache-tomcat-7.0.65/webapps/manager manager
    rm -rf apache-tomcat-7.0.65
    rm tomcat.tar.gz

В файле `conf/tomcat-users.xml`В `<tomcat-users>` добавить

    <role rolename="manager-gui"/>
    <role rolename="admin-gui"/>
    <user username="USER" password="PASSWORD" roles="manager-gui, admin-gui"/>

Deploy war-файла на сервере через Curl:

    curl -T "FlowerExpert.war" "http://USER:PASSWORD@flowerexpert.com.ua/manager/text/deploy?path=/&update=true"