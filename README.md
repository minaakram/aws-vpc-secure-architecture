# Secure Multi-Tier VPC Networking Environment ☁️

## 📝 Project Overview
This project demonstrates the design and implementation of a secure networking environment on AWS. It focuses on isolating private resources while maintaining secure administrative access and outbound internet connectivity.

## 🏗️ Architecture
The environment consists of:
- **Custom VPC** with Public and Private subnets.
- **Internet Gateway (IGW)** for public internet access.
- **NAT Gateway** to allow private instances to download updates securely.
- **Bastion Host** acting as a secure jump box for administration.
- **Dual-layer Security:** Security Groups (Instance-level) and Network ACLs (Subnet-level).

![Architecture Diagram](./architecture.png) 
*(Note: Replace "architecture.png" with your image filename)*

## 🛠️ Implementation Steps
1. **Networking Foundation:** Created a VPC and set up Public/Private subnets across Availability Zones.
2. **Routing:** Configured Route Tables for the public subnet (via IGW) and the private subnet (via NAT Gateway).
3. **Security Enforcement:** - Created a **Bastion Host** with restricted SSH access (My IP only).
   - Configured **SSH Agent Forwarding** to connect to private instances without storing keys on the bastion.
   - Implemented **Network ACLs** to block specific ICMP (Ping) traffic as an additional security layer.
4. **Validation:** Successfully tested connectivity from the private instance to the internet.

## 📸 Verification & Screenshots
### Successful Internet Connectivity (Ping Test)
![Ping Test](./ping-test.png)
*(Note: Replace "ping-test.png" with your image filename)*

### Security Layer Validation
- Verified that the Private Instance is not reachable directly from the internet.
- Verified that the NACL rules successfully dropped traffic when configured.

## 🎓 Skills Learned
- VPC Design & Subnetting.
- Route Table Management.
- NAT Gateway & Internet Gateway configuration.
- SSH Agent Forwarding for secure administration.
- Stateless vs. Stateful filtering (NACLs vs. Security Groups).
