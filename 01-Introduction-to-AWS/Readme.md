# AWS Introduction

## What is Cloud Computing?

Cloud computing is the delivery of computing services such as servers, storage, databases, networking, software, and analytics over the internet instead of using local computers or on-premises infrastructure.

Instead of purchasing and maintaining physical hardware, users can access resources on demand and pay only for what they use.

---

# Key Concepts

## 1. Scalability

Scalability is the ability to increase or decrease computing resources based on application demand.

Example:
- During a festival sale, an e-commerce website receives millions of users.
- Additional servers are added automatically to handle the increased traffic.

---

## 2. Elasticity

Elasticity is the automatic allocation and removal of resources according to the workload.

Example:
- If traffic increases, AWS automatically adds CPU, memory, storage, and network resources.
- When traffic decreases, those resources are removed to reduce costs.

---

# Benefits of Cloud Computing

- Pay only for what you use (Variable Cost Model)
- Faster deployment of applications
- High scalability and elasticity
- No need to purchase or maintain physical servers
- Global infrastructure for worldwide deployment
- High availability and reliability

---

# Cloud Computing Service Models

## 1. Infrastructure as a Service (IaaS)

Provides virtual machines, networking, and storage.

**AWS Example:**
- Amazon EC2

**Customer manages:**
- Operating System
- Applications
- Runtime
- Data

AWS manages:
- Physical servers
- Networking
- Storage hardware

---

## 2. Platform as a Service (PaaS)

Provides a platform to develop and deploy applications without managing infrastructure.

**AWS Examples:**
- AWS Elastic Beanstalk
- Amazon RDS

---

## 3. Software as a Service (SaaS)

Provides complete software applications over the internet.

Examples:
- Amazon Chime
- Gmail
- Microsoft 365

---

# Cloud Deployment Models

## Public Cloud

Infrastructure owned and managed by cloud providers like AWS.

Example:
- Amazon Web Services

---

## Private Cloud

Infrastructure dedicated to a single organization.

Suitable for:
- Banks
- Government organizations
- Healthcare

---

## Hybrid Cloud

Combination of Public Cloud and Private Cloud.

Example:
A company stores sensitive customer data in a private cloud while hosting its website on AWS.

---

## Community Cloud

Shared infrastructure used by multiple organizations with similar security or compliance requirements.

Example:
Government departments sharing cloud infrastructure.

---

# Ways to Access AWS

There are three ways to interact with AWS:

1. AWS Management Console (Web Interface)
2. AWS Command Line Interface (AWS CLI)
3. AWS SDKs (Software Development Kits)

---

# AWS Global Infrastructure

AWS infrastructure consists of:

```
Region
│
├── Availability Zone (AZ)
│      │
│      ├── Data Center
│      ├── Data Center
│
├── Availability Zone
│      │
│      ├── Data Center
│      ├── Data Center
```

### Region

A geographical area where AWS has data centers.

Example:
- ap-south-1 (Mumbai)
- us-east-1 (Virginia)

---

### Availability Zone (AZ)

Each Region contains two or more isolated Availability Zones.

Benefits:
- High Availability
- Fault Tolerance

---

### Data Center

A physical facility containing servers, networking equipment, storage devices, and power systems.

---

# AWS Shared Responsibility Model

AWS follows a Shared Responsibility Model.

## AWS is responsible for (Security **of** the Cloud)

- Physical security
- Hardware
- Networking
- Global Infrastructure
- Hypervisor

## Customer is responsible for (Security **in** the Cloud)

- IAM Users
- Passwords
- Applications
- Data
- Operating System
- Security Groups
- Encryption

---

# Interview Questions

## What is Cloud Computing?

Cloud computing is the delivery of IT resources over the internet with pay-as-you-go pricing.

---

## Difference between Scalability and Elasticity

| Scalability | Elasticity |
|-------------|------------|
| Increases or decreases resources based on demand. | Automatically adjusts resources dynamically. |
| Can be manual or automatic. | Mostly automatic. |

---

## What are the Cloud Service Models?

- IaaS
- PaaS
- SaaS

---

## Name the AWS Global Infrastructure Components.

- Region
- Availability Zone
- Data Center

---

## What is the AWS Shared Responsibility Model?

AWS secures the cloud infrastructure, while customers secure their applications, data, and configurations inside AWS.

---

# Summary

- Cloud Computing
- Scalability
- Elasticity
- Benefits of Cloud
- Service Models (IaaS, PaaS, SaaS)
- Deployment Models
- AWS Access Methods
- AWS Global Infrastructure
- Shared Responsibility Model