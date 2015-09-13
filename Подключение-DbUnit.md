* добавить зависимости в `pom.xml`
```
<dependency>
	<groupId>org.dbunit</groupId>
	<artifactId>dbunit</artifactId>
	<version>2.5.1</version>
</dependency>

<dependency>
	<groupId>com.github.springtestdbunit</groupId>
	<artifactId>spring-test-dbunit</artifactId>
	<version>1.2.1</version>
</dependency>
```
* добавить xml-файл с информацией для базы данных с таким содержимым:
```
<?xml version="1.0" encoding="UTF-8"?>
<dataset>
    <table_name_1 column_name_1="value" ... />
    ...
</dataset>
```