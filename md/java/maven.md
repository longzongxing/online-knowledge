# Maven 打包

## 1.打包命令

1.cd到需要打包项目的pom.xml文件下 运行：mvn clean install -Dmaven.test.skip=true -Dmaven.javadoc.skip=true 

代码意思代表：Clean 跳过测试 直接install

```
mvn clean install -Dmaven.test.skip=true -Dmaven.javadoc.skip=true
```

## 2.运行jar

```
java -Dfile.encoding=utf-8 -jar WriteToExcel5.jar
```

