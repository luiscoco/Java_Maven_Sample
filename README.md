# Java Maven Sample

## 1. Download and install Apache Maven

Download Apache Maven from the web page: https://maven.apache.org/download.cgi

![image](https://github.com/luiscoco/Java_with_Maven_Sample/assets/32194879/2f9b000d-2d34-4393-bdeb-d2526fefed07)

Unzig the **** file and place the folder in the C: root hard disk

![image](https://github.com/luiscoco/Java_with_Maven_Sample/assets/32194879/a0c36327-8fbb-452d-bf0d-74fa79dc27bf)

![image](https://github.com/luiscoco/Java_with_Maven_Sample/assets/32194879/db6c25a8-9d03-4100-adf2-bb2a67d43bb6)

## 2. Set the Mavent bin folder in the PATH environmental variable

Copy the bin folder path: C:\apache-maven-3.9.5\bin and paste in the PATH environmental variable

![image](https://github.com/luiscoco/Java_with_Maven_Sample/assets/32194879/1dd0f932-8561-4651-b28d-3b6dc6473012)

![image](https://github.com/luiscoco/Java_with_Maven_Sample/assets/32194879/a7156f52-3172-4823-bcc8-b5e09ff215b5)

## 3. Verify Maven installation

Run this command to verify the Maven installation

```
mvn -v
```

![image](https://github.com/luiscoco/Java_with_Maven_Sample/assets/32194879/0ce8a441-d30e-46a4-b01c-2edf06a06447)

**IMPORTANT NOTE:** We already installed before "C:\Program Files\Java\jdk-1.8\jre"

![image](https://github.com/luiscoco/Java_with_Maven_Sample/assets/32194879/ca78766b-9c67-4b4a-9b5b-af813f93f672)

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

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/77d02450-df17-448d-9507-15afb4fa7231)

To run the application execute the command:

```
mvn exec:java 
```

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/3c11bd70-7f34-4c6b-8595-176dd4584e5c)
