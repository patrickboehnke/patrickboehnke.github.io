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
'THE SYSTEM IS DOWN!'... F*ck, where are my glasses... Why did I turn my computer off?... Theres blocking in the database... Which database? Which server? All my metrics tell me is blocking... somewhere... But where?... There's 100 SQL servers... 5 hours later... Found it!

That's what happens when your metrics have labels with only low **cardinality**. You can't relate a specific metric to a specific place or application/service. Let's try this again with high **cardinality** metrics.

'THE SYSTEM IS DOWN!'... F*ck, where are my glasses... Why did I turn my computer off?... Theres blocking in the main customer database in our primary SQL server in the Central US... Let me log in and kill that query... Done and back to bed.

With high **cardinality** you can relate every measured value to its origin. 
