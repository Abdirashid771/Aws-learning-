# Security Groups - ALB Lab

## ALB Security Group
- Inbound: HTTP (80) from 0.0.0.0/0
- Outbound: All traffic (default)

## EC2 Security Group
- Inbound: HTTP (80) from ALB Security Group
- Outbound: All traffic (default)
