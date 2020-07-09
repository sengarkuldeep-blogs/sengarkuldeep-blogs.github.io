---
layout: post
title: "JShell & experimenting JDK features in MacOS"
date: 2020-07-09
categories:
  - "code"
---

With the six monthly release cadence of java, it is of paramount that we can experiment with its EarlyAccess releases quickly and on an ongoing process. Otherwise with the pace java is moving, keeping up with it would be difficult.
And Jshell seems to me to be a very good tool to those experimentations.

<!-- more -->

## Jshell

JShell is an REPL(Read Evaluate Print Loop) tool provided by Java with its JDK9. It is an interactive tool to learn java and protoype code.

**How to run**
Simple run `jshell` from command line

> If want to experiment with preview feature include --enable-preview

## Java EarlyAccess releases

You can download Early Access releases from [openjdk](http://openjdk.java.net/)

## Setup environment

I use mac and for managing I do following things:

1. Download and extract the jdk to _/Library/Java/JavaVirtualMachines/_
2. Run `` export JAVA_HOME=`/usr/libexec/java_home -v 16` ``
   > java_home is out of the box utility provided to list all or specific version of jdk. If you are not on Mac simply export the exact location of the extracted jdk

I've configured profile rc to wrap this on in command like: `usejava 16`

## Using jshell

**confirm the version**

```sh
    jshell --version
```

### Experiment

```
    jshell> Thread.startVirtualThread(()-> System.out.println("Hello, World!"));
    Hello, World!
    $2 ==> VirtualThread[<unnamed>,<no carrier thread>]
```
