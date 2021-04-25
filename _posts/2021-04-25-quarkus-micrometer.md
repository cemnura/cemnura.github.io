---
layout: post
title: "Quarkus Micrometer with New Relic & Datadog"
permalink: /quarkus-micrometer/
---

# Micrometer

In a distributed microservice architecture tracking application metrics in production and settings alarms to give better insight to problems within the system is crucial.
There are many systems and tools you can use to track application metrics.

Choosing the correct tool is critical and might change threw out the years of a large distributed application.
Normally, if we were required to change the monitoring service, we would take a deep breath and change the whole system accordingly.
Imagine as the number of services grew changing the monitoring service cost would increase in parallel.

[Micrometer](https://micrometer.io/) is a vender-neutral application metric facade allowing JVM-based applications to connect and send data to monitoring services without vendor any vendor lock-ins.

This means in order to change to metric monitoring system we are using, we would only have to change the Micrometer facade.
This would ease our minds about vendor locking and greatly decrease the cost of changing the monitoring system we are using.



## Micrometer Supported System

1. Datadog
2. New Relic
3. Prometheus 
4. StatsD
5. Google Stackdriver