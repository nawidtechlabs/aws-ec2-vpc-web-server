# AWS EC2 + VPC Web Server Deployment

## Overview
Instead of just launching an EC2 instance, I built the full network around it to understand how traffic, routing, and security actually work in AWS.

This project demonstrates deploying a secure, publicly accessible web server inside a custom VPC.

---

## Architecture
- Custom VPC (10.1.0.0/16)
- Public subnet (10.1.2.0/24)
- Internet Gateway attached to VPC
- Route table configured for internet access
- EC2 instance (Ubuntu 24.04)
- Apache web server running on port 80

---

## 🔐 Security Configuration
- HTTP (Port 80) → Open to the internet (0.0.0.0/0)
- SSH (Port 22) → Restricted to my IP only
- Security Groups used to control inbound traffic

---

## Deployment Steps (High-Level)
1. Created a custom VPC with defined CIDR block  
2. Configured a public subnet  
3. Attached an Internet Gateway  
4. Updated route table to allow outbound internet access  
5. Launched EC2 instance inside the subnet  
6. Configured security group rules (HTTP + restricted SSH)  
7. Installed Apache on Ubuntu  
8. Verified public access via browser  

---

## Result
Successfully deployed a live web server accessible via public IP.

Apache default page confirmed the server is running and reachable.

---

## Screenshots
<img width="1536" height="1024" alt="EC2 blurred" src="https://github.com/user-attachments/assets/5cc4c8b7-ffcb-456f-ba96-2ea7aef619f0" />
<img width="1068" height="812" alt="Apache " src="https://github.com/user-attachments/assets/66b3b223-a67f-42ff-b1a6-4c838d316913" />
<img width="1536" height="1024" alt="Security Group Blurred" src="https://github.com/user-attachments/assets/b3e721ab-92c3-4cee-ad14-8d63e75ce38c" />


- EC2 instance running  
- Apache "It works" page  
- Security group configuration  

---

## 🧠 What I Learned
This project helped me understand that cloud infrastructure is not just about launching resources — it's about:

- How networking components connect (VPC, subnets, routing)
- How to control exposure and reduce attack surface
- How security groups act as a firewall at the instance level

---

## 🔜 Next Steps
- Add monitoring (CloudWatch)
- Implement logging
- Explore automation (Terraform)

---

## ⚙️ Tech Stack
- AWS EC2
- AWS VPC
- Ubuntu Linux
- Apache2
