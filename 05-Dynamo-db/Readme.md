# Amazon DynamoDB

## What is DynamoDB?

Amazon DynamoDB is a **fully managed NoSQL database service** provided by AWS. Unlike relational databases, DynamoDB does not use the traditional table-row-column relationship like SQL databases. Instead, it stores data as **items** (similar to JSON documents) inside tables.

It is designed for applications that require **high performance, scalability, and low latency**.

---

# Features of DynamoDB

- **Fully Managed Service**
  - AWS manages the infrastructure, scaling, software patching, backups, and maintenance.
  - No server management is required.

- **Automatic Scaling**
  - Automatically scales read and write capacity based on application traffic.

- **High Availability**
  - Data is automatically replicated across multiple Availability Zones (AZs) within an AWS Region to ensure high availability and fault tolerance.

- **Security**
  - Supports fine-grained access control using AWS IAM policies.
  - Provides encryption at rest and encryption in transit.

- **Backup and Restore**
  - Supports on-demand backups and point-in-time recovery (PITR).
  - Allows restoring deleted or modified data.

---

# DynamoDB Data Types

## 1. String (S)

Stores a sequence of Unicode characters.

**Example**

```json
{
  "Name": "Arfa"
}
```

---

## 2. Number (N)

Stores numeric values.

- Integer
- Floating-point
- Positive
- Negative
- Zero

**Example**

```json
{
  "Age": 23,
  "Salary": 50000
}
```

---

## 3. List (L)

An ordered collection of values.

A list can contain different data types, including nested lists and maps.

**Example**

```json
{
  "Skills": [
    "Linux",
    "AWS",
    "Docker"
  ]
}
```

---

## 4. Map (M)

An unordered collection of key-value pairs.

Similar to a JSON object.

**Example**

```json
{
  "Address": {
    "City": "New York",
    "ZipCode": "10001"
  }
}
```

---

## 5. Boolean (BOOL)

Stores either **true** or **false**.

**Example**

```json
{
  "UserID": "12345",
  "UserName": "John",
  "Active": true
}
```

---

# DynamoDB Global Tables

DynamoDB Global Tables replicate your table automatically across multiple AWS Regions.

### Benefits

- Multi-region replication
- Low latency for global users
- Disaster recovery
- High availability

**Example**

```
India Region
      │
      │
      ▼
US Region
      │
      ▼
Europe Region
```

If data is updated in one region, the changes are automatically replicated to the other configured regions.

---

# DynamoDB Streams

DynamoDB Streams capture changes made to items in a table in real time.

The stream records:

- INSERT
- MODIFY
- REMOVE (Delete)

This feature is useful for triggering downstream processes whenever data changes.

---

# Integration with AWS Lambda

DynamoDB Streams can trigger an AWS Lambda function whenever data changes in a table.

### Workflow

```
User
   │
   ▼
DynamoDB Table
   │
   ▼
DynamoDB Stream
   │
   ▼
AWS Lambda
```

Example use cases:

- Send notifications
- Update another database
- Process orders
- Audit logging

---

# DynamoDB Time to Live (TTL)

Time to Live (TTL) automatically deletes expired items from a DynamoDB table.

You specify an expiration timestamp for each item. Once the time is reached, DynamoDB removes the item automatically.

### Benefits

- Reduces storage costs
- Automatically removes outdated data
- No manual cleanup required

**Example**

If a TTL of **40 days** is set, any item older than 40 days is automatically deleted.

---

# DynamoDB Integrations

DynamoDB integrates with several AWS services, including:

- AWS Lambda
- Amazon Kinesis
- Amazon S3
- Amazon CloudWatch
- AWS IAM
- Amazon API Gateway
- AWS Glue
- Third-party tools

---

# DynamoDB Transactions

DynamoDB supports ACID transactions, allowing multiple read or write operations to be completed as a single unit.

If one operation fails, the entire transaction is rolled back.

## ACID Properties

### Atomicity

All operations succeed or all fail together.

---

### Consistency

Ensures data remains valid before and after the transaction.

---

### Isolation

Concurrent transactions do not interfere with one another.

---

### Durability

Once committed, data is permanently stored even if failures occur.

---

### Conditional Writes

Transactions support conditional updates and deletes.

Example:

Update an item only if:

```
Balance >= 1000
```

Otherwise, the transaction fails.

---

# CRUD Operations

DynamoDB supports standard CRUD operations.

## Create

Add a new item to a table.

---

## Read

Retrieve data from a table.

---

## Update

Modify an existing item.

---

## Delete

Remove an item from a table.

---

# DynamoDB Accelerator (DAX)

Amazon DynamoDB Accelerator (DAX) is a fully managed, in-memory cache for DynamoDB.

It improves read performance by serving frequently accessed data directly from memory instead of querying the database.

### Benefits

- Microsecond response times
- Handles millions of requests per second
- Reduces read latency
- Improves application performance

### Architecture

```
Application
      │
      ▼
DAX Cache
      │
      ▼
DynamoDB
```

---

# Advantages of DynamoDB

- Fully managed service
- Serverless
- Automatic scaling
- High availability
- Low latency
- Secure with IAM integration
- Backup and restore support
- Global Tables
- DynamoDB Streams
- TTL support
- ACID transactions
- DAX caching support

---

# Interview Questions

1. What is Amazon DynamoDB?
2. Is DynamoDB SQL or NoSQL?
3. Why is DynamoDB called a fully managed service?
4. What are the features of DynamoDB?
5. What are the supported data types?
6. What are Global Tables?
7. What is DynamoDB Streams?
8. How does DynamoDB integrate with AWS Lambda?
9. What is Time to Live (TTL)?
10. What are ACID properties?
11. What are DynamoDB transactions?
12. What is DAX?
13. What are CRUD operations?
14. How is DynamoDB different from Amazon RDS?
15. What are the advantages of DynamoDB?