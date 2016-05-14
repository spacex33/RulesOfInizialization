`docker rm -f percona`
`docker run --name percona -p 6603:3306 -e MYSQL_ROOT_PASSWORD=12345 -d percona/percona-server:latest --character-set-server=utf8 --collation-server=utf8_general_ci`
`404878c1be7aad2139325365e3669d47954c77619aee407b74d01009d44f5e6a`