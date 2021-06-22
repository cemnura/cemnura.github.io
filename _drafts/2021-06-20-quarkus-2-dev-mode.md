---
layout: post
title: "A Day of in a life of a Quarkus Developer"
permalink: /quarkus-v2/
---

# A Day of in a life of a Quarkus 2 Developer

The upcoming Quarkus 2 release is bringing a new level of Developer Joy.
Previously, Quarkus developers were enlightened with live reloading witch in itself is a pretty outstanding way to develop a Java microservice.
Quarkus 2 is bringing the continuous testing which will enable developers to run unit test in a live reloading fashion.

# Morning

After his daily routine, a quarkus developer boots his computer and opens his project in his preferable IDE.
The developer then opens his terminal and

``./mvnw clean quarkus:dev``

the developer is greated

```
__  ____  __  _____   ___  __ ____  ______
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/
 -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/
2021-06-22 08:49:20,919 INFO  [io.quarkus] (Quarkus Main Thread) my-awesome-app 1.0.0-SNAPSHOT on JVM (powered by Quarkus 2.0.0.CR3) started in 2.483s. Listening on: http://localhost:8080
2021-06-22 08:49:20,923 INFO  [io.quarkus] (Quarkus Main Thread) Profile dev activated. Live Coding activated.
2021-06-22 08:49:20,924 INFO  [io.quarkus] (Quarkus Main Thread) Installed features: [cdi, resteasy, resteasy-jackson, smallrye-context-propagation]

--
Tests paused, press [r] to resume
```

The developers awesome project has started up and is ready to start the day of coding. 
The developer, which had forgotten the last state he left his code decides to run his tests.

## So, the developer presses **[r]**

```
Running 0/2. Running: org.acme.awesome.GreetingResourceTest#testHelloEndpoint()
Running Tests for the first timeWARNING: An illegal reflective access operation has occurred
WARNING: Illegal reflective access by org.codehaus.groovy.vmplugin.v9.Java9 (file:/Users/cemnura/.m2/repository/org/codehaus/groovy/groovy/3.0.8/groovy-3.0.8.jar) to constructor java.lang.AssertionError(java.lang.String)
2021-06-22 09:05:36,678 <span style="color:red">ERROR</span> [io.qua.test] (Test runner thread) ==================== TEST REPORT #1 ====================
2021-06-22 09:05:36,679 <span style="color:red">ERROR</span> [io.qua.test] (Test runner thread) Test GreetingResourceTest#testHelloEndpoint() failed 
: java.lang.AssertionError: 1 expectation failed.
Response body doesn't match expectation.
Expected: is "zello"
  Actual: hello

        at io.restassured.internal.ValidatableResponseImpl.body(ValidatableResponseImpl.groovy)
        at org.acme.awesome.GreetingResourceTest.testHelloEndpoint(GreetingResourceTest.java:21)

2021-06-22 09:05:36,682 ERROR [io.qua.test] (Test runner thread) >>>>>>>>>>>>>>>>>>>> 1 TESTS FAILED <<<<<<<<<<<<<<<<<<<<

--
1 tests failed (1 passing, 0 skipped), 2 tests were run in 3475ms.

```
