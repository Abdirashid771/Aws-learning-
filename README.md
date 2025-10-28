# VPC and Network Setup

## 🎯 Objective
Create a custom VPC with public and private subnets, set up internet access, and deploy EC2 instances with secure segmentation.

---

## 🏗️ Architecture
- VPC (10.0.0.0/16)
- Public Subnet (10.0.1.0/24) → Bastion Host + NAT Gateway
- Private Subnet (10.0.2.0/24) → Private EC2
- Internet Gateway (IGW)
- NAT Gateway (NGW)
- Route Tables for public/private routing

---

## 🔒 Security
- Bastion Host (public): SSH (22) allowed from My IP  
- Private EC2: SSH (22) allowed only from Bastion SG  
- No direct internet access to private instance

---

## ✅ Verification
- SSH: Laptop → Bastion → Private EC2  
- From Private EC2:
  ```bash
  curl -I http://example.com
  curl -s https://icanhazip.com
``` 
→ Shows NAT Gateway IP (outbound internet works)

---

## 🧹 Cleanup

Terminate EC2s → Delete NAT Gateway → Release EIP → Delete IGW, route tables, subnets, SGs, and VPC.
