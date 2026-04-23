# 🌐 AWS Advanced VPC Networking Lab (Bastion Host & NAT Gateway)


---

## 📌 Overview

In this lab, I designed and implemented a **secure AWS Virtual Private Cloud (VPC) architecture** with both public and private subnets.

I configured **internet connectivity using an Internet Gateway and NAT Gateway**, and I deployed a **bastion host** to securely access private EC2 instances.

This lab helped me understand real-world AWS network segmentation and secure architecture design.

---

## 🎯 Objectives

In this lab, I:

- Created a custom VPC with CIDR `10.0.0.0/16`
- Configured public and private subnets
- Enabled DNS hostnames for EC2 connectivity
- Created and attached an Internet Gateway
- Configured route tables for public and private traffic
- Deployed a NAT Gateway for private subnet internet access
- Launched a bastion host in the public subnet
- Launched a private EC2 instance in an isolated subnet
- Used SSH to access private resources securely

---

## 🛠️ Tech Stack

- Amazon VPC  
- Amazon EC2 (Linux instances)  
- Internet Gateway  
- NAT Gateway  
- Bastion Host (Jump Box)  
- Route Tables  
- Security Groups  
- Amazon Linux 2023  
- SSH  

---

## 📂 Lab Breakdown

---

### 🔹 Task 1: Create VPC

In this task, I created a new VPC.

- I created a VPC named **Lab VPC**
- CIDR block: `10.0.0.0/16`
- I enabled DNS hostnames for EC2 instances

This allowed EC2 instances to resolve public DNS names automatically.

---

### 🔹 Task 2: Create Subnets

I created both public and private subnets:

#### Public Subnet
- CIDR: `10.0.0.0/24`
- Enabled auto-assign public IPv4

#### Private Subnet
- CIDR: `10.0.2.0/23`
- Designed for internal-only resources

This separated internet-facing and private resources.

---

### 🔹 Task 3: Create Internet Gateway

I created and attached an Internet Gateway:

- Name: **Lab IGW**
- Attached it to **Lab VPC**

This enabled internet access for public subnet resources.

---

### 🔹 Task 4: Configure Route Tables

I configured routing for public and private traffic:

#### Public Route Table
- Created and associated with Public Subnet
- Added route:
  - Destination: `0.0.0.0/0`
  - Target: Internet Gateway

#### Private Route Table
- Associated with Private Subnet
- Initially routed only within VPC

This established proper network segmentation.

---

### 🔹 Task 5: Launch Bastion Host

I launched a bastion server in the public subnet:

- Name: **Bastion Server**
- AMI: Amazon Linux 2023
- Security Group allowed SSH access
- Public IP enabled

This server acted as a secure entry point into private resources.

---

### 🔹 Task 6: Create NAT Gateway

I created a NAT Gateway to allow private subnet internet access:

- Placed in Public Subnet
- Allocated Elastic IP
- Named: **Lab NAT Gateway**

I then updated the private route table:

- Added route:
  - Destination: `0.0.0.0/0`
  - Target: NAT Gateway

This allowed private instances to access the internet securely.

---

### 🔹 Task 7: Test Private Subnet Access

I launched a private EC2 instance:

- Subnet: Private Subnet
- Security Group allowed SSH from VPC (`10.0.0.0/16`)
- Installed password login via user data script

#### Access Flow:
1. I connected to the **bastion host**
2. I SSH’d into the **private instance**
3. I tested internet access using:

```bash
ping -c 3 amazon.com

---

## 📘 Key Learnings

In this lab, I learned how to:

- Design secure multi-tier AWS network architectures
- Separate public and private workloads using subnets
- Control traffic flow using route tables
- Enable secure access using bastion hosts
- Provide outbound internet access using NAT gateways
- Implement real-world AWS networking best practices

--- 

## 🚀 Outcome

By the end of this lab, I successfully:

- Built a full VPC network architecture
- Configured secure routing between subnets
- Deployed and accessed private EC2 instances securely
- Verified NAT Gateway internet connectivity
- Implemented a bastion-based access model