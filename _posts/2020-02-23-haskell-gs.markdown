---
layout: post
title: "Haskell Getting Started"
date: 2020-02-23
categories: programming
---

Haskell is a pure functional language

<!-- more -->

## Haskell

- Created in 1987 by enthusiasts to help increase the productivity and accuracy
- Pure Functional Language
  - Functions are first class member, that is functions can be used like any other values.
  - Expressions never have "_side-effects_"
  - Functions will always return same output for same input.
  - _referential transparency_ - No Mutation ! this comes handy when working with concurrency.
- Lazy
  - Haskell expressions are not evaluated until their results are needed.
  - Helps in working with infinite data structures
  - _wholemeal programming_ - a more compositional programming style
- Statically typed
  - Apart from being Statically typed, haskell is an expressive language (that makes it different form java, c++)
- Concise
  - A 5M lines of code in Java can be written in 1M lines in Haskell
- Speed
  - As fast as ( sometimes more ) Java, C++
    - directly to native
    - abstraction provides multicore & parallel processing.

## Stack

Stack is a cross-platform program for developing Haskell projects. It is aimed at Haskellers both new and experienced.

It features:

- Installing GHC automatically, in an isolated location.
- Installing packages needed for your project.
- Building your project.
- Testing your project.
- Benchmarking your project.

### Installation

`curl -sSL https://get.haskellstack.org/ | sh`

### Create a new project

- `stack new <project_name>` will create a new directory.

#### stack.yaml

Once a project is created you'll see **stack.yaml** file created, and few others like LICENSE, <project_name>.cabal, Setup.hs.
stack.yaml has a field "resolver", it tells you which version of ghci you want to use.

### Building

```sh
    stack setup
    stack build
    stack exec <project_name_exe>
```

> notice the project_name_exe : this is mentioned in <project_name>.cabal file as executable.

### Project structure

project is built, tested and managed via the <project_name>.cabal file. Here you can mention the libraries, packages to include.

#### cabal file

```haskell
library
  hs-source-dirs:      src
  exposed-modules:
    Lib
```

Among the configuration files, you will also see a directory structure:
![directory_struct](directory-structure.png)

This is the default structure of the project, but can be changed with respective changes in cabal file.

## Code

Add code to src library ( or the one mentioned in cabal file _(Library->hs-source-dirs)_.

### module

modules are like packages in java. or modules in java 9. You can expose them as library for others to use. publish them to hackage too.

```haskell
module <module_name> (exposed functions) where
    {-- code here --}
```

### function

function, like any expression in haskell, has a signature and a type.

**Declaration**

```haskell
func :: Int -> Int
```

Here func takes an argument of the type Int and returns Int
