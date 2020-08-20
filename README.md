TDLight Java [![Build Status](https://travis-ci.org/tdlight-team/tdlight-java.svg?branch=dev)](https://travis-ci.org/tdlight-team/tdlight-java)
====================

A barebone java wrapper for TDLib (and TDLight)

This wrapper gives you direct access to TDLib API in Java.

## Requirements
JVM: Oracle JVM and OpenJDK

Java versions: Java 10, 11, 12, 13, 14

Operating system: Windows, Linux

Supported CPU architectures: amd64 (linux, windows), aarch64 (linux)

Required libraries for linux: OpenSSL and zlib

## Including TDLight in a project
Maven configuration example to use this version of tdlight-java:
```xml
<repositories>
  <repository>
    <id>tdlight-gihtub</id>
    <name>GitHub TDLight Team Apache Maven Packages</name>
    <url>https://maven.pkg.github.com/tdlight-team/tdlight-java</url>
  </repository>
</repositories>

<dependencies>
  <dependency>
    <groupId>it.tdlight</groupId>
    <artifactId>tdlight-java</artifactId>
    <version>REPLACE_WITH_LATEST_VERSION</version>
  </dependency>
</dependencies>
```
Gradle configuration example to use this version of tdlight-java:
```groovy
repositories {
     maven { url "https://maven.pkg.github.com/tdlight-team/tdlight-java" }
}
dependencies {
     implementation 'it.tdlight:tdlight-java:REPLACE_WITH_LATEST_VERSION'
}
```

Replace `REPLACE_WITH_LATEST_VERSION` with the latest version of tdlight, you can find it on the **Releases** tab on github.

## Usage
Simple initialization of a native TDLib client
```java
import java.io.File;

import it.tdlight.tdlight.Client;
import it.tdlight.tdlight.Init;
import it.tdlight.tdlight.Log;

public class Example {
    public static void main(String[] args) {
        // Initialize TDLight native libraries
        Init.start();

        // Set TDLib log level to 1
        Log.setVerbosityLevel(1);

        // Uncomment this line to print TDLib logs to a file
        // Log.setFilePath("logs" + File.separatorChar + "tdlib.log");
        
        Client client = new Client();
        
        // Initialize the TDLib client
        client.initializeClient();

        // Now you can use the client
    }
}
```

### TDLib methods documentation
[TdApi class javadoc](https://tdlight-team.github.io/tdlib-docs)

## About
#### License
TDLight is licensed by Andrea Cavalli <andrea@cavallium.it> under the terms of the GNU Lesser General Public License 3

### Libraries licenses

JTDlib is licensed by Ernesto Castellotti <erny.castell@gmail.com> under the terms of the GNU Lesser General Public License 3

TDLib is licensed by Aliaksei Levin <levlam@telegram.org> and Arseny Smirnov <arseny30@gmail.com> under the terms of the Boost Software License				

OpenSSL is licensed under the terms of Apache License v2

Zlib is licensed under the terms of Zlib license