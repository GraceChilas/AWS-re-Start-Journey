# AWS Compute Lab Instructions: EC2 Instance Setup and Management

## Overview

In this lab, I learned how to launch, configure, monitor, and manage an Amazon EC2 instance. I also explored security groups, storage, resizing, and termination protection.

---

## Task 1: Launch an EC2 Instance

### Step 1: Name My Instance

- I entered a name for my EC2 instance  
- AWS automatically created a **key-value pair**:
  - **Key:** Name  
  - **Value:** My chosen instance name  

---

### Step 2: Choose an Amazon Machine Image (AMI)

- I selected an AMI from the **Quick Start list**  

- The AMI included:

  - A root volume template (operating system or application server)
  - Launch permissions
  - Block device mapping  

> ?? I noted that I can also create a custom AMI or use AWS Marketplace images.

---

### Step 3: Choose an Instance Type

- I selected **t3.micro**
  - 2 vCPUs  
  - 1 GiB memory  

- This was suitable for my lab requirements  

---

### Step 4: Configure Key Pair

- I skipped creating a key pair  
- I did not need to log in to the instance for this lab  

---

### Step 5: Configure Network Settings

- I selected a **VPC**  
- I configured a **security group**  
- I removed **SSH (port 22)** access to improve security  

---

### Step 6: Add Storage

- I used the default **Amazon EBS volume**:
  - Size: **8 GiB**  
  - Used as the root volume  

---

### Step 7: Configure Advanced Details

- I added a **User Data script**  
- This script automatically installed a web server when the instance launched  

---

### Step 8: Launch the Instance

- I launched the instance  
- I observed the status change:
  - **Pending ? Running**  
- I noted the **Public DNS name** to access the instance  

---

## Task 2: Monitor My Instance

### Step 1: Check Instance Status

- I verified the instance health using **status checks**  

### Step 2: View CloudWatch Metrics

- I opened the monitoring tab  
- I reviewed available metrics such as CPU and network usage  

### Step 3: Understand Monitoring Types

- I learned:

  - **Basic monitoring:** 5-minute intervals (default)  
  - **Detailed monitoring:** 1-minute intervals (optional)  

### Step 4: Use Troubleshooting Tools

- I explored the **Instance Screenshot** feature for troubleshooting  

---

## Task 3: Configure Security Group and Access Web Server

### Step 1: Test Initial Access

- I attempted to access the web server using the public DNS  
- The request failed because HTTP traffic was not allowed  

### Step 2: Update Security Group

- I edited inbound rules to allow:

  - **HTTP (port 80)**  

### Step 3: Verify Access

- I refreshed my browser  
- I successfully accessed the web server and saw:

"Hello From Your Web Server!"
---

## Task 4: Resize My EC2 Instance

### Step 1: Stop the Instance

- I stopped the instance before making changes  
- I noted:
  - No compute charges while stopped  
  - Storage charges still apply  

---

### Step 2: Change Instance Type

- I changed the instance type:
  - From **t3.micro → t3.small**  
- This increased the available memory  

---

### Step 3: Resize Storage

- I modified the EBS volume:
  - From **8 GiB → 10 GiB**  

---

### Step 4: Restart the Instance

- I started the instance again  
- I confirmed:
  - Increased memory  
  - Increased storage  

---

## Task 5: Test Termination Protection

### Step 1: Attempt to Terminate

- I selected the instance  
- I clicked **Terminate**  

### Step 2: Observe Behavior

- The termination attempt failed  
- An error message appeared  

### Step 3: Understand Why

- I confirmed that **termination protection was enabled**  
- This prevented accidental deletion  

---

## Key Concepts I Learned

- **EC2 Instance:** A virtual server in AWS  
- **AMI:** A template used to launch instances  
- **Security Group:** A virtual firewall controlling traffic  
- **EBS:** Persistent storage for EC2  
- **User Data:** A script that runs at launch  
- **Termination Protection:** Prevents accidental deletion  

---

## My Lab Completion Checklist

- [x] I launched an EC2 instance  
- [x] I configured networking and a security group  
- [x] I installed and accessed a web server  
- [x] I monitored instance performance  
- [x] I resized instance and storage  
- [x] I tested termination protection  

---

## Outcome

By completing this lab, I am now able to:
- Launch and configure EC2 instances  
- Manage security and access  
- Monitor performance using CloudWatch  
- Scale compute and storage resources  
- Understand instance protection mechanisms  
