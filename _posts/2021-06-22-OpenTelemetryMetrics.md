---
layout: post
title: OpenTelemetry Metrics - Efficient?
---

# What you're getting by reading this
-

# What are Metrics?
**Metrics** are a concept in software telemetry that consists of a single numeric value tracked over time. They are identified by **Labels**, which are descriptive attributes (e.g., hostname, service name, etc). **Metrics** are generally sent to a company providing observability services such as [New Relic](https://newrelic.com/) or [Splunk] (https://www.splunk.com/).

```
  Example:
  CPU utilization on a web server
  Memory usage on a web server
  Page load times
```
# The problem with Metrics
Metrics are fantastic for keeping tabs on your infrastructure. You need to know that your servers have memory available or that they aren't at 100% CPU utilization. But, this usefulness comes with a downside: **metrics** are incredibly inefficient from a storage perspective. For every data point you record you have to store the entire set of labels. This is a problem because a lot of vendors charge based on the volume of ingested data ($/GB).

# Some suggestions for **Metrics**
## Store multiple values in each **metric** entry
This is the easiest and most sensible way to cut down on the ingest data volume. Often times the grouping of data is logical. Infrastructure metrics tend to go together. CPU, memory, disk, and network statistics can be grouped into a single entry.

The downsides are:
1. Your vendor/technology needs to support this
2. It is not consistent with **metrics** best practices

## Use the fewest labels you can
If the first solution wasn't enough or you can't pursue it then the next best option is to eliminate any unnecessary labels from your **metrics**.
