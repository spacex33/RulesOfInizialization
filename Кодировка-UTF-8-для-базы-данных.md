В файле /etc/mysql/my.cnf нужно добавить следующие строки

    [mysqld]
    character-set-server = utf8
    character-set-filesystem = utf8


Если база данных уже была создана с другой кодировкой, можно изменить кодировки базы и таблиц такими командами в mysql:

    mysql> ALTER DATABASE databasename CHARACTER SET utf8 COLLATE utf8_unicode_ci;
    mysql> ALTER TABLE tablename CONVERT TO CHARACTER SET utf8 COLLATE utf8_unicode_ci;