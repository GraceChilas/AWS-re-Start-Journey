# 🌐 AWS VPC & EC2 Web Server Lab

---

## 📌 Overview

In this lab, I designed and deployed a **Virtual Private Cloud (VPC)** in AWS and launched an **EC2 web server instance** inside it.

I configured networking components such as subnets, route tables, and security groups, and I deployed a working web server accessible over the internet.

---

## 🎯 Objectives

In this lab, I:

- Created a custom Virtual Private Cloud (VPC)
- Configured public and private subnets
- Set up route tables and subnet associations
- Created a security group to control inbound traffic
- Launched an EC2 instance inside the VPC
- Deployed and accessed a web server

---

## 🛠️ Tech Stack

- Amazon VPC  
- Amazon EC2  
- Amazon Linux 2 AMI    
- AWS Security Groups  
- AWS Route Tables  
- Bash (User Data scripts)  

---

## 📂 Lab Breakdown

---

### 🔹 Task 1: Create a VPC

In this task, I created a custom VPC using the VPC Wizard.

I configured:
- VPC CIDR: `10.0.0.0/16`
- 1 Availability Zone
- 1 Public Subnet (`10.0.0.0/24`)
- 1 Private Subnet (`10.0.1.0/24`)
- NAT Gateway enabled in 1 AZ
- Default tenancy and no IPv6

I named the resources:
- VPC: **Lab VPC**
- Public Subnet: **Public Subnet 1**
- Private Subnet: **Private Subnet 1**
- Route Tables: **Public Route Table** and **Private Route Table**

---

### 🔹 Task 2: Create Additional Subnets

In this task, I expanded the network for high availability.

I created:

- **Public Subnet 2**
  - CIDR: `10.0.2.0/24`

- **Private Subnet 2**
  - CIDR: `10.0.3.0/24`

I placed these subnets in a second Availability Zone configuration for better fault tolerance.

---

### 🔹 Task 3: Associate Subnets and Configure Routes

In this task, I associated subnets with route tables.

- I associated **Public Subnet 2** with the public route table  
- I associated **Private Subnet 2** with the private route table  

This ensured correct routing for both public and private network traffic.

---

### 🔹 Task 4: Create a Security Group

In this task, I created a firewall security group.

I configured:

- Security Group Name: **Web Security Group**
- Description: Enable HTTP access
- VPC: **Lab VPC**

Inbound rule added:
- Type: HTTP
- Source: Anywhere IPv4
- Purpose: Allow web traffic

This security group allowed public access to my web server.

---

### 🔹 Task 5: Launch EC2 Web Server

In this task, I launched an EC2 instance inside my VPC.

I configured:

- Name: **Web Server 1**
- AMI: Amazon Linux 2
- Instance type: `t3.micro`
- Key pair: `vockey`
- Subnet: **Public Subnet 2**
- Auto-assign public IP: Enabled
- Security group: **Web Security Group**

---

### 🔹 User Data Script

I used the following script to automatically configure the web server:

```bash
#!/bin/bash
yum install -y httpd mysql php
wget https://aws-tc-largeobjects.s3.us-west-2.amazonaws.com/CUR-TF-100-RESTRT-1/267-lab-NF-build-vpc-web-server/s3/lab-app.zip
unzip lab-app.zip -d /var/www/html/
chkconfig httpd on
service httpd start

---

### 🔹 Web Server Validation

After deployment:

- I waited for 2/2 status checks passed
- I copied the Public IPv4 DNS
- I opened it in a browser
- I successfully accessed the web server

---

### 📘 Key Learnings

In this lab, I learned how to:

- Design and build a custom VPC architecture
- Configure subnets across Availability Zones
- Control network traffic using route tables
- Secure resources using security groups
- Deploy and access a live web server on EC2
- Automate server setup using user data scripts

---

### 🚀 Outcome

By the end of this lab, I successfully:

- Created a fully functional VPC
- Configured public and private networking
- Deployed a secure EC2 web server
- Verified web access through a browser