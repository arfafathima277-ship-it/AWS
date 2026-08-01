# Elastic Load Balancer (ELB)

## What is Elastic Load Balancer (ELB)?

Elastic Load Balancer (ELB) is a fully managed AWS service that automatically distributes incoming application traffic across multiple targets.

Targets include:
- Amazon EC2 Instances
- Containers (ECS/EKS)
- IP Addresses
- AWS Lambda Functions

ELB improves:
- High Availability
- Scalability
- Fault Tolerance
- Performance
- Reliability

---

# Why Do We Need ELB?

Without ELB

User

↓

EC2 Instance

↓

Server Failure

↓

Application Down

With ELB

User

↓

Elastic Load Balancer

↓

EC2-1

↓

EC2-2

↓

EC2-3

Traffic is distributed evenly across healthy instances.

---

# Advantages of ELB

- Automatic Traffic Distribution
- High Availability
- Fault Tolerance
- Health Monitoring
- SSL/TLS Offloading
- Auto Scaling Integration
- Highly Scalable
- Managed AWS Service

---

# Types of Elastic Load Balancer

AWS provides four types of Load Balancers.

## 1. Application Load Balancer (ALB)

Application Load Balancer works at **Layer 7 (Application Layer)** of the OSI Model.

### Supported Protocols

- HTTP
- HTTPS

### Features

- Path-based Routing
- Host-based Routing
- Microservices Support
- Container-based Applications
- Advanced Request Routing

### Best Used For

- Web Applications
- REST APIs
- Microservices

---

## 2. Network Load Balancer (NLB)

Network Load Balancer works at **Layer 4 (Transport Layer)**.

### Supported Protocols

- TCP
- UDP
- TLS

### Features

- Extremely High Performance
- Very Low Latency
- Millions of Requests Per Second
- Static IP Address Support

### Best Used For

- Gaming Applications
- Streaming Applications
- Financial Applications

---

## 3. Gateway Load Balancer (GWLB)

Gateway Load Balancer is designed to deploy and scale virtual network appliances.

Examples:

- Firewalls
- Intrusion Detection Systems (IDS)
- Intrusion Prevention Systems (IPS)
- Traffic Inspection

Gateway Load Balancer operates at:

- Layer 3 (Network Layer)
- Layer 4 (Transport Layer)

---

## 4. Classic Load Balancer (CLB)

Classic Load Balancer is the legacy load balancer provided by AWS.

### Supported Protocols

- HTTP
- HTTPS
- TCP
- SSL

It operates at:

- Layer 4
- Layer 7

Classic Load Balancer is mainly used for older AWS applications.

---

# ELB Comparison

| Feature | ALB | NLB | CLB |
|----------|-----|-----|-----|
| OSI Layer | Layer 7 | Layer 4 | Layer 4 & Layer 7 |
| Protocols | HTTP, HTTPS | TCP, UDP, TLS | HTTP, HTTPS, TCP, SSL |
| Routing | Path & Host Based | IP & Port Based | Basic Routing |
| Performance | Advanced | Very High | Standard |
| Best For | Web Apps | High Performance Apps | Legacy Apps |

---

# Components of ELB

## Listener

A Listener checks incoming requests on a specific protocol and port.

Examples

HTTP :80

HTTPS :443

---

## Target Group

A Target Group is a collection of backend resources that receive traffic.

Targets may include:

- EC2
- IP Address
- Containers
- Lambda

---

## Health Check

Health Checks continuously monitor backend targets.

Healthy Instance

↓

Receives Traffic

Unhealthy Instance

↓

Traffic Stops Automatically

---

# ELB Workflow

Client

↓

Elastic Load Balancer

↓

Listener

↓

Health Check

↓

Target Group

↓

Healthy EC2 Instances

↓

Response to Client

---

# ELB with Auto Scaling

Auto Scaling automatically launches or terminates EC2 instances based on demand.

ELB automatically:

- Registers new instances
- Removes terminated instances
- Routes traffic only to healthy instances

No manual configuration is required.

---

# EC2 User Data Script (Nginx Installation)

The following User Data script automatically installs and starts the Nginx web server during EC2 launch.

```bash
#!/bin/bash
yum update -y
amazon-linux-extras install nginx1.12 -y
service nginx start
```

### What this script does

- Updates packages
- Installs Nginx
- Starts the Nginx service

---

# Open Systems Interconnection (OSI) Model

The OSI (Open Systems Interconnection) Model consists of seven layers.

| Layer | Name | Purpose |
|--------|------|---------|
| Layer 7 | Application | HTTP, HTTPS, FTP, SMTP |
| Layer 6 | Presentation | Encryption, Compression |
| Layer 5 | Session | Session Management |
| Layer 4 | Transport | TCP, UDP |
| Layer 3 | Network | Routing using IP Address |
| Layer 2 | Data Link | MAC Address, Switching |
| Layer 1 | Physical | Cables, Signals, Hardware |

---

# Hands-on Performed

During the lab:

- Created multiple EC2 instances
- Installed Nginx using User Data
- Created a Target Group
- Registered EC2 instances
- Configured Health Checks
- Created an Application Load Balancer
- Configured Listener (HTTP:80)
- Attached Target Group
- Accessed the application using the ELB DNS Name
- Verified load balancing across multiple instances

---

# Interview Questions

## 1. What is Elastic Load Balancer?

Elastic Load Balancer automatically distributes incoming traffic across multiple backend resources.

---

## 2. Why do we use ELB?

- High Availability
- Fault Tolerance
- Traffic Distribution
- Scalability
- Auto Scaling Integration

---

## 3. What are the types of ELB?

- Application Load Balancer (ALB)
- Network Load Balancer (NLB)
- Gateway Load Balancer (GWLB)
- Classic Load Balancer (CLB)

---

## 4. Which Load Balancer works at Layer 7?

Application Load Balancer (ALB)

---

## 5. Which Load Balancer works at Layer 4?

Network Load Balancer (NLB)

---

## 6. Which protocols does ALB support?

- HTTP
- HTTPS

---

## 7. Which protocols does NLB support?

- TCP
- UDP
- TLS

---

## 8. What is Gateway Load Balancer used for?

It is used for deploying virtual network appliances like firewalls, IDS, and IPS.

---

## 9. What is a Listener?

A Listener checks incoming requests on specific ports and forwards them to a Target Group.

---

## 10. What is a Target Group?

A collection of backend resources that receive traffic from the Load Balancer.

---

## 11. What is a Health Check?

Health Checks monitor backend resources and stop sending traffic to unhealthy targets.

---

## 12. What happens if one EC2 instance becomes unhealthy?

ELB automatically stops routing traffic to that instance and sends requests only to healthy instances.

---

## 13. Can ELB work with Auto Scaling?

Yes. ELB automatically registers newly launched instances and removes terminated instances.

---

## 14. What is User Data in EC2?

User Data is a startup script that automatically installs software and configures an EC2 instance during launch.

---

## 15. What is the OSI Model?

The OSI Model is a seven-layer networking model that explains how data travels between devices.

---

## 16. What is the difference between ALB and NLB?

| ALB | NLB |
|------|------|
| Layer 7 | Layer 4 |
| HTTP/HTTPS | TCP/UDP/TLS |
| Path & Host Routing | IP & Port Routing |
| Web Applications | High Performance Applications |