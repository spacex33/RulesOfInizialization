В файле /etc/mysql/my.cnf нужно добавить следующие строки

    [mysqld]
    character-set-server = utf8
    character-set-filesystem = utf8


Если база данных уже была создана с другой кодировкой, можно изменить кодировки базы и таблиц такими командами в mysql:

    mysql> ALTER DATABASE databasename CHARACTER SET utf8 COLLATE utf8_unicode_ci;
    mysql> ALTER TABLE tablename CONVERT TO CHARACTER SET utf8 COLLATE utf8_unicode_ci;


Если это не помогает, попробовать изменить collation в mysql-workbench: ПКМ на имени базы

    ALTER SCHEMA `flowerexpert`  DEFAULT COLLATE utf8_bin ;

Решение проблемы с кодировкой на OpenShift

    ssh $app_uuid@app_name-mynamespace.rhcloud.com
    mysql -h $OPENSHIFT_DB_HOST -P $OPENSHIFT_DB_PORT -u $OPENSHIFT_DB_USERNAME --password="$OPENSHIFT_DB_PASSWORD"
    SET GLOBAL character_set_server=utf8, collation_server=utf8_general_ci;
    DROP DATABASE $app_name;
    CREATE DATABASE $app_name DEFAULT CHARACTER SET utf8 DEFAULT COLLATE utf8_unicode_ci;

Еще OpenShift
    
    http://stackoverflow.com/questions/33054209/jboss-how-to-get-utf-8-working-request-encoding