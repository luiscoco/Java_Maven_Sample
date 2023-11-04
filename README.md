# Java Maven Sample

## 1. Download and install Apache Maven

Download Apache Maven from the web page: https://maven.apache.org/download.cgi

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/2588a600-4919-4882-935d-f792024793a8)

Unzig the **apache-maven-3.9.5-bin.tar** file and place the folder in the C: root hard disk

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/ab3b37c9-6438-4cba-aaf0-537a2f866916)

## 2. Set the Mavent bin folder in the PATH environmental variable

Copy the bin folder path: **C:\apache-maven-3.9.5\bin** and paste in the **PATH** environmental variable

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/6dba2422-7b73-4443-9a73-5fbd291b0ead)

## 3. Verify Maven installation

Run this command to verify the Maven installation

```
mvn -v
```

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/df7d036f-7c0d-4495-af7b-71225a2bdee1)

**IMPORTANT NOTE:** We already installed before "C:\Program Files\Java\jdk-1.8\jre"

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/e14041f8-794b-4dd3-b5df-27236549fe79)

## 4. Create the Java application in VSCode

Open VSCode

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/99b4263c-3c47-4099-9769-14d9a8c16fa2)

Press the keys **Ctrl+Shift+P** for creating a **new Java application**

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/8b3170f5-28d5-4d02-af12-4f2cf54ca047)

We select **Maven** project type

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/a89c55a0-e633-40f2-8e31-1e639a283654)

We select **No Archetype**

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/8fe04c54-3a13-46d3-9296-af9fdc2b7268)

We set the package name **com.example**

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/b570cb5d-c2cb-4a48-b360-3b61b798322a)

We set the application name

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/99274c64-7d2e-4a4e-a815-7826ec39fbbc)

We select the folder where to place the new Java application

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/91542e3d-5779-4327-81e3-d64db15e2890)

We open the new Java application

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/df4e51c4-59ab-45e0-9881-be3e9d97fd6f)

The original **pom.xml** file not include the **<build>** tag. We will add this tag in the following sections below

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
</project>
```

## 5. Java application source code

```java
package com.example;

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}
```

## 6. Java application pom.xml file

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

## 7. Compile and Run the Java with Maven application

To compile the application run the command:

```
mvn clean install
```

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/1ede466f-8645-4025-88ab-d97b6542eb46)

To run the application execute the command:

```
mvn exec:java 
```

![image](https://github.com/luiscoco/Java_Maven_Sample/assets/32194879/9252e35b-a276-484d-8784-f4297bcad50b)
