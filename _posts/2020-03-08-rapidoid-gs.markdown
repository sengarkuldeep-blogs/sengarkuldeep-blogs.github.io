---
layout: post
title: "Rapidoid"
date: 2020-03-08
categories: code
---

Rapidoid is extremely fast and lightweight framework for building rest apis. In this post I will be writing how to get started just by writing a few a lines of code.

<!-- more -->

## Introduction

With the advent of microservices and container based platform the need of a very lightweight and fast rest api is of great importance.

Apprantely we all are too well versed with spring-boot, and haven't pulled the neck higher enough to notice that spring-boot is a heavy framework for building rest api that is light and fast.

You can obviously choose to go for no-dependency famework that is old plain java, and Java 9+ does bring a lot to the table. But it needs you to code your own solutions, even the basic tasks like path extractions.

So comes the middle ground, a lightweight, minimal framework that just is enough. We have many like UnderTow, JavaLin, etc. I happen to land on [techempower benchmarks](https://www.techempower.com/benchmarks/#section=data-r12&hw=peak&test=plaintext&a=2), and noticed that rapidoid is the fastest even faster than some of the c++ equivalant.

So this post is to write a simple rest api with Rapidoid.

## Getting started

1. add the following dependency, to you `pom.xml`:

```
<dependency>
<groupId>org.rapidoid</groupId>
<artifactId>rapidoid-quick</artifactId>
<version>5.5.5</version>
</dependency>
```

2. Create a Main class like following:

```java
public class Main {
    public static void main(String[] args) {
         On.get("/").plain("Hello World!");
    }
}
```

And that's your hello world rest api.
