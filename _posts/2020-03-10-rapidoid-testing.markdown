---
layout: post
title: "Testing a Rapidoid rest api"
date: 2020-03-10
categories:
  - "code"
---

In this post i will try to explain how to write an integration test for rest apis written using Rapidoid.

<!-- more -->

To test your rest api, there are two things need to do:

1. extend your test class with [**RapidoidIntegrationTest**](https://github.com/rapidoid/rapidoid/blob/master/rapidoid-commons/src/main/java/org/rapidoid/test/RapidoidIntegrationTest.java)
2. Annotate your test class with [_@IntegrationTest_](https://github.com/rapidoid/rapidoid/blob/master/rapidoid-commons/src/main/java/org/rapidoid/annotation/IntegrationTest.java), and pass the main class parameter.

Something like below:

```java
@IntegrationTest(main = Main.class)
public class UserIntegrationTest extends RapidoidIntegrationTest {
}
```

For writing the test case, it is simple:

- Use **Self** class for performing all the rest calls.

like below:

```java
    @Test
    public void shouldInsertUser() {
        Map<String, ?> user1 = U.map("name", "Kuldeep");
        User user = Self.post("/users").data(user1).toBean(User.class);
        Assert.assertThat(user.getId(), Is.is(1L));
    }
```

In addition to the assertion api provided by Junit, **RapidoidTest** provides some sugarcoated methods for assertion.
