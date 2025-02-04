# Code 相關

## 目錄

* [Java](#Java)

* [Spring boot](#Spring-boot)

* [Maven](#Maven)

  * [Maven的功能](#Maven的功能)
  * [Maven 專案結構](#Maven-專案結構)
  * [Maven 常用指令](#Maven-常用指令)

* [公司專案架構解讀](#公司專案架構解讀)
  * [cdp-backend-services](#cdp-backend-services)

## Java

* JDK：Java Development Kit

* .jar：Java Archive，Java的壓縮檔，裡面包含了多個Java的class檔

## Spring boot

> Spring Boot 是目前 Java 後端中最主流的開發框架

## Maven

Maven是一個專案管理工具，基於POM(Project Object Model)概念，利用**pom.xml**釐清專案中不同jar的依賴關係及建構project所需設定/配置，從而建構一個專案。

> pom.xml實際妙用：

Maven不會將所需的jar檔放入專案資料夾，而是放在本地電腦資料夾或私有repository或Central Repository，這樣專案資料夾更輕盈，方便部署。如果Local repo沒有所需jar檔，會先從私有repository獲取，若無則從Maven Central Repository下載。

部署時的敏感資訊, 如賬號或密碼等, 可以不需放在 pom.xml 內。這些設定的資訊可以放在 settings.xml 檔案內, 不隨 Maven 散佈出去。

### Maven的功能

1.構建(bulid)：專案(project)建構(build)後會產生的Maven的artifact，可能是jar或是war檔，這些檔案預設會存在Local Repository。
2.管理jar
3.編譯程式碼
4.自動運行單元測試
5.打包
6.生成報表
7.部署項目，生成web站點

### Maven 專案結構

```
project
|-- pom.xml
`-- src
    |-- main
    |   |-- java
    |   |   `-- com
    |   |       `-- mycompany
    |   |           `-- app
    |   |               `-- App.java
    |   `-- resources
    |       `-- log4j.properties
    `-- test
        |-- java
        |   `-- com
        |       `-- mycompany
        |           `-- app
        |               `-- AppTest.java
        `-- resources
            `-- log4j.properties
```

### Maven 常用指令

| 指令 | 說明 |
| --- | --- |
| mvn clean | 將上一次建構好的文件與資料夾移除，確保後續動作完全從零執行 |
| mvn package | 將專案打包成jar或war檔 |
| mvn install | 將打包好的檔案放入Local repo |
| mvn deploy | 將打包好的檔案放入 local & remote repo |
| mvn test | 執行單元測試 |
| mvn compile | 編譯程式碼 |
| mvn clean install | 先清除再打包(速度慢但保險) |


