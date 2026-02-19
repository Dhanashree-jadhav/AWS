# 🌍 Amazon Route 53 – Complete Guide

## 📌 Introduction

Amazon Route 53 is a highly available and scalable Domain Name System (DNS) web service provided by AWS.  
It is used to route internet traffic to AWS resources such as EC2, Load Balancer, S3, and other services.

The name "Route 53" comes from:
- **Route** → It routes user traffic
- **53** → DNS operates on port 53

---

## 🌐 What is DNS?

DNS (Domain Name System) is the phonebook of the internet.

It converts a human-readable domain name like:

www.example.com

into an IP address like:

3.110.45.21


Without DNS, users would need to remember IP addresses instead of domain names.

---

## 🏗️ Core Components of Route 53

### 1️⃣ Hosted Zone

A Hosted Zone is a container for DNS records of a domain.

There are two types:

- **Public Hosted Zone** → Used for internet-facing domains
- **Private Hosted Zone** → Used inside a VPC for internal applications

---

### 2️⃣ DNS Records

DNS records define how traffic is routed for a domain.

| Record Type | Purpose |
|-------------|----------|
| A | Maps domain to IPv4 address |
| AAAA | Maps domain to IPv6 address |
| CNAME | Maps one domain to another domain |
| MX | Routes emails to mail servers |
| NS | Specifies name servers for domain |
| TXT | Used for verification and email security |

---

## 🔀 Routing Policies in Route 53

Routing policies determine how Route 53 responds to DNS queries.

### 1️⃣ Simple Routing
Routes traffic to a single resource.

### 2️⃣ Weighted Routing
Splits traffic based on assigned weights (e.g., 70% / 30%).

Used for:
- A/B testing
- Blue-Green deployment

### 3️⃣ Latency-Based Routing
Routes users to the AWS region with lowest latency.

Improves performance globally.

### 4️⃣ Failover Routing
Routes traffic to secondary resource if primary fails.

Used for high availability and disaster recovery.

### 5️⃣ Geolocation Routing
Routes traffic based on user location.

### 6️⃣ Multi-Value Routing
Returns multiple healthy IP addresses.

---

## 🔎 CNAME vs Alias Record

| Feature | CNAME | Alias |
|----------|--------|--------|
| Type | Standard DNS record | AWS-specific record |
| Maps To | Another domain name | AWS resource |
| Root Domain Support | ❌ Not allowed | ✅ Allowed |
| Performance | Requires additional DNS lookup | Direct AWS resolution |

### When to Use:
- Use **CNAME** for subdomains.
- Use **Alias** for root domain and AWS resources like ALB, CloudFront, S3.

---

## ⚙️ How Route 53 Works

1. User enters domain in browser.
2. DNS resolver queries Route 53.
3. Route 53 checks hosted zone records.
4. Returns IP address.
5. User connects to the target server.

---

## 🏢 Real-World Example

You deploy an application behind an Application Load Balancer (ALB).

AWS provides:
my-alb-123.us-east-1.elb.amazonaws.com


To connect your domain:

- Create Public Hosted Zone.
- Create A record.
- Enable Alias.
- Select ALB as target.

Now users can access:

https://mydomain.com


---

## 🎯 Key Features of Route 53

- Highly available and scalable
- Global DNS service
- Health checks
- Domain registration
- Traffic flow management
- Integration with AWS services

---

## 🎤 Interview Questions

### Q1: What is Route 53?
Route 53 is AWS’s scalable DNS service that routes user traffic to AWS resources using domain names.

### Q2: Why is Route 53 called 53?
Because DNS operates on port 53.

### Q3: What is Hosted Zone?
A container that stores DNS records for a domain.

### Q4: What is difference between Public and Private Hosted Zone?
Public is internet-facing. Private is accessible only within a VPC.

### Q5: What is Alias record?
Alias is an AWS-specific record that maps a domain to AWS resources and supports root domain mapping.

---

## 🚀 Conclusion

Amazon Route 53 is a powerful DNS service that helps manage domain routing, improve performance, ensure high availability, and integrate seamlessly with AWS infrastructure.

It is widely used in production environments for scalable and reliable web applications.

---


