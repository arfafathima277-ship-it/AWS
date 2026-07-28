# AWS VPC (Virtual Private Cloud)

## What is Networking?

Networking is the process of connecting two or more devices (computers, servers, laptops, mobile phones, printers, etc.) so they can communicate and share data.

### Types of Networks

### 1. LAN (Local Area Network)
- Covers a small geographical area.
- Used in homes, schools, and offices.
- High speed and low latency.

**Example:** Office network or home Wi-Fi.

### 2. WAN (Wide Area Network)
- Covers a large geographical area.
- Connects multiple LANs together.
- The Internet is the largest WAN.

**Example:** Company branches connected across different cities.

---

# What is a Network?

A network is a collection of connected devices that communicate and exchange data with each other.

---

# What is AWS VPC?

**VPC (Virtual Private Cloud)** is a logically isolated virtual network in AWS where you can securely launch and manage AWS resources.

Think of it as your own private data center inside the AWS Cloud.

## Features

- Logically isolated network
- Region-specific service
- Supports public and private subnets
- Secure networking environment
- Default limit: **5 VPCs per Region** (can be increased)

---

# Components of a VPC

## 1. Security Groups

Security Groups act as virtual firewalls for EC2 instances.

### Features

- Instance-level security
- Supports only Allow rules
- Denies all inbound traffic by default
- Allows all outbound traffic by default (modifiable)
- Stateful

### Stateful

If inbound traffic is allowed, the response traffic is automatically allowed.

---

## 2. Network ACL (NACL)

Network ACL is a firewall for Subnets.

### Features

- Subnet-level security
- Supports both Allow and Deny rules
- Separate inbound and outbound rules
- Stateless

### Stateless

Inbound and outbound rules must be configured separately.

---

# Security Group vs NACL

| Security Group | NACL |
|----------------|------|
| Instance level | Subnet level |
| Allow rules only | Allow and Deny rules |
| Stateful | Stateless |
| Evaluates all rules | Evaluates rules in order |

---

## 3. CIDR (Classless Inter-Domain Routing)

CIDR defines the IP address range available for a VPC or Subnet.

Example:

```text
10.0.0.0/16
```

Supports:
- IPv4
- IPv6

---

## 4. Route Table

A Route Table contains routing rules that determine where network traffic should go.

Every subnet must be associated with a Route Table.

AWS automatically creates a **Local Route**, which cannot be deleted.

Example:

```text
Destination       Target

10.0.0.0/16       Local
0.0.0.0/0         Internet Gateway
```

---

## 5. Subnets

A subnet is a smaller network inside a VPC.

### Public Subnet

A Public Subnet has a route to the Internet Gateway (IGW).

Used for:
- Web Servers
- Load Balancers
- Bastion Hosts

---

### Private Subnet

A Private Subnet does not have direct internet access.

It accesses the internet through a NAT Gateway for outbound traffic only.

Used for:
- Databases
- Backend Servers
- Application Servers

---

## 6. Internet Gateway (IGW)

An Internet Gateway allows communication between resources in a public subnet and the Internet.

Features:
- Enables inbound internet access
- Enables outbound internet access
- Attached to one VPC

---

## 7. NAT Gateway

A NAT Gateway allows EC2 instances in private subnets to access the Internet for outbound connections.

The Internet cannot initiate connections to private EC2 instances.

Common Uses:
- Software updates
- Package installation
- Downloading dependencies

---

## 8. AWS Direct Connect

AWS Direct Connect is a dedicated private network connection between your on-premises data center and AWS.

### Benefits

- Private connectivity
- Lower latency
- Higher bandwidth
- More reliable network performance
- Reduced internet traffic

Bandwidth ranges from **50 Mbps to 100 Gbps**.

---

# VPC Connectivity

## 1. VPC Peering

- Connects two VPCs privately.
- No transitive routing.

Best for connecting a small number of VPCs.

---

## 2. Transit Gateway

Transit Gateway acts as a central hub connecting multiple VPCs and on-premises networks.

Benefits:
- Simplifies network architecture
- Supports transitive routing
- Easy to manage

---

# VPC Endpoints

A VPC Endpoint allows private communication between your VPC and supported AWS services without using the public Internet.

Benefits:
- Improved security
- Lower latency
- No Internet Gateway required
- No NAT Gateway required for supported services

---

## Types of VPC Endpoints

### Interface Endpoint

- Uses AWS PrivateLink
- Creates Elastic Network Interfaces (ENIs)
- Used for services such as:
  - CloudWatch
  - Secrets Manager
  - SNS
  - SQS
  - KMS

---

### Gateway Endpoint

Supports only:
- Amazon S3
- Amazon DynamoDB

Benefits:
- Free to use
- No Internet Gateway required
- No NAT Gateway required
- Traffic stays within the AWS network

---

# Interview Questions

## Basic Questions

1. What is a VPC?
2. Why do we use a VPC?
3. What is the default VPC?
4. What is a Public Subnet?
5. What is a Private Subnet?
6. What is CIDR?
7. What is an Internet Gateway?
8. What is a NAT Gateway?
9. What is a Route Table?
10. What is a Security Group?

---

## Intermediate Questions

1. Difference between Security Group and NACL?
2. Why is a Security Group stateful?
3. Why is a NACL stateless?
4. Can a private subnet access the Internet?
5. Can the Internet directly access an EC2 instance in a private subnet?
6. What is VPC Peering?
7. What is Transit Gateway?
8. What is AWS Direct Connect?
9. What are VPC Endpoints?
10. Difference between Interface Endpoint and Gateway Endpoint?

---

# Quick Revision

- **VPC** → Private virtual network in AWS.
- **Subnet** → Smaller network inside a VPC.
- **Public Subnet** → Has a route to the Internet Gateway.
- **Private Subnet** → No direct internet access.
- **Internet Gateway (IGW)** → Enables internet connectivity.
- **NAT Gateway** → Allows outbound internet access for private subnets.
- **Security Group** → Instance-level firewall (Stateful).
- **NACL** → Subnet-level firewall (Stateless).
- **Route Table** → Controls network traffic routing.
- **CIDR** → Defines the IP address range.
- **VPC Peering** → Connects two VPCs privately.
- **Transit Gateway** → Central hub connecting multiple VPCs.
- **VPC Endpoint** → Private access to AWS services without using the Internet.