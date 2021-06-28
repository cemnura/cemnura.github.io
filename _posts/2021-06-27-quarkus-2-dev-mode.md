---
layout: post
title: "A Day in a life of a Quarkus Developer"
permalink: /quarkus-v2/
---

The upcoming Quarkus 2 release is bringing a new level of Developer Joy.
Previously, Quarkus developers were enlightened with live reloading witch in itself is a pretty outstanding way to develop a Java microservice.
Quarkus 2 is bringing continuous testing feature which will enable developers to run unit test in a live reloading fashion.

## **Morning**

After his morning routine, the quarkus developer boots his computer and opens his project in his preferable IDE.
The developer takes a sip of his coffee and then opens his terminal and

``./mvnw clean quarkus:dev``

the developer is greeted

```
__  ____  __  _____   ___  __ ____  ______
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/
 -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/
2021-06-27 09:00:00,000 INFO  [io.quarkus] (Quarkus Main Thread) my-awesome-app 1.0.0-SNAPSHOT on JVM (powered by Quarkus 2.0.0.CR3) started in 2.483s. Listening on: http://localhost:8080
2021-06-27 09:00:00,000 INFO  [io.quarkus] (Quarkus Main Thread) Profile dev activated. Live Coding activated.
2021-06-27 09:00:00,000 INFO  [io.quarkus] (Quarkus Main Thread) Installed features: [cdi, resteasy, resteasy-jackson, smallrye-context-propagation]

--
Tests paused, press [r] to resume
```

The developers awesome project has started up and is ready to start the day of coding. 
The developer, which had forgotten the last state he left his code decides to run his tests.

# The developer presses **[r]**

```
Running 0/2. Running: org.acme.awesome.GreetingResourceTest#testHelloEndpoint()
Running Tests for the first time
2021-06-27 09:01:00,123 ERROR [io.qua.test] (Test runner thread) ==================== TEST REPORT #1 ====================
2021-06-27 09:01:00,124 ERROR [io.qua.test] (Test runner thread) Test GreetingResourceTest#testHelloEndpoint() failed 
: java.lang.AssertionError: 1 expectation failed.
Response body doesn't match expectation.
Expected: is "zello"
  Actual: hello

        at io.restassured.internal.ValidatableResponseImpl.body(ValidatableResponseImpl.groovy)
        at org.acme.awesome.GreetingResourceTest.testHelloEndpoint(GreetingResourceTest.java:21)

2021-06-27 09:01:03,599 ERROR [io.qua.test] (Test runner thread) >>>>>>>>>>>>>>>>>>>> 1 TESTS FAILED <<<<<<<<<<<<<<<<<<<<

--
1 tests failed (1 passing, 0 skipped), 2 tests were run in 3475ms.
Press [r] to re-run, [v] to view full results, [p] to pause, [h] for more options>
```

The developer shocked by his mistake takes action to fix the problem.

# Coding Intensifies

The developer fixes the problem and observes the following

```
2021-06-27 10:01:20,681 INFO  [io.qua.dep.dev.RuntimeUpdatesProcessor] (Test Compile Timer) Changed source files detected, recompiling GreetingResourceTest.java
2021-06-27 10:01:21,874 WARN  [io.qua.dep.dev.JavaCompilationProvider] (Test Compile Timer) bootstrap class path not set in conjunction with -source 8, line -1 in [unknown source]

--
All 2 tests are passing (0 skipped), 2 tests were run in 791ms.
Press [r] to re-run, [v] to view full results, [p] to pause, [h] for more options>

```

The developer, taking a sip of coffee, sees that the tests have run automatically without even needing to trigger the tests or restart the awesome project.

## **Afternoon**

The developer, triumphing his morning code session is met with a new challenge. 
The already awesome project needs to store data to be even more awesome.

The developer cracks his knuckles and adds the database dependency.

`./mvnw quarkus:add-extension -Dextensions="quarkus-hibernate-orm,quarkus-jdbc-postgresql"`

# The developer strikes **[⏎]** 

# Takes several sips of his coffee

