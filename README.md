# AWS and Terraform – Concepts, Components, and EC2 Deployment Guide
**1.Introduction to AWS**

Amazon Web Services (AWS) is a cloud computing platform that offers on-demand access to computing resources over the internet. Rather than purchasing and managing physical servers, storage, and networking infrastructure, customers can use these services from AWS and scale them as needed.
AWS operates on a pay-as-you-use model, and customers are charged only for the services they use.

**2.Core AWS Concepts**

**2.1 Region**

A region is a geographical area where AWS has established multiple data centers.
Example:

ap-south-1 (Mumbai)

us-east-1 (N. Virginia)

Selecting a region determines where your resources will be hosted.

**2.2 Availability Zone (AZ)**

An Availability Zone is an isolated data center in a region. Each region has multiple AZs.

Using multiple AZs provides high availability and redundancy.

**2.3 EC2 (Elastic Compute Cloud)**

EC2 is a virtual computer in the cloud. It offers computing power to run applications.
Main components of EC2:
1.Instance Type (CPU & RAM)

2.AMI (Operating System)

3.Key Pair (secured login)

4.Security Group (firewall rules)

**2.4 VPC (Virtual Private Cloud)**
A VPC is a private network in AWS where resources such as EC2 instances are launched.

It enables control over:

a)IP address ranges

b)Subnets

c)Routing

d)Security

**2.5 Subnet**

A subnet is a smaller network within a VPC. It helps to organize and segregate resources.

**2.6 Security Group**

A security group is a virtual firewall that manages inbound and outbound traffic for resources.

**Typical rules:**

>Allow SSH (port 22)

>Allow HTTP (port 80)

>Allow HTTPS (port 443)

**2.7 Key Pair**

Key pairs are employed for secure authentication of EC2 instances rather than passwords.

It comprises of:

>Public key (stored in AWS)

>Private key (.pem file, stored by user)

**3. What is Terraform?**

Terraform is an Infrastructure as Code (IaC) tool that is employed to define, create, and manage cloud infrastructure using configuration files.

Rather than creating resources manually through the cloud console, Terraform enables automation of the process using code.

**4. Why Terraform is Used**

Automation of infrastructure creation

Consistency across environments

Easy replication of resources

Version control of infrastructure

Less manual errors

**5. Terraform Core Components**
   
**5.1 Provider**

A provider specifies the cloud platform that Terraform will work with.

Example:

AWS provider

**5.2 Resource**

A resource specifies what kind of infrastructure resource needs to be created.

Examples:

**EC2 instance**

**VPC**

**Security group**

**5.3 Variables**

Variables enable reusability of Terraform code.

Variables prevent hardcoding of values.

**5.4 State File**

Terraform maintains the details of the resources created in a state file. This is useful for Terraform to keep track of changes and manage the infrastructure accordingly.

**6. Terraform Workflow**

Terraform has a predefined workflow:

**terraform init – Initializes the working directory and downloads the necessary providers**

**terraform plan – Displays the resources to be created or altered**

**terraform apply – Deploys the resources**

**terraform destroy – Deletes all the resources created**

7. Steps to Launch an EC2 Instance Manually in AWS
   
Step 1: Login to AWS Console

     Login to the AWS Management Console and choose a region (example: Mumbai).

Step 2: Open EC2 Service

     Search for EC2 in the services menu and click on it.

Step 3: Launch Instance

     Click on Launch Instance.

Step 4: Choose AMI

     Choose an Amazon Machine Image like Ubuntu Linux.

Step 5: Choose Instance Type

     Choose an instance type like t2.micro.

Step 6: Create or Select Key Pair

     Create a new key pair and download the .pem file.

Step 7: Configure Network Settings

    Choose VPC

    Choose subnet

    Enable auto-assign public IP

Step 8: Configure Security Group

Allow necessary ports:

    SSH (22)

    HTTP (80)

Step 9: Launch Instance

    Review and click Launch.

The EC2 instance will be launched successfully.

8. Launching an EC2 Instance Using Terraform
Step 1: Install Terraform

       Make sure Terraform is installed on the local machine.

Step 2: Create Project Directory

     Create a project directory to hold Terraform configuration files.

Step 3: Provider Configuration

     Terraform is set up to connect to AWS with access credentials.

Step 4: Define EC2 Resource

     The parameters of the EC2 instance, including AMI, instance type, key pair, and security group, are defined in Terraform configuration files.

Step 5: Initialize Terraform

    Run terraform init to initialize the environment.

Step 6: Plan Infrastructure

    Run terraform plan to examine what Terraform will create.

Step 7: Apply Configuration

    Run terraform apply to launch the EC2 instance.

Step 8: Resource Cleanup

    Run terraform destroy to remove all resources created when no longer needed.
 
**9. Conclusion**

AWS offers scalable cloud infrastructure, and Terraform helps to automate and ensure consistency in the management of these resources. Knowledge of AWS services and Terraform concepts helps to efficiently create, manage, and delete infrastructure in a systematic and repeatable manner.
