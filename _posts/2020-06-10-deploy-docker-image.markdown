---
layout: post
title: "Build and Deploy docker images"
date: 2020-06-28
categories:
  - "code"
---

Docker is an open platform for developing, shipping, and running applications. Docker enables you to separate your applications from your infrastructure so you can deliver software quickly.

<!-- more -->

## Build Image

For building image i'm using the gradle+java based code, which is available [here](https://github.com/kuldeepsengar/rapidoid-rest-api)

There are other ways that i've tried to use to build, other than the IDE plugin based ones, like below:

1. Dockerfile: You can either
   1. Build the jar file through gradle and write the Dockerfile to copy the jars and run.
   1. Build the image using Dockerfile
      1. that'll run gradle, generate jars, copy them, and run them
      1. or run gradle within the dockerfile to run the app

**Gradle -> Jar -> Dockerfile**

- Create a task in gradle to copy all the runtime dependencies

  ```gradle
  def dependencyPath = new File("$buildDir/libs/dependency")
  task copyRuntimeLibs(type: Copy) {
      if(!dependencyPath.isDirectory()){
          dependencyPath.mkdirs();
      }
      from configurations.runtimeClasspath
      into dependencyPath

  }
  ```

- Make jar task depend on the **copyRuntimeLibs** task

  ```gradle
  jar {
    dependsOn 'copyRuntimeLibs'
  }
  ```

- In the Dockerfile

  ```Dockerfile
    FROM openjdk:11-jdk
    ARG JAR_FILE=build/libs/*.jar
    ARG DEPENDENCY=build/libs/dependency
    COPY ${JAR_FILE} /app/main.jar
    COPY ${DEPENDENCY} /app/libs
    ENTRYPOINT ["java","-cp","/app/*:/app/libs/*","org.sengarkuldeep.Main"]
  ```
