# Java Maven Sample

## 1. Download and install Apache Maven

Download Apache Maven from the web page: https://maven.apache.org/download.cgi

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/2588a600-4919-4882-935d-f792024793a8)

Unzig the **** file and place the folder in the C: root hard disk

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/ab3b37c9-6438-4cba-aaf0-537a2f866916)

## 2. Set the Mavent bin folder in the PATH environmental variable

Copy the bin folder path: C:\apache-maven-3.9.5\bin and paste in the PATH environmental variable

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/6dba2422-7b73-4443-9a73-5fbd291b0ead)

## 3. Verify Maven installation

Run this command to verify the Maven installation

```
mvn -v
```


**IMPORTANT NOTE:** We already installed before "C:\Program Files\Java\jdk-1.8\jre"


## 4. Java application source code

```java
package com.example;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

## 5. Java application pom.xml file

```xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.example</groupId>
    <artifactId>sample_maven_with_java</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <maven.compiler.source>1.8</maven.compiler.source>
        <maven.compiler.target>1.8</maven.compiler.target>
    </properties>

    <build>
        <plugins>
            <plugin>
                <!-- Maven JAR Plugin Configuration -->
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>
                <version>3.1.0</version>
                <configuration>
                    <archive>
                        <manifest>
                            <mainClass>com.example.Main</mainClass>
                        </manifest>
                    </archive>
                </configuration>
            </plugin>

            <plugin>
                <!-- Exec Maven Plugin Configuration -->
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>exec-maven-plugin</artifactId>
                <version>3.1.0</version>
                <configuration>
                    <mainClass>com.example.Main</mainClass>
                </configuration>
                <executions>
                    <execution>
                        <goals>
                            <goal>java</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
</project>
```

## 6. Compile and Run the Java with Maven application

To compile the application run the command:

```
mvn clean install
```


To run the application execute the command:

```
mvn exec:java 
```