```
Downloading from central: https://repo.maven.apache.org/maven2/io/quarkus/quarkus-hibernate-orm/2.0.0.CR3/quarkus-hibernate-orm-2.0.0.CR3.pom
                                                          .
                                                          .
                                                          .
[INFO] Changes detected to [/Users/cemnura/Documents/github.com/awesome/awesome-project/getting-started/pom.xml], restarting dev mode
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 2 resources
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 3 source files to /Users/cemnura/Documents/github.com/awesome/awesome-project/getting-started/target/classes
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /Users/cemnura/Documents/github.com/awesome/awesome-project/getting-started/src/test/resources
[INFO] Changes detected - recompiling the module!
[INFO] Compiling 2 source files to /Users/cemnura/Documents/github.com/awesome/awesome-project/getting-started/target/test-classes
2021-06-27 13:36:34,110 INFO  [io.quarkus] (Shutdown thread) my-awesome-app stopped in 0.017s

--
Tests paused, press [r] to resume

2021-06-27 13:36:38,837 INFO  [org.tes.doc.DockerClientProviderStrategy] (build-37) Loaded org.testcontainers.dockerclient.UnixSocketClientProviderStrategy from ~/.testcontainers.properties, will try it first
2021-06-27 13:36:39,442 INFO  [org.tes.doc.DockerClientProviderStrategy] (build-37) Found Docker environment with local Unix socket (unix:///var/run/docker.sock)
2021-06-27 13:36:39,443 INFO  [org.tes.DockerClientFactory] (build-37) Docker host IP address is localhost
2021-06-27 13:36:39,490 INFO  [org.tes.DockerClientFactory] (build-37) Connected to docker: 
  Server Version: 20.10.6
  API Version: 1.41
  Operating System: Docker Desktop
  Total Memory: 1987 MB
2021-06-27 13:36:39,492 INFO  [org.tes.uti.ImageNameSubstitutor] (build-37) Image name substitution will be performed by: DefaultImageNameSubstitutor (composite of 'ConfigurationFileImageNameSubstitutor' and 'PrefixingImageNameSubstitutor')
2021-06-27 13:36:41,142 INFO  [org.tes.DockerClientFactory] (build-37) Ryuk started - will monitor and terminate Testcontainers containers on JVM exit
2021-06-27 13:36:41,143 INFO  [org.tes.DockerClientFactory] (build-37) Checking the system...
2021-06-27 13:36:41,143 INFO  [org.tes.DockerClientFactory] (build-37) ✔︎ Docker server version should be at least 1.6.0
2021-06-27 13:36:41,251 INFO  [org.tes.DockerClientFactory] (build-37) ✔︎ Docker environment should have more than 2GB free disk space
2021-06-27 13:36:41,277 INFO  [🐳 .2]] (build-37) Pulling docker image: postgres:13.2. Please be patient; this may take some time but only needs to be done once.
2021-06-27 13:36:43,223 INFO  [🐳 .2]] (docker-java-stream-2078814337) Starting to pull image
2021-06-27 13:36:43,238 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending,  0 downloaded,  0 extracted, (0 bytes/0 bytes)
2021-06-27 13:36:44,097 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers: 13 pending,  1 downloaded,  0 extracted, (1 KB/? MB)
2021-06-27 13:36:46,701 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers: 12 pending,  2 downloaded,  0 extracted, (10 MB/? MB)
2021-06-27 13:36:47,056 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers: 11 pending,  3 downloaded,  0 extracted, (12 MB/? MB)
2021-06-27 13:36:50,189 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers: 10 pending,  4 downloaded,  0 extracted, (26 MB/? MB)
2021-06-27 13:36:51,119 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  9 pending,  5 downloaded,  0 extracted, (30 MB/? MB)
2021-06-27 13:36:51,614 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  8 pending,  6 downloaded,  0 extracted, (33 MB/? MB)
2021-06-27 13:36:53,751 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  7 pending,  7 downloaded,  0 extracted, (42 MB/? MB)
2021-06-27 13:36:54,072 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  6 pending,  8 downloaded,  0 extracted, (43 MB/? MB)
2021-06-27 13:36:54,776 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  5 pending,  9 downloaded,  0 extracted, (46 MB/? MB)
2021-06-27 13:36:55,306 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  5 pending,  9 downloaded,  1 extracted, (50 MB/? MB)
2021-06-27 13:36:55,551 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  5 pending,  9 downloaded,  2 extracted, (51 MB/? MB)
2021-06-27 13:36:55,631 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  5 pending,  9 downloaded,  3 extracted, (51 MB/? MB)
2021-06-27 13:36:55,991 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  5 pending,  9 downloaded,  4 extracted, (52 MB/? MB)
2021-06-27 13:36:56,439 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  4 pending, 10 downloaded,  4 extracted, (55 MB/? MB)
2021-06-27 13:36:56,456 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  4 pending, 10 downloaded,  5 extracted, (55 MB/? MB)
2021-06-27 13:36:56,565 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  4 pending, 10 downloaded,  6 extracted, (56 MB/? MB)
2021-06-27 13:36:56,646 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  4 pending, 10 downloaded,  7 extracted, (56 MB/? MB)
2021-06-27 13:36:56,719 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  4 pending, 10 downloaded,  8 extracted, (56 MB/? MB)
2021-06-27 13:36:57,380 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  3 pending, 11 downloaded,  8 extracted, (59 MB/? MB)
2021-06-27 13:36:57,408 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  2 pending, 12 downloaded,  8 extracted, (59 MB/? MB)
2021-06-27 13:36:58,335 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  1 pending, 13 downloaded,  8 extracted, (63 MB/? MB)
2021-06-27 13:37:09,357 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending, 14 downloaded,  8 extracted, (109 MB/109 MB)
2021-06-27 13:37:12,756 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending, 14 downloaded,  9 extracted, (109 MB/109 MB)
2021-06-27 13:37:12,830 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending, 14 downloaded, 10 extracted, (109 MB/109 MB)
2021-06-27 13:37:12,899 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending, 14 downloaded, 11 extracted, (109 MB/109 MB)
2021-06-27 13:37:12,970 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending, 14 downloaded, 12 extracted, (109 MB/109 MB)
2021-06-27 13:37:13,044 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending, 14 downloaded, 13 extracted, (109 MB/109 MB)
2021-06-27 13:37:13,110 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pulling image layers:  0 pending, 14 downloaded, 14 extracted, (109 MB/109 MB)
2021-06-27 13:37:13,124 INFO  [🐳 .2]] (docker-java-stream-2078814337) Pull complete. 14 layers, pulled in 29s (downloaded 109 MB at 3 MB/s)
2021-06-27 13:37:13,136 INFO  [🐳 .2]] (build-37) Creating container for image: postgres:13.2
2021-06-27 13:37:13,434 INFO  [🐳 .2]] (build-37) Starting container with ID: e36344742041519477a89cc4b468a6e9e85a977adf125c4350c2f5f8f3f0657c
2021-06-27 13:37:14,798 INFO  [🐳 .2]] (build-37) Container postgres:13.2 is starting: e36344742041519477a89cc4b468a6e9e85a977adf125c4350c2f5f8f3f0657c
2021-06-27 13:37:15,956 INFO  [🐳 .2]] (build-37) Container postgres:13.2 started in PT34.704751S
__  ____  __  _____   ___  __ ____  ______ 
 --/ __ \/ / / / _ | / _ \/ //_/ / / / __/ 
 -/ /_/ / /_/ / __ |/ , _/ ,< / /_/ /\ \   
--\___\_\____/_/ |_/_/|_/_/|_|\____/___/   
2021-06-27 13:37:17,444 INFO  [io.quarkus] (Quarkus Main Thread) my-awesome-app 1.0.0-SNAPSHOT on JVM (powered by Quarkus 2.0.0.CR3) started in 39.795s. Listening on: http://localhost:8080
2021-06-27 13:37:17,445 INFO  [io.quarkus] (Quarkus Main Thread) Profile dev activated. Live Coding activated.
2021-06-27 13:37:17,445 INFO  [io.quarkus] (Quarkus Main Thread) Installed features: [agroal, cdi, hibernate-orm, jdbc-postgresql, narayana-jta, resteasy, resteasy-jackson, smallrye-context-propagation]

--
Tests paused, press [r] to resume


```

