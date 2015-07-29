После установки Maven, в папке проекта FlowerExpert (там где файл pom.xml) набираем команду:

    mvn -q clean install

После этого появится папка target в которой находится файл FlowerExpert.war. Его нужно скопировать в папку webapps Томкэта. Например,

    sudo cp ./target/FlowerExpert.war /var/lib/tomcat7/webapps/

Томкэт сам распакует этот архив в папку FlowerExpert. В браузере вводим:

    http://localhost:8080/FlowerExpert/