# AWS ElastiCache

## What is Caching?

Caching is the process of storing frequently accessed data in a high-speed memory so that applications can retrieve it quickly instead of repeatedly fetching it from a slower database.

It improves application performance, reduces latency, and decreases the load on backend databases.

---

# What is AWS ElastiCache?

Amazon ElastiCache is a **fully managed in-memory caching service** provided by AWS. It helps applications run faster by storing frequently accessed data in memory, allowing applications to retrieve data with very low latency.

Instead of requesting data from a database every time, the application first checks the cache. If the data is available, it is returned immediately.

---

# How ElastiCache Works

```
Client
   │
   ▼
Application
   │
   ▼
ElastiCache
   │
(Cache Hit)
   │
Response

(Cache Miss)
   │
   ▼
Database
   │
   ▼
ElastiCache
   │
   ▼
Application
```

---

# Cache Engines Supported

Amazon ElastiCache supports two caching engines:

## 1. Redis

Redis is an advanced in-memory data store that supports multiple data structures.

### Features

- Supports Strings, Lists, Sets, Hashes, and Sorted Sets
- Data persistence
- Replication
- High availability
- Automatic failover
- Pub/Sub messaging
- Cluster mode support

Redis is suitable for applications requiring high availability and advanced features.

---

## 2. Memcached

Memcached is a simple, high-performance distributed caching system.

### Features

- Key-value storage
- Multi-threaded
- Extremely fast
- Easy to scale horizontally
- No persistence
- No replication

Memcached is ideal for simple caching workloads.

---

# Redis vs Memcached

| Redis | Memcached |
|--------|-----------|
| Supports multiple data types | Supports only key-value pairs |
| Data persistence | No persistence |
| Replication supported | No replication |
| Automatic failover | No failover |
| Rich feature set | Simple and lightweight |
| Suitable for complex applications | Suitable for simple caching |

---

# Features of Amazon ElastiCache

## Fully Managed

AWS manages:

- Infrastructure
- Software updates
- Monitoring
- Maintenance
- Automatic backups (Redis)
- Scaling

---

## Scalable

- Easily increase or decrease cache capacity.
- Supports both vertical and horizontal scaling.

---

## High Performance

- Stores data in memory.
- Microsecond response time.
- Reduces database load.

---

## High Availability

Redis supports:

- Multi-AZ deployment
- Automatic failover
- Replication

---

## Cost Effective

- Pay only for the resources you use.
- Reduces database usage and improves overall efficiency.

---

# Use Cases

## Web Application Caching

Cache frequently accessed resources such as:

- HTML pages
- Images
- CSS
- JavaScript
- User sessions

---

## Database Query Caching

Store frequently executed query results to reduce database load.

---

## Session Management

Store user login sessions.

Example:

```
User Login
      │
      ▼
Redis Cache
```

---

## Real-Time Analytics

Store:

- User activity
- Application metrics
- Sensor data
- Clickstream data

---

## Gaming

Store:

- Leaderboards
- Player sessions
- Game statistics

---

## E-Commerce

Cache:

- Product catalog
- Shopping cart
- Frequently viewed products

---

# Getting Started with Amazon ElastiCache

1. Sign in to the AWS Management Console.
2. Open the **Amazon ElastiCache** service.
3. Click **Create Cache**.
4. Select a cache engine:
   - Redis
   - Memcached
5. Choose:
   - Node type
   - Cluster configuration
   - VPC
   - Security Group
6. Review the configuration.
7. Create the cache cluster.

---

# Caching Strategies

## 1. Cache-Aside (Lazy Loading)

The application first checks the cache.

- Cache Hit → Return data.
- Cache Miss → Read from the database and store it in the cache.

### Flow

```
Application
      │
      ▼
Cache
 │         │
Hit      Miss
 │         ▼
 │     Database
 │         ▼
 └──── Store in Cache
```

---

## 2. Write-Through Cache

Whenever data is written to the database, it is also written to the cache.

### Advantages

- Cache always contains updated data.
- Fewer cache misses.

### Disadvantage

