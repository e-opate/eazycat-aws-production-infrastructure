# EazyCat AWS Production Infrastructure

## Overview

Production-style AWS infrastructure for a web application, designed for **high availability, security, scalability, and cost control**.

## Architecture

```text
Internet
   ↓
Application Load Balancer
   ↓
Private EC2
   ↓
Private RDS
   ↓
S3
```

Deployed across **2 Availability Zones** using a segmented VPC.

## Network

* VPC: `10.0.0.0/16`
* 2 Public subnets
* 2 Private App subnets
* 2 Private DB subnets
* Internet Gateway
* Separate route tables by tier

## AWS Services

**VPC · EC2 · ALB · Auto Scaling · RDS · S3 · IAM · CloudWatch · CloudTrail · Route 53**

## Key Engineering Decisions

* **2 AZs** → improve availability
* **Private EC2/RDS** → reduce public exposure
* **ALB** → distribute application traffic
* **Auto Scaling** → handle changing demand
* **IAM Roles** → avoid hard-coded credentials
* **Monitoring** → detect performance and operational issues
* **Cost controls** → minimize unnecessary AWS spend

## Status

🟡 **In Progress** — Network foundation completed.

Detailed technical decisions, deployment steps, testing, and troubleshooting are documented in `/docs`.
