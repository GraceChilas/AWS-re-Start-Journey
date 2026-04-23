# AWS Auto Scaling Lab 

## Task 1: Creating an AMI for Auto Scaling

In this task, I create an AMI from the existing Web Server 1. This
action saves the contents of the boot disk so that I can launch new
instances with identical content.

On the AWS Management Console, I enter **EC2** in the search bar and
open the Amazon EC2 Management Console.

I navigate to **Instances**, select **Web Server 1** (Running), and
create an image: - Image name: **Web Server AMI** - Description: **Lab
AMI for Web Server**

I choose **Create image** and note the AMI ID.



## Task 2: Creating a Load Balancer

I create an Application Load Balancer named **LabELB**.

These are the configurations for ALB:

-   VPC: **Lab VPC**
-   Subnets: **Public Subnet 1 & 2**
-   Security Group: **Web Security Group**

I create a target group: 
-   Name: **lab-target-group** 
-   Type: **Instances**

I attach the target group and create the load balancer. I copy the DNS
name for later use.



## Task 3: Creating a Launch Template

I create a launch template named **lab-app-launch-template**.

These are the configurations for my template

-   AMI: **Web Server AMI**
-   Instance type: **t3.micro**
-   Key pair: **None**
-   Security group: **Web Security Group**

I create and confirm the template.



## Task 4: Creating an Auto Scaling Group

I create an Auto Scaling group named **Lab Auto Scaling Group**.

These are the configuratios for my auto-scaling group

-   VPC: **Lab VPC**
-   Subnets: **Private Subnet 1 & 2**
-   Load balancer: **lab-target-group**
-   Health check: **ELB**

### Capacity:

-   Desired: 2
-   Min: 2
-   Max: 4

### Scaling Policy:

-   Metric: CPU Utilization
-   Target: 50%

I add tag: 
-   Key: Name 
-   Value: Lab Instance



## Task 5: Verifying Load Balancing

I confirm two instances are running.

In **Target Groups**, I verify both instances are **healthy**.

I open the load balancer DNS and confirm the app loads successfully.



## Task 6: Testing Auto Scaling

I go to **CloudWatch Alarms** and monitor **AlarmHigh**.

I run a load test from the application.

After a few minutes: 
-   CPU exceeds 50% 
-   Alarm triggers 
-   New instances launch automatically

I verify additional instances in EC2.



## Task 7: Terminating Web Server 1

I select **Web Server 1** and terminate it, as it is no longer needed.


## Objectives

After completing this lab, I was able to:

•	Create an AMI from an EC2 instance.

•	Create a load balancer.

•	Create a launch template and an Auto Scaling group.

•	Configure an Auto Scaling group to scale new instances within private subnets.

Use Amazon CloudWatch alarms to monitor the performance of your infrastructure

