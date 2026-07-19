# Amazon EC2 (Elastic Compute Cloud)

## What is Amazon EC2?

Amazon Elastic Compute Cloud (EC2) is an AWS Compute service that provides scalable virtual servers (called Instances) in the cloud.

EC2 follows the Infrastructure as a Service (IaaS) model and allows users to launch, manage, and terminate virtual machines on demand.

AWS follows a pay-as-you-go pricing model, so users only pay for the resources they consume.

---

# AWS Compute Services

AWS offers several compute services:

- Amazon EC2
- AWS Lambda
- Amazon Lightsail
- AWS Outposts

> Note: Amazon EBS is a storage service that is commonly used with EC2.

---

# AWS Pricing

## Compute

- Charged per hour or per second depending on the instance type.

## Storage

- Charged per GB per month.

## Database

Pricing depends on:

- Database engine
- Instance size
- Storage
- Backup
- Data transfer

---

# EC2 Pricing Options

## On-Demand

- Pay only for usage
- No long-term commitment

## Reserved Instances

- All Upfront Reserved Instance (AURI)
- Partial Upfront Reserved Instance (PURI)
- No Upfront Reserved Instance (NURI)

---

## Spot Instances

- Uses unused AWS capacity
- Lowest pricing
- Can be interrupted by AWS

---

# What is an EC2 Instance?

An EC2 Instance is a virtual server running in AWS.

Each instance provides:

- CPU
- Memory
- Storage
- Networking
- Operating System

---

# EC2 Features

- Scalable compute capacity
- Multiple instance types
- Secure networking
- Flexible storage
- Auto Scaling support
- High Availability
- Pay-as-you-go pricing

---

# EC2 Configuration

While launching an EC2 instance we can customize:

- Region
- Amazon Machine Image (AMI)
- Instance Type
- Key Pair
- VPC
- Subnet
- Security Group
- Storage (EBS)
- Tags

---

# Scalability

Scalability is the ability to increase or decrease computing resources according to application demand.

---

# Elasticity

Elasticity automatically adjusts CPU, memory, storage, and networking resources based on workload.

---

# Instance States

- Pending
- Running
- Stopping
- Stopped
- Rebooting
- Terminated

---

# Public IP vs Private IP

## Public IPv4

- Used to access EC2 from the internet
- Required for SSH or RDP

---

## Private IPv4

- Used for communication within the VPC
- Not accessible from the internet

---

# Security Groups

Security Groups act as virtual firewalls for EC2 instances.

Characteristics:

- Stateful
- Controls inbound traffic
- Controls outbound traffic

Default Rules:

- Inbound → Deny all
- Outbound → Allow all

Common Ports:

| Service | Port |
|---------|-----:|
| SSH | 22 |
| HTTP | 80 |
| HTTPS | 443 |

---

# EC2 Storage Options

## Instance Store

- Temporary storage
- Data is lost after instance termination

---

## Amazon EBS

- Persistent block storage
- Data remains even after the instance stops

---

# EBS Volumes

EBS Volumes provide persistent storage for EC2 instances.

Important:

- EC2 Instance and EBS Volume must be in the same Availability Zone.
- Multiple EBS Volumes can be attached depending on the instance type.

---

# EBS Snapshots

An EBS Snapshot is a backup of an EBS Volume.

Used for:

- Backup
- Recovery
- Disaster Recovery
- Creating new volumes

---

# Types of EBS Volumes

## General Purpose SSD (gp3/gp2)

Suitable for:

- Development
- Web applications
- General workloads

---

## Provisioned IOPS SSD (io1/io2)

Suitable for:

- Databases
- High-performance applications

---

# Auto Scaling

Auto Scaling automatically adjusts EC2 resources according to traffic.

Benefits:

- High Availability
- Better Performance
- Cost Optimization

---

## Horizontal Scaling

Also known as Scaling Out / Scaling In.

Scaling Out:

- Launch additional EC2 instances.

Scaling In:

- Remove EC2 instances.

---

## Vertical Scaling

Increase the resources of an existing EC2 instance.

Example:

- 2 vCPU → 4 vCPU
- 4 GB RAM → 8 GB RAM

---

# Practical Performed

During this lab, we performed the following tasks:

- Opened the AWS Management Console.
- Navigated to the EC2 Dashboard.
- Clicked **Launch Instance**.
- Entered an instance name.
- Selected an Amazon Machine Image (AMI).
- Chose an instance type (Free Tier eligible).
- Created/selected a Key Pair.
- Configured the Security Group.
- Allowed SSH (Port 22).
- Configured EBS storage.
- Launched the EC2 instance.
- Verified the instance entered the **Running** state.
- Viewed the Public IPv4 and Private IPv4 addresses.
- Explored Security Groups, Key Pairs, Volumes, and Snapshots.
- Performed Start, Stop, and Reboot operations on the instance.

---

# Best Practices

- Use IAM Users instead of the Root User.
- Open only the required ports in Security Groups.
- Never share your `.pem` key file.
- Stop unused instances to reduce costs.
- Create EBS Snapshots regularly.
- Use IAM Roles for applications running on EC2.

---

# Interview Questions

### What is Amazon EC2?

Amazon EC2 is an AWS compute service that provides scalable virtual servers in the cloud.

---

### What is an EC2 Instance?

An EC2 Instance is a virtual machine running on AWS infrastructure.

---

### What is a Security Group?

A Security Group is a stateful virtual firewall that controls inbound and outbound traffic for EC2 instances.

---

### Difference between Public IP and Private IP?

Public IP:

- Accessible over the internet.

Private IP:

- Used only within the VPC.

---

### What is an EBS Snapshot?

An EBS Snapshot is a backup of an EBS Volume.

---

### Difference between Horizontal and Vertical Scaling?

Horizontal Scaling:

- Add or remove EC2 instances.

Vertical Scaling:

- Increase CPU or RAM of an existing instance.

---

# Practical Screenshots

Add screenshots of:

- EC2 Dashboard
- Launch Instance
- AMI Selection
- Instance Type
- Security Group
- Key Pair
- Running Instance
- Public IP Address
- EBS Volume
- EBS Snapshot