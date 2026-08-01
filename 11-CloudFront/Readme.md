# Amazon CloudFront

## What is CloudFront?

Amazon CloudFront is AWS's Content Delivery Network (CDN).

It delivers content to users with low latency by caching data at edge locations worldwide.

---

## Why CloudFront?

Without CDN

User
↓

Request travels to Origin Server

↓

Higher latency

With CloudFront

User

↓

Nearest Edge Location

↓

Content served faster

---

## Origin

The original location where CloudFront fetches data.

Examples

- S3 Bucket
- EC2
- ALB
- Custom Server

---

## Edge Locations

AWS data centers spread across the world.

Frequently requested content is cached here.

---

## Cache

CloudFront stores copies of files.

Examples

- Images
- CSS
- JS
- HTML
- Videos

Future requests are served directly from cache.

---

## Cache Miss

Content not found in cache.

CloudFront fetches from origin.

Stores it.

Returns to user.

---

## Cache Hit

Content already exists in cache.

Returned immediately.

No request goes to origin.

---

## Benefits

- Low latency
- Global delivery
- Reduced server load
- DDoS protection
- HTTPS support
- Cost optimization

---

## Security

Supports

- SSL/TLS
- AWS Shield
- AWS WAF
- Signed URLs
- Signed Cookies

---

## CloudFront Workflow

User

↓

Edge Location

↓

Cache Hit?
│

├── Yes → Return content

└── No

↓

Origin

↓

Store in Cache

↓

Return Content

---

## Interview Questions

### What is CloudFront?

AWS CDN service.

---

### What is CDN?

Network of globally distributed servers that cache content closer to users.

---

### Difference between S3 and CloudFront?

S3

Storage.

CloudFront

Content delivery.

---

### What is an Edge Location?

Location where cached content is stored.

---

### What is Origin?

Original server from which CloudFront fetches content.

---

### What is Cache Hit?

Content served directly from cache.

---

### What is Cache Miss?

CloudFront fetches content from origin because cache doesn't contain it.