- Slightly slower write operations.

---

## 3. Cache Eviction Policy

When the cache becomes full, older data is removed.

Common Redis eviction policies include:

- LRU (Least Recently Used)
- LFU (Least Frequently Used)
- Random
- TTL-based eviction

---

## 4. Cache Warming

Preload frequently accessed data into the cache before the application receives traffic.

Benefits:

- Faster application startup
- Lower latency

---

## 5. Data Serialization

Convert objects into a compact format before storing them.

Benefits:

- Saves memory
- Improves cache performance

---

## 6. Connection Pooling

Reuse existing connections between the application and cache.

Benefits:

- Lower latency
- Better performance
- Reduced connection overhead

---

## 7. Sharding

Distribute data across multiple cache nodes.

Benefits:

- Improved scalability
- Higher throughput
- Better fault tolerance

---

## 8. Time To Live (TTL)

Each cache item can have an expiration time.

After the TTL expires, the item is automatically removed.

Benefits:

- Prevents stale data
- Frees memory automatically

---

## 9. Cache Invalidation

Remove or refresh cache entries whenever the source data changes.

Benefits:

- Prevents outdated information
- Improves data consistency

---

## 10. Monitoring

Monitor cache performance using Amazon CloudWatch.

Important metrics:

- Cache Hit Rate
- Cache Miss Rate
- CPU Utilization
- Memory Usage
- Network Traffic
- Evictions

---

## 11. Cost Optimization

Regularly review:

- Node size
- Cache usage
- Hit ratio
- Cluster configuration

This helps avoid unnecessary costs.

---

# Redis Cluster Modes

Amazon ElastiCache for Redis supports two cluster modes.

---

## Cluster Mode Enabled

Redis Cluster distributes data across multiple shards.

### Features

- Automatic sharding
- High availability
- Replication
- Automatic failover
- Horizontal scaling
- Handles large datasets

Suitable for:

- Large applications
- High traffic
- Global applications

---

## Cluster Mode Disabled

Redis runs as a single primary node.

### Features

- No automatic sharding
- Simpler architecture
- Easier management
- Lower operational complexity

Suitable for:

- Small applications
- Development environments
- Low traffic workloads

---

# Cluster Mode Comparison

| Feature | Cluster Enabled | Cluster Disabled |
|----------|----------------|------------------|
| Sharding | Yes | No |
| Horizontal Scaling | Yes | No |
| High Availability | Yes | Limited |
| Automatic Failover | Yes | Replica-based only |
| Large Dataset Support | Yes | Limited |
| Complexity | Higher | Lower |

---

# Choosing the Right Cluster Mode

Choose **Cluster Mode Enabled** if:

- Your application has high traffic.
- You need horizontal scaling.
- You require automatic failover.
- Your dataset is very large.

Choose **Cluster Mode Disabled** if:

- Your workload is small.
- You want a simpler setup.
- High scalability is not required.

---

# Advantages of Amazon ElastiCache

- Fully managed service
- Extremely low latency
- Improves application performance
- Reduces database load
- Supports automatic scaling
- High availability
- Secure with VPC and IAM integration
- Supports Redis and Memcached
- Cost-effective
- Easy integration with AWS services

---

# Common AWS Integrations

Amazon ElastiCache integrates with:

- Amazon EC2
- AWS Lambda
- Amazon RDS
- Amazon DynamoDB
- Amazon CloudWatch
- Amazon API Gateway
- Amazon ECS
- Amazon EKS

---

# Interview Questions

1. What is Amazon ElastiCache?
2. What is caching?
3. Why is caching used?
4. What is the difference between Redis and Memcached?
5. What is Cache-Aside caching?
6. What is Write-Through caching?
7. What is Time To Live (TTL)?
8. What is cache invalidation?
9. What is sharding?
10. What is cache warming?
11. What is Redis Cluster?
12. What is the difference between Cluster Mode Enabled and Disabled?
13. What is a Cache Hit and Cache Miss?
14. How does ElastiCache improve application performance?
15. Which AWS services integrate with ElastiCache?