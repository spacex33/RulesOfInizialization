1. Создать пустую базу данных для SonarQube. Кодировка базы данных должна быть UTF-8, язык - English.
2. [Скачать](http://www.sonarqube.org/downloads/) и разархивировать архив.
3. Внести изменения в файл `<install_directory>/conf/sonar.properties`, например:    
    
    ```
    sonar.jdbc.username=user
    sonar.jdbc.password=password
    sonar.jdbc.url=jdbc:mysql://localhost:3306/sonar?useUnicode=true&characterEncoding=utf8&rewriteBatchedStatements=true&useConfigs=maxPerformance
    sonar.web.host=localhost
    sonar.web.port=80
    sonar.web.context=/sonar
    ```
4. Запустить сервер следующими командами:
    
    * On Linux/Mac OS: `bin/<YOUR OS>/sonar.sh start`    
    * On Windows: `bin/windows-x86-XX/StartSonar.bat`

5. Настроить Maven:

    В файл `settings.xml` (если его нету, то нужно его создать), который находится по адресу `$MAVEN_HOME/conf` или `~/.m2` добавить настройки:
    
    ```
<settings>
    <profiles>
        <profile>
            <id>sonar</id>
            <activation>
                <activeByDefault>true</activeByDefault>
            </activation>
            <properties>
                <sonar.jdbc.url>
                  jdbc:mysql://localhost:3306/sonar?useUnicode=true&amp;characterEncoding=utf8
                </sonar.jdbc.url>
                <sonar.jdbc.username>user</sonar.jdbc.username>
                <sonar.jdbc.password>password</sonar.jdbc.password>
                <sonar.host.url>
                  http://localhost:80/sonar
                </sonar.host.url>
            </properties>
        </profile>
     </profiles>
</settings>
    ```

6. Настроить `pom.xml`:
    
    * добавить в `pom.xml`:
    ```
<properties>
        <sonar.language>java</sonar.language>
    </properties>
    ```
7. Запустить сканирование командой 
    
    ```
    mvn clean install
    mvn sonar:sonar
    ```
8. Смотреть отчет: [http://localhost/sonar/dashboard/index/1](http://localhost/sonar/dashboard/index/1)