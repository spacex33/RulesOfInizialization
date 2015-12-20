1. Cоздать приложение на Openshift (Нажать на кнопку **Add Application…**);
2. Тип приложения **Tomcat 7 (JBoss EWS 2.0)**;
3. Создать базу данных (Нажать на кнопку **Add MySQL 5.5**);
4. Установить rhc https://developers.openshift.com/en/getting-started-debian-ubuntu.html;
5. Настроить ssh ключи `rhc setup`
6. Зайти через консоль на OpenShift (`Want to log in to your application?` на странице с приложением, копировать команду)
7. Найти переменные окружения MySQL : `env | grep MYSQL`
8. Для удобства скопировать настройки OpenShift :
   
```
   DRIVER_CLASS_NAME=com.mysql.jdbc.Driver
   JDBC_URL=jdbc:mysql://$OPENSHIFT_MYSQL_DB_HOST:$OPENSHIFT_MYSQL_DB_PORT/flowerexpert?useUnicode=true&characterEncoding=UTF-8
   JDBC_USER=$OPENSHIFT_MYSQL_DB_USERNAME
   JDBC_PASSWORD=$OPENSHIFT_MYSQL_DB_PASSWORD
```

Установить переменные окружения для Tomcat:

rhc set-env JAVA_OPTS_EXT="-DDRIVER_CLASS_NAME=com.mysql.jdbc.Driver -DJDBC_URL=jdbc:mysql://$OPENSHIFT_MYSQL_DB_HOST:$OPENSHIFT_MYSQL_DB_PORT/flowerexpert?useUnicode=true&characterEncoding=UTF-8 -DJDBC_USER=$OPENSHIFT_MYSQL_DB_USERNAME -DJDBC_PASSWORD=$OPENSHIFT_MYSQL_DB_PASSWORD" -a flowerexpert