# AWS Auto Scaling

## What is AWS Auto Scaling?

AWS Auto Scaling is a service that automatically adjusts the number of EC2 instances based on application demand. It helps maintain application performance while reducing costs.

---

# Why Auto Scaling?

Without Auto Scaling:
- Servers may become overloaded during high traffic.
- Resources may remain idle during low traffic, increasing costs.

With Auto Scaling:
- Automatically adds EC2 instances during high demand.
- Automatically removes EC2 instances during low demand.
- Improves availability and optimizes cost.

---

# Benefits of Auto Scaling

- High Availability
- Fault Tolerance
- Automatic Scaling
- Cost Optimization
- Better Performance
- Easy Integration with Elastic Load Balancer (ELB)

---

# Auto Scaling Components

## 1. Launch Template

A Launch Template contains the configuration required to launch an EC2 instance.

It includes:
- Amazon Machine Image (AMI)
- Instance Type
- Key Pair
- Security Group
- Storage (EBS)
- User Data Script

---

## 2. Auto Scaling Group (ASG)

An Auto Scaling Group manages a collection of EC2 instances.

It ensures that the desired number of healthy instances are always running.

---

## Capacity Settings

### Minimum Capacity
The minimum number of EC2 instances that must always be running.

### Desired Capacity
The ideal number of EC2 instances that Auto Scaling tries to maintain.

### Maximum Capacity
The maximum number of EC2 instances that can be launched.

Example:

Minimum = 2

Desired = 3

Maximum = 6

---

# Scaling Policies

## 1. Dynamic Scaling

Automatically increases or decreases instances based on CloudWatch metrics such as CPU utilization.

Example:
- CPU > 70% → Add instances
- CPU < 30% → Remove instances

---

## 2. Scheduled Scaling

Automatically scales resources at a specific date and time.

Example:
Increase instances every Monday at 9:00 AM.

---

## 3. Predictive Scaling

Uses machine learning to predict future traffic and scales resources before demand increases.

---

# Auto Scaling Workflow

```text
           User Traffic
                 │
                 ▼
        Elastic Load Balancer
                 │
                 ▼
        Auto Scaling Group
        ┌──────┼──────┐
        ▼      ▼      ▼
      EC2-1  EC2-2  EC2-3
```

If traffic increases:

```text
CloudWatch Alarm
        │
        ▼
Auto Scaling Group
        │
        ▼
Launch New EC2 Instance
```

If traffic decreases:

```text
CloudWatch Alarm
        │
        ▼
Auto Scaling Group
        │
        ▼
Terminate Extra EC2 Instance
```

---

# Auto Scaling with ELB

Elastic Load Balancer distributes incoming traffic among healthy EC2 instances.

When Auto Scaling launches a new EC2 instance, it is automatically registered with the Load Balancer.

If an instance becomes unhealthy, ELB stops sending traffic to it, and Auto Scaling replaces it with a new healthy instance.

---

# Health Checks

Auto Scaling continuously checks the health of EC2 instances.

If an instance fails:
- Marks it as unhealthy.
- Terminates the instance.
- Launches a replacement automatically.

---

# Advantages

- Automatic Scaling
- High Availability
- Cost Efficient
- Fault Tolerant
- Better Performance
- Automatic Recovery
- Easy Integration with ELB
- No Manual Intervention

---

# Real-Time Example

An e-commerce website experiences high traffic during a festival sale.

- Auto Scaling automatically launches additional EC2 instances.
- ELB distributes traffic across all instances.
- After the sale ends, extra instances are terminated automatically to reduce costs.

---

# Hands-on Steps

1. Create a Launch Template.
2. Select AMI and Instance Type.
3. Configure Security Group and Key Pair.
4. Create an Auto Scaling Group.
5. Set Minimum, Desired, and Maximum Capacity.
6. Attach an Application Load Balancer.
7. Configure Scaling Policies.
8. Create CloudWatch Alarms.
9. Launch the Auto Scaling Group.
10. Monitor scaling activities.

---

# Interview Questions

### 1. What is AWS Auto Scaling?

AWS Auto Scaling automatically adds or removes EC2 instances based on application demand.

---

### 2. What is an Auto Scaling Group (ASG)?

A logical group of EC2 instances managed together to maintain the desired capacity.

---

### 3. What is a Launch Template?

A Launch Template contains the configuration required to launch EC2 instances.

---

### 4. What are the three capacity settings?

- Minimum Capacity
- Desired Capacity
- Maximum Capacity

---

### 5. What are the types of Scaling Policies?

- Dynamic Scaling
- Scheduled Scaling
- Predictive Scaling

---

### 6. Which AWS service monitors Auto Scaling metrics?

Amazon CloudWatch.

---

### 7. Can Auto Scaling work with ELB?

Yes. ELB automatically distributes traffic to healthy EC2 instances managed by the Auto Scaling Group.

---

### 8. What happens if an EC2 instance becomes unhealthy?

Auto Scaling terminates the unhealthy instance and launches a new one automatically.

---

# Summary

- Automatically adjusts EC2 instances based on demand.
- Uses Launch Templates and Auto Scaling Groups.
- Works with CloudWatch and Elastic Load Balancer.
- Improves availability, scalability, and cost efficiency.