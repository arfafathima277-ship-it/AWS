---

# Interview Questions

### 1. What is Amazon CloudFront?
Amazon CloudFront is AWS's Content Delivery Network (CDN) service that delivers content from Edge Locations with low latency.

### 2. What is a CDN?
A CDN is a globally distributed network of servers that cache and deliver content closer to users.

### 3. What is an Edge Location?
An AWS location where cached content is stored closer to users.

### 4. What is an Origin?
The original source of the content.

Examples:
- Amazon S3
- EC2
- Application Load Balancer
- Custom Web Server

### 5. What is Cache Hit?
Content is already available in the Edge Location and served directly.

### 6. What is Cache Miss?
Content is not available in the Edge Location, so CloudFront retrieves it from the Origin.

### 7. What types of files can CloudFront cache?

- Images
- HTML
- CSS
- JavaScript
- Videos
- API Responses

### 8. What are the benefits of CloudFront?

- Faster content delivery
- Low latency
- Reduced server load
- Global availability
- Improved security
- DDoS protection

### 9. Which AWS services integrate with CloudFront?

- S3
- EC2
- Elastic Load Balancer
- Route 53
- AWS WAF
- AWS Shield

### 10. Does CloudFront support HTTPS?
Yes. CloudFront supports SSL/TLS certificates for secure communication.