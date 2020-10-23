# Notes on Refactoring

## CloudWatch Alarms

* A CloudWatch alarm state is configured with three settings:
  - Period (s): The length of time to evaluate the metric to create each individual data point for a metric.
  - Evaluation Period: The number of the most recent data points to evaluate when determining alarm state.
  - Datapoints to Alarm: The number of data points within the Evaluation Period that must be breached to cause an alarm state.

## Managing Session State

There are two options to managing session state
1. Sticky Sessions with Local Session Caching

  This is the pattern where you send the same user to a particular web server for each request. The user session is stored on the web server, and a cookie directs the user to a that particular web server each time.

  Pros:
    - Cost effective
    - Low latency since session is in local memory

  Cons:
    - Scale! If you scale up, you may have unequal load across servers
    - If you lose a server, you are likely to lose the sessions on the server

2. Distributed Session Management

  Abstract session persistence away from the web servers to a specific service. A common solution is to leverage an in-memory cache like Redis or Memcached.

  Pros:
    - They can be used to cache other data in addition to session data
    - They can be accessed from any web server
    - Offer improved reliability through read replicas and distribution across cache nodes.

  Cons:
    - Network latency is added to memory latency; TODO: review latency thumb rules
    - Cost

## ElastiCache

* Whitepaper - [Performance at Scale with Amazon Elasticache](https://d0.awsstatic.com/whitepapers/performance-at-scale-with-amazon-elasticache.pdf)

### [Memcached vs. Redis](https://aws.amazon.com/elasticache/redis-vs-memcached/)

* Memcached:
  - Simple caching model
  - Supports multi-threading: Can handle more operations with increased compute capacity

## RDS

* Read replicas allow for enhanced performance and durability for read-intensive workloads
  - Read replicas can be promoted to master status, useful as part of a sharding implementation
  - You can add indexes to just the read replicas for increased performance
  - A read replica can be in a standby AZ and promoted if the master DB fails
  - The traffic between the main and read replicas is automatically encrypted
