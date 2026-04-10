# AWS 3-Tier Web Architecture 🏗️

## 🌐 Live Demo
Successfully deployed and tested AWS 3-Tier Web App!

## 📋 Project Overview
Designed and deployed a production-grade 3-tier web 
architecture on AWS demonstrating high availability, 
scalability, and security best practices.

## 🛠️ AWS Services Used
- **VPC** — Custom network with 6 subnets across 2 AZs
- **EC2** — Web servers (Nginx+React) App servers (Node.js)
- **RDS MySQL** — Managed database in private subnet
- **Application Load Balancer** — Public and Internal
- **Auto Scaling Groups** — Web and App tier
- **S3** — Application code storage
- **IAM** — EC2 roles for secure access
- **AWS Systems Manager** — Secure access without SSH

## 🔒 Security Design
- Web servers in public subnets
- App and DB servers in private subnets
- Security groups with least-privilege access
- SSM Session Manager instead of SSH
- NAT Gateway for private subnet internet access

## 📈 High Availability
- Resources across 2 Availability Zones
- Auto Scaling Groups (min 2, max 4 instances)
- ALB health checks replace unhealthy instances
- Multi-AZ database subnet group

## 🖥️ Three Tiers Explained
### Tier 1 — Web Tier
- EC2 instances running Nginx
- Serves React.js frontend
- In public subnets with ALB

### Tier 2 — App Tier  
- EC2 instances running Node.js
- Business logic on Port 4000
- In private subnets with internal ALB

### Tier 3 — Database Tier
- RDS MySQL in private subnets
- Only accessible from App Tier
- Port 3306 restricted by security group

## 💡 What I Learned
- Designing multi-tier VPC networking
- Configuring security groups with least privilege
- Setting up internal vs external load balancers
- Creating AMIs and Launch Templates
- Connecting frontend → backend → database securely
- Using SSM Session Manager for secure access
