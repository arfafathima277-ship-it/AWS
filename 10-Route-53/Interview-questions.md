---

# Interview Questions

### 1. What is Amazon Route 53?
Amazon Route 53 is AWS's highly available and scalable DNS (Domain Name System) service used to route internet traffic to applications.

### 2. Why is it called Route 53?
It is named after Port 53, the standard port used by the DNS protocol.

### 3. What is DNS?
DNS translates human-readable domain names into IP addresses.

### 4. What is a Hosted Zone?
A Hosted Zone is a container that stores DNS records for a domain.

### 5. What is the difference between Public Hosted Zone and Private Hosted Zone?

Public Hosted Zone
- Accessible over the internet.
- Used for public websites.

Private Hosted Zone
- Accessible only within a VPC.
- Used for internal applications.

### 6. What are the routing policies available in Route 53?

- Simple Routing
- Weighted Routing
- Latency Routing
- Failover Routing
- Geolocation Routing
- Geoproximity Routing
- Multi-Value Routing

### 7. What is a Health Check?
A Health Check monitors the availability of resources. If a resource becomes unhealthy, Route 53 redirects traffic to healthy resources.

### 8. What is the difference between CNAME and Alias Record?

CNAME
- Standard DNS record.
- Cannot be used for the root domain.

Alias Record
- AWS-specific record.
- Can be used for the root domain.
- No additional DNS lookup.

### 9. Can Route 53 register domain names?
Yes. Route 53 can register and manage domain names.

### 10. Which AWS services commonly integrate with Route 53?

- Elastic Load Balancer
- CloudFront
- S3 Static Website
- API Gateway
- EC2