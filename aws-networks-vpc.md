<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)

**Author:** muluthukubura@gmail.com  
**Email:** muluthukubura@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate building a virtual private cloud. by creating an Amazon VPC, a public subnet, and an internet gateway. I'm doing this project because setting up and managing a VPC is a vital skill for anyone looking to master cloud infrastructure.

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service that lets you create your own isolated network within AWS. It allows you to launch and manage AWS resources in a private environment, separate from other users’ resources. By creating subnets inside the VPC, you can organize your resources and control how they communicate, ensuring better security and flexibility.

In today's project, I used Amazon VPC to create a private cloud environment and allocated IP addresses within the range 10.0.0.0 to 10.0.255.255 using an IPv4 CIDR block. I then created a subnet to subdivide this environment, assigning IP addresses from 10.0.0.0 to 10.0.0.255. Finally, I set up an Internet Gateway and attached it to the subnet to enable communication between the VPC and the outside world (Public Internet).

### Personal reflection

This project took me one and a half hours to understand all the concepts while doing each step.

One thing I didn’t expect in this project was how easy it was to use AWS CloudShell to create the VPC, subnet, and Internet Gateway. The integrated environment made the process straightforward and efficient, allowing me to manage resources without needing to set up a local configuration.

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will access the VPC console and create a VPC.

### How VPCs work

A Virtual Private Cloud (VPC) is what allows AWS resources to be private to you. Think of your AWS region as a country—within that country, a VPC is like managing your own city. - Without VPCs, all AWS resources would exist in one giant, open space in the cloud, like a country without cities or districts. - With a VPC, you gain control over your resources, deciding how they communicate and integrate with each other.
This setup lets you organize your infrastructure securely, without exposing everything to the public internet.



### Why there is a default VPC in AWS accounts

There was already a default VPC in my account ever since my AWS account was created. This is because to help you get things quickly started, this VPC lets you launch resources like EC2 instances and RDS databases. Letting you test AWS resources without needing to set up VPC from scratch.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is a range of IP addresses that my VPC can allocate to the resources deployed in my VPC.

---

## Subnets

### What I did in this step

In this step, I will create a subnet inside the VPC because it allows me to divide the VPC into smaller sections, organize resources, and control how they are accessed.

### Creating and configuring subnets

Subnets are subsections of a VPC, similar to how neighborhoods are subdivisions within a city. In my AWS account, subnets are automatically created—one for each availability zone in the region where I set up my VPC. Since my region is Asia Pacific (Mumbai), which contains three availability zones, I already have three default subnets available.


### Public vs private subnets

The difference between public and private subnets lies in the accessibility of the resources inside them. - For example, if we are running a public-facing website, it needs to be accessible from the internet. In this case, the EC2 instance hosting the website should be launched in a public subnet. - On the other hand, the application’s database, which stores sensitive data, should not be directly accessible from the internet. It only needs to communicate with the EC2 instance, so it should be placed in a private subnet. - A subnet is considered public if it has a route to an Internet Gateway. Without this route, the subnet is private by default.





![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled auto-assign public IPv4 addresses. By default, resources in a subnet only receive private IP addresses, which allow internal communication within the VPC but not direct access to the internet. To make an instance accessible from or able to connect to the internet, it must have a public IP address. Enabling this setting ensures that any instance launched in the subnet automatically receives a public IP, so that it can communicate with the internet without requiring manual configuration


---

## Internet gateways

### What I did in this step

In this step, I will create an internet gateway because it provides a path for communication between my VPC and the outside world.

### Setting up internet gateways

Internet gateways are the key VPC components that allow internet access for the resources in my VPC/subnet. An internet gateway is also how users in the public can access my resources in a public subnet.


Attaching an internet gateway means resources in your VPC can now access the internet. The EC2 instances with public IP addresses also become accessible to users, so your applications hosted on those servers become public too.


![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will open a handy tool called AWS CloudShell to run commands. Using CloudShell, I can execute AWS CLI commands to set up a VPC, subnet, and Internet Gateway. Engineers often rely on the CLI to automate tasks with scripts, which makes it an essential tool for managing cloud environments efficiently.


### Exploring CloudShell and CLI

CloudShell is a browser-based shell for running AWS commands, while the CLI is the command-line tool engineers use to interact with and automate AWS services.

### Debugging my setup

To set up a VPC or a subnet, you can use the following AWS CLI commands:

- aws ec2 create-vpc --cidr-block 10.0.0.0/24 --query Vpc.VpcId --output text

- aws ec2 create-tags --resources vpc-0e983a011188763e6 --tags Key=Name,Value="Network VPC 2"

- aws ec2 create-subnet --vpc-id vpc-0e983a011188763e6 --cidr-block 10.0.0.0/24

When creating a subnet, make sure to include the --cidr-block option (for example, 10.0.0.0/24). This ensures that IP addresses are properly assigned to your subnet and helps avoid configuration errors.


![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

---

---
