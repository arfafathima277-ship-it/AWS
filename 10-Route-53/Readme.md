# Amazon Route 53

## What is Amazon Route 53?

Amazon Route 53 is AWS's highly available and scalable Domain Name System (DNS) service.

It is used to:
- Register domain names.
- Route internet traffic to applications.
- Convert domain names into IP addresses.
- Perform health checks on resources.
- Improve application availability using different routing policies.

Route 53 supports both:
- IPv4
- IPv6

---

## How Route 53 Works

When a user enters a domain name in the browser, Route 53 translates the domain name into an IP address so that the browser can connect to the correct server.

Example:

www.google.com

↓

DNS Lookup

↓

Amazon Route 53

↓

Returns IP Address

↓

Browser connects to the server

Some example domain names:

- www.google.com
- www.amazonprimevideo.in
- www.github.com

---

## Features

- Domain Registration
- DNS Management
- Health Checks
- Traffic Routing
- High Availability
- Supports IPv4 and IPv6
- Integration with AWS Services

---

## Routing Policies

### 1. Simple Routing Policy
- Used for a single resource or server.
- Suitable for simple applications.
- No load balancing or failover.

**Example:** One EC2 instance hosting a website.

---

### 2. Weighted Routing Policy
- Routes traffic based on assigned weights.
- Useful for A/B testing and traffic distribution.

**Example:**
- Server A → 80%
- Server B → 20%

---

### 3. Latency Routing Policy
- Routes users to the AWS Region with the lowest network latency.
- Improves application response time.

**Example:**
A user from India is routed to the Mumbai Region instead of the US Region.

---

### 4. Geolocation Routing Policy
- Routes traffic based on the user's geographic location.
- Useful for serving region-specific content.

**Example:**
- India → Indian Website
- USA → US Website

---

### 5. Geoproximity Routing Policy
- Routes traffic based on the geographic location of AWS resources.
- Can shift traffic using Traffic Flow and bias settings.

---

### 6. Failover Routing Policy
- Used for disaster recovery.
- Redirects traffic from the primary resource to the secondary (backup) resource if the primary becomes unhealthy.

---

### 7. Multi-Value Answer Routing Policy
- Returns up to **8 healthy IP addresses** in response to a DNS query.
- Performs health checks before returning IP addresses.
- Helps improve availability.

---

## Health Checks

Route 53 continuously monitors the health of endpoints such as:

- EC2 Instances
- Load Balancers
- Public Web Servers

If an endpoint becomes unhealthy, Route 53 automatically redirects traffic to healthy resources.

---

## Advantages

- Highly available and scalable
- Supports IPv4 and IPv6
- Automatic failover
- Multiple routing policies
- Health monitoring
- Easy integration with AWS services

---

