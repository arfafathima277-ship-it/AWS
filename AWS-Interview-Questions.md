# AWS Interview Questions

## 1. What is AWS?

AWS (Amazon Web Services) is a cloud computing platform that provides on-demand services like computing, storage, databases, networking, security, and monitoring.

---

## 2. What are the different types of cloud computing?

- Public Cloud
- Private Cloud
- Hybrid Cloud

---

## 3. What is Amazon EC2?

Amazon EC2 (Elastic Compute Cloud) is a service that provides virtual servers (instances) in the cloud to run applications.

---

## 4. What is Amazon S3?

Amazon S3 (Simple Storage Service) is an object storage service used to store files such as images, videos, backups, and logs.

---

## 5. Difference between EBS and S3?

| EBS | S3 |
|-----|----|
| Block Storage | Object Storage |
| Attached to EC2 | Accessed over the Internet |
| Low latency | Highly durable |
| Used as disk | Used for file storage |

---

## 6. What is a VPC?

A Virtual Private Cloud (VPC) is a logically isolated network in AWS where you can launch AWS resources securely.

---

## 7. What are Public and Private Subnets?

Public Subnet:
- Has Internet Gateway access
- Used for Web Servers

Private Subnet:
- No direct Internet access
- Used for Databases and Backend Servers

---

## 8. What is an Internet Gateway?

An Internet Gateway (IGW) allows communication between resources in a VPC and the Internet.

---

## 9. What is a NAT Gateway?

A NAT Gateway allows instances in a private subnet to access the Internet without exposing them to incoming Internet traffic.

---

## 10. What is an AMI?

AMI (Amazon Machine Image) is a template containing an operating system, software, and configuration used to launch EC2 instances.

---

## 11. What are Security Groups?

Security Groups are virtual firewalls that control inbound and outbound traffic for EC2 instances.

State: Stateful

---

## 12. What are Network ACLs?

Network ACLs are subnet-level firewalls.

State: Stateless

---

## 13. Difference between Security Group and NACL?

| Security Group | NACL |
|---------------|------|
| Instance Level | Subnet Level |
| Stateful | Stateless |
| Allow Rules Only | Allow and Deny Rules |

---

## 14. What is an Elastic IP?

Elastic IP is a static public IPv4 address that can be associated with an EC2 instance.

---

## 15. What is Auto Scaling?

Auto Scaling automatically increases or decreases the number of EC2 instances based on traffic and demand.

---

## 16. What is Elastic Load Balancer (ELB)?

ELB distributes incoming traffic across multiple EC2 instances to improve availability and fault tolerance.

Types:
- Application Load Balancer (ALB)
- Network Load Balancer (NLB)
- Gateway Load Balancer (GWLB)

---

## 17. What is Route 53?

Route 53 is AWS's DNS service used for domain registration, DNS routing, and health checks.

---

## 18. What is CloudWatch?

CloudWatch is a monitoring service used to monitor AWS resources, logs, metrics, and alarms.

---

## 19. What is IAM?

IAM (Identity and Access Management) controls authentication and authorization in AWS.

Components:
- Users
- Groups
- Roles
- Policies

---

## 20. What is CloudFront?

CloudFront is AWS's Content Delivery Network (CDN) that delivers content with low latency using Edge Locations.

---

## 21. What is the difference between Scaling Up and Scaling Out?

Scaling Up:
- Increase CPU/RAM of an existing server.

Scaling Out:
- Add more servers behind a Load Balancer.

---

## 22. What is RDS?

Amazon RDS is a managed relational database service.

Supported databases:
- MySQL
- PostgreSQL
- MariaDB
- Oracle
- SQL Server

---

## 23. What is EFS?

Elastic File System is a shared file storage service that can be mounted on multiple EC2 instances.

---

## 24. What is ECR?

Amazon Elastic Container Registry (ECR) stores Docker container images securely.

---

## 25. What is ECS?

Amazon Elastic Container Service (ECS) is a managed container orchestration service for running Docker containers.

---

## 26. What is AWS CLI?

AWS CLI is a command-line tool used to manage AWS services from the terminal.

Example:

```bash
aws s3 ls
```

---

## 27. What is the AWS Shared Responsibility Model?

AWS is responsible for:
- Cloud infrastructure
- Physical security
- Hardware
- Networking

Customer is responsible for:
- Data
- IAM
- Applications
- Operating System
- Security Groups

---

## 28. What is an Availability Zone?

An Availability Zone (AZ) is one or more isolated data centers within an AWS Region.

---

## 29. What is an AWS Region?

A Region is a geographical location containing multiple Availability Zones.

Example:
- Mumbai (ap-south-1)
- N. Virginia (us-east-1)

---

## 30. Why do you want to use AWS?

- High Availability
- Scalability
- Security
- Cost-effective
- Global Infrastructure
- Pay-as-you-go pricing
