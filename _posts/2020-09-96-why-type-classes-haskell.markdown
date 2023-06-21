---
layout: post
title: "Haskell Type signatures"
date: 2020-09-06
categories:
  - "code"
---

Haskell is static typed language, that means it has to know all the types at compile time and not runtime.
But in certain cases like polymorphism, Haskell does something smart to assess the type, through type inference.

<!-- more -->

When you type in your GHCi prompt `:t "Hello" ` you would see an output as :

```
"Hello": [Char]
```

But when you type the command `:t 13 ` you would see:

```
13 :: Num a => a
```

Strange ! why not Integer ? because Haskell doesn't know it yet, whether it is an Integer or a Fraction. So it will select the broadest polymorphic type to represent 13 here.
