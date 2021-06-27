---
layout: post
title: Cardinality Myth Busting
date: June 24, 2021
---

# What we're covering
- What **cardinality** means
- That you don't need any one dimension to be high **cardinality**

# What is **Cardinality**
**Cardinality** is a measure of the number of distinct elements in a group. In a monitoring/telemetry context consider the server type (e.g., web or database) versus a unique identifier. The former is low **cardinality** while the latter is high **cardinality**.

# Why you should care about **cardinality**
'THE SYSTEM IS DOWN!'... F*ck, where are my glasses... Why did I turn my computer off?... Theres blocking in the database... Which database? Which server? All my metrics tell me is blocking... somewhere... But where?... There's 100 SQL servers... 2 hours later... Found it!

That's what happens when your metrics have labels with only low **cardinality**. You can't relate a specific metric to a specific place or application/service. Let's try this again with high **cardinality** metrics.

Zzzzzzz... Zzzzzz...

That's right you never got woken up. The operations team was able to track the failure to its source and remediate it.

# How do we get high **cardinality**?
## A single high **cardinality** dimension
The most common way I've seen for having enough **cardinality** is to have one or more unique identifier(s) for every metric emitting entity. This could be a combination of UUID for the server and another one for the micro-service or application. When it works, this approach is simple and efficient. In principle you only need to store three or four labels and the metric value.

There are drawbacks, however, is that without storing a mapping of identifiers to a human readable format this approach won't work. If your technology is capable of joining different datasets together then a simple solution is to keep one set of human readable labels and join it to the measured data. If that's not an option then adding human readable labels to everything is going to get [expensive] (https://patrickboehnke.github.io/OpenTelemetryMetrics/)
## Multiple low-medium **cardinality dimensions
The other approach for getting high **cardinality**
