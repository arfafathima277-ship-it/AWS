# Amazon S3 (Simple Storage Service)

## What is Amazon S3?

Amazon Simple Storage Service (Amazon S3) is an object storage service provided by AWS that is used to store and retrieve any amount of data from anywhere over the internet.

S3 stores data as **objects**, and these objects are stored inside **Buckets**.

---

# Why Amazon S3?

Amazon S3 is widely used for:

- Static website hosting
- Backup and recovery
- Data archiving
- Log storage
- Media storage
- Disaster Recovery
- Big Data Analytics

---

# Key Features

- Highly Scalable
- Highly Durable
- Secure Storage
- Object Storage
- Versioning
- Lifecycle Policies
- Replication
- Multiple Storage Classes
- Pay-as-you-go Pricing

---

# S3 Terminology

## Bucket

A Bucket is a container used to store objects in Amazon S3.

Bucket names:

- Must be globally unique
- Created in a specific AWS Region
- Cannot be renamed after creation

---

## Object

An Object is any file stored inside an S3 Bucket.

Examples:

- Images
- Videos
- PDF Files
- HTML Files
- Documents
- Backup Files

Maximum object size:

**5 TB**

---

# Durability and Availability

Amazon S3 provides:

- **99.999999999% (11 9's) Durability**
- **99.99% (4 9's) Availability**

Durability ensures that your data is protected against hardware failures, while availability ensures that your data is accessible whenever required.

---

# Fine-Grained Access Control

Amazon S3 provides fine-grained access control using:

- IAM Policies
- Bucket Policies
- Access Control Lists (ACLs)

By default, AWS blocks public access to newly created buckets for better security.

---

# Multipart Upload

Multipart Upload allows a large object to be divided into multiple smaller parts and uploaded simultaneously.

Benefits:

- Faster uploads
- Better reliability
- Resume interrupted uploads
- Efficient handling of large files

---

# Encryption

Amazon S3 supports encryption to secure data.

## Encryption in Transit

Protects data while it is transferred between the client and AWS using HTTPS/SSL.

---

## Encryption at Rest

Protects data stored inside Amazon S3.

Types:

### Server-Side Encryption (SSE)

AWS encrypts the data after it reaches Amazon S3.

### Client-Side Encryption (CSE)

The client encrypts the data before uploading it to Amazon S3.

---

# Replication

Amazon S3 supports automatic replication of objects.

## Same Region Replication (SRR)

Copies objects between buckets within the same AWS Region.

Use Cases:

- Compliance
- Log aggregation

---

## Cross Region Replication (CRR)

Copies objects between buckets located in different AWS Regions.

Use Cases:

- Disaster Recovery
- Global applications
- Backup across Regions

---

# Amazon S3 Storage Classes

## S3 Standard

- Frequently accessed data
- Low latency
- High availability

Examples:

- Websites
- Mobile Applications
- Frequently accessed files

---

## S3 Intelligent-Tiering

Automatically moves objects between different access tiers based on usage patterns to optimize storage costs.

---

## S3 Standard-Infrequent Access (Standard-IA)

- For data that is accessed less frequently
- Lower storage cost
- Minimum storage duration: **30 days**

---

## S3 One Zone-Infrequent Access (One Zone-IA)

- Stores data in a single Availability Zone
- Lower cost than Standard-IA
- Suitable for non-critical data

---

## S3 Glacier Flexible Retrieval

Designed for long-term archival storage.

Minimum storage duration:

**90 days**

---

## S3 Glacier Deep Archive

Lowest-cost storage class for long-term archival.

Minimum storage duration:

**180 days**

---

# Lifecycle Policies

Lifecycle Policies automatically transition or delete objects based on predefined rules.

Examples:

- Move objects to Glacier after a specified number of days.
- Delete old backups automatically.

Benefits:

- Cost Optimization
- Automated Storage Management

---

# Versioning

Versioning allows multiple versions of the same object to be stored in an S3 Bucket.

Benefits:

- Recover deleted files
- Restore previous versions
- Track changes made to objects

Each version receives a unique **Version ID**.

---

# Common Use Cases

- Website Hosting
- Backup and Recovery
- Application Logs
- Image and Video Storage
- Software Distribution
- Data Archiving
- Disaster Recovery

---

# Interview Questions

### What is Amazon S3?

Amazon S3 is an object storage service used to store and retrieve any amount of data from anywhere.

---

### What is a Bucket?

A Bucket is a container used to store objects in Amazon S3.

---

### What is an Object?

An Object is a file stored inside an S3 Bucket.

---

### What is the maximum object size in Amazon S3?

**5 TB**

---

### What is Multipart Upload?

Multipart Upload divides a large object into multiple smaller parts and uploads them simultaneously for better performance and reliability.

---

### What is Versioning?

Versioning stores multiple versions of the same object, allowing recovery of deleted or modified files.

---

### What is a Lifecycle Policy?

A Lifecycle Policy automatically moves or deletes objects based on predefined rules.

---

### What is the difference between SRR and CRR?

**SRR (Same Region Replication):**

Replicates objects within the same AWS Region.

**CRR (Cross Region Replication):**

Replicates objects to another AWS Region.

---

### Name the Amazon S3 Storage Classes.

- S3 Standard
- S3 Intelligent-Tiering
- S3 Standard-IA
- S3 One Zone-IA
- S3 Glacier Flexible Retrieval
- S3 Glacier Deep Archive

---

# Summary

- Amazon S3 is an object storage service.
- Data is stored as objects inside buckets.
- Maximum object size is 5 TB.
- S3 provides 99.999999999% durability and 99.99% availability.
- Supports Multipart Upload, Versioning, Replication, Lifecycle Policies, and Encryption.
- Multiple storage classes help optimize cost based on access patterns.