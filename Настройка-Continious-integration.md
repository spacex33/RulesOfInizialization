1. Cоздать приложение на Openshift (Нажать на кнопку **Add Application…**);
2. Тип приложения **Tomcat 7 (JBoss EWS 2.0)**;
3. Создать базу данных (Нажать на кнопку **Add MySQL 5.5**);
4. Установить rhc https://developers.openshift.com/en/getting-started-debian-ubuntu.html;
5. Настроить ssh ключи `rhc setup`
6. Зайти через консоль на OpenShift (`Want to log in to your application?` на странице с приложением, копировать команду)
7. Найти переменные окружения MySQL : `env | grep MYSQL`