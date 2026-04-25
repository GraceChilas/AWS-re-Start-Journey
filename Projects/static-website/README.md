# Static Website Project

## Description
This project demonstrates hosting a static website using AWS services.

## Concepts Demonstrated
- Static website hosting
- Cloud architecture basics
- Deployment principles

After Hours Cafe – AWS Cloud Migration Project
## 📌 Project Overview

After Hours Cafe is a beloved local coffee shop facing operational challenges due to outdated on-premises systems and limited online presence. To improve efficiency, scalability, and customer engagement, the cafe migrated its IT infrastructure to the cloud using Amazon Web Services (AWS).

This project presents a high-level AWS cloud architecture that supports:

- Static website hosting
- Scalable compute services
- Secure database management
- Serverless processing
- Secure authentication
- Migration from on-premises systems

---

## 🎯 Project Objectives

- Migrate existing infrastructure to AWS Cloud
- Improve operational efficiency
- Provide a scalable and reliable environment
- Develop a cloud-hosted website for menu display
- Enhance customer engagement
- Ensure high availability and security

---

## 🏗️ Architecture Overview

The architecture is divided into the following core layers:

---

## 1️⃣ Compute Services

- Amazon EC2
- Hosts web and application servers
- Provides scalable compute capacity
- Supports Auto Scaling for workload fluctuations
- AWS Lambda
- Executes serverless functions
- Processes events such as orders or uploads
- Reduces infrastructure management

---

## 2️⃣ Storage Services

- Amazon S3
- Hosts static website (HTML, CSS, JavaScript, images)
- Provides highly durable and scalable storage
- Enables static website hosting
- Supports custom domain configuration
- Amazon EBS
- Provides persistent block storage for EC2
- Stores database and application data

## 3️⃣ Database Services

- Amazon RDS
- Hosts relational databases (menu items, orders)
- Supports Multi-AZ deployment for high availability
- Amazon DynamoDB
- Stores NoSQL data (customer profiles, preferences)
- Offers low-latency performance

---

## 4️⃣ Security Services

- AWS IAM
- Manages user roles and access permissions
- Secures AWS resources
- Amazon Cognito
- Handles customer authentication
- Manages user sign-up and sign-in
- Protects customer data

---

## 5️⃣ Migration Services

- AWS Database Migration Service
- Migrates on-premises databases to AWS
- Ensures minimal downtime
- AWS Server Migration Service
- Migrates virtual machines to EC2
- Replicates existing servers into AWS

---

## 🌐 Website Hosting

The FreshlyGround website is hosted using:

- Amazon S3 Static Website Hosting
- HTML, CSS, and JavaScript files stored in an S3 bucket
- Public access configured securely
- Custom domain support for branding

This approach is:

- Cost-effective
- Scalable
- Easy to maintain
- Highly available

---

## 💰 Cost Considerations

Estimated costs depend on:

- EC2 instance types and usage hours
- S3 storage size and requests
- RDS instance class and storage
- DynamoDB read/write capacity
- Lambda execution time and requests

Cost optimization strategies:

- Use Reserved Instances where applicable
- Enable Auto Scaling
- Monitor usage with AWS Cost Explorer

---

## 🔐 Security & Best Practices

- IAM roles applied to EC2 and Lambda
- Encryption at rest (S3, EBS, RDS)
- Multi-AZ deployment for high availability
- Principle of least privilege
- Secure authentication using Cognito

---

## 📊 Benefits of This Architecture

✔ Improved operational efficiency
✔ High scalability
✔ Increased reliability
✔ Secure customer authentication
✔ Reduced infrastructure management
✔ Cost-effective static website hosting

---

## 🚀 Future Enhancements

- Implement CI/CD using AWS CodePipeline
- Add CloudFront for global content delivery
- Integrate payment gateway services
- Enable real-time analytics
- Add monitoring using CloudWatch

---

## 📁 Project Deliverables

- AWS Architecture Diagram
- README Documentation
- Static Website (HTML/CSS)
- Cost Estimation Overview
