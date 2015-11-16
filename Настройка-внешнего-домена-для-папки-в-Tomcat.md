В настройках домена (напр. на ukraine.com.ua) нужно указать ip по которому находится Tomcat (в нашем случае это ip нашего vps - 31.131.19.194).

в файле Tomcat server.xml добавить аналогичную запись:

    <Host name="flowerexpert.com.ua"  appBase="flowerexpert_webapps" unpackWARs="true" autoDeploy="true">
    <Alias>www.flowerexpert.com.ua</Alias>
    </Host>

flowerexpert_webapps - это папка в /var/lib/tomcat7. В ней содержится папка ROOT в которую распаковано содержимое FlowerExpert.war.