The maven dependency are downloaded automatically, and a zero config postgres database docker is provided without the need to restart the awesome project.

The developer, reruns the test to see everything is still working.

# The developer presses **[r]**

```
All 2 tests are passing (0 skipped), 2 tests were run in 11131ms.
Press [r] to re-run, [v] to view full results, [p] to pause, [h] for more options>
```

## **More options?**

The developer, astonished that he is still running the same quarkus dev mode he ran in the morning wonders if there is any other feature.

# The developer presses **[h]**

```

The following commands are available:
[r] - Re-run all tests
[f] - Re-run failed tests
[b] - Toggle 'broken only' mode, where only failing tests are run (disabled)
[v] - Print failures from the last test run
[o] - Toggle test output (disabled)
[p] - Pause tests
[i] - Toggle instrumentation based reload (disabled)
[l] - Toggle live reload (enabled)
[s] - Force live reload scan
[h] - Display this help

```

## **Broken Only?**

The developer, in which is about to develop the datastore for the awesome project enables **\'broken only\'** mode.

# The developer presses **[b]**

```
2021-06-27 13:40:00,999 INFO  [io.qua.dep.dev.tes.TestSupport] (Aesh InputStream Reader) Broken only mode enabled
```

# Coding Intensifies

The developer, practitioner of test driven development continues to add the datastore to the awesome project and adds the required test.

```
All 3 tests are passing (0 skipped), 1 tests were run in 1562ms.
```

The developers, previous test were not broken. Therefore, only the additional test was runned.

## **Refactoring**

The technical depth has increased due to intense coding sessions. 
The developer, sees it necessary to do a refactor.
During the refactoring of the awesome project the developer chooses to pause the continuous testing.

# The developer presses **[p]**

```
--
Tests paused, press [r] to resume
```

# Refactoring Intensifies

Pleased with the refactor, to observe where was broken, the developer wishes to run all the tests again which was previously paused. 

# The developer presses **[r]**

```
All 3 tests are passing (0 skipped), 3 tests were run in 1631ms.
```

Amazed that all his test passed on the first try the developer chooses to reassert that his test are passing.

# The developer presses **[v]**

```
2021-06-27 17:58:00,000 INFO  [io.qua.dep.dev.tes.TestSupport] (Aesh InputStream Reader) All tests passed, no output to display
```

## **Evening**

The day is nearing to an end. The developer, feeling accomplished, stretches his arms out while looking at the awesome project chooses to end the day.

## The developer presses **[ctrl + c]**

```
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  08:59 h
[INFO] Finished at: 2021-06-27T17:59:59+03:00
[INFO] ------------------------------------------------------------------------
```
