    wget -O tomcat.tar.gz http://apache.volia.net/tomcat/tomcat-7/v7.0.65/bin/apache-tomcat-7.0.65.tar.gz
    tar -xzvf tomcat.tar.gz
    cp -avr apache-tomcat-7.0.65/webapps/manager manager
    rm -rf apache-tomcat-7.0.65
    rm tomcat.tar.gz
