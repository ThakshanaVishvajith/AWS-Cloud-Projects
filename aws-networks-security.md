<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-security)

**Author:** muluthukubura@gmail.com  
**Email:** muluthukubura@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a logically isolated section of the AWS cloud within a specific region. It allows you to provision and manage your AWS resources in a secure, private environment. With a VPC, you gain full control over your networking setup, including IP address ranges, subnets, route tables, network ACLs and gateways.


### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to design a secure and functional environment.
I created a subnet within the VPC to host my resources.
I attached an Internet Gateway to the VPC, enabling communication between my subnet and the public internet.
I configured a route table to manage inbound and outbound traffic, directing internet-bound traffic through the internet gateway.
To secure individual resources, I set up a security group that controlled access to my EC2 instance at the instance level.
Additionally, I implemented a network ACL (Access Control List) to provide an extra layer of security at the subnet level.










### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that AWS had already created a default security group and network ACL for the default VPC in my AWS region.

### This project took me...

This project took me one and a half hours to understand the concept and implement it.

---

## Route tables

Route tables are like GPS that direct traffic within my VPC to the correct destination.


Route tables are needed to make a subnet public because a subnet needs to have a route to an internet gateway in order to consider the subnet public.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

The destination is the range of IP addresses that traffic in my VPC is trying to reach. The target is the road/path that the traffic will use to get to their destination. 

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 and a target of my IG-Thakshana (Internet Gateway)


![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are like security guards that monitor both inbound and outbound traffic at the resource level. i.e. every single resource in a subnet/VPC has a security group.

### Inbound vs Outbound rules

Inbound rules are the rules that monitor/restrict inbound traffic, e.g., users visiting a web app I'm hosting.


Outbound rules are the rules that monitor/restrict outbound traffic, e.g., my web app requesting data from a public source.
By default, an outbound rule will allow all outbound traffic.
I also configured an inbound rule that allows all inbound HTTP traffic.


![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs are like community watchmen that secure my network at a subnet level.


### Security groups vs. network ACLs

The difference between a security group and a network ACL is their scope, i.e., a security group secures my network at the resource level (So every single resource in my VPC is associated with a security group), while  network ACLs secured my network at the subnet level (every single subnet in my VPC is associated with a network ACL.)


---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

A default network ACL's inbound rule is set up to allow all incoming traffic

A default network ACL's outbound rule is set up to allow all outgoing traffic.


In contrast, a custom ACL's inbound and outbound rules are automatically set to deny all incoming/outgoing traffic. 


![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

I created  an additional VPC , internet gateway and security group Instead of my usual region, I used AWS CloudShell to create those. Teams would use multiple regions for

Improve latency for their end users, which means apps run faster because resources are physically closer to the users' location.
Protect themselves from natural disasters and other risks—if one region experiences an outage, other regions can maintain operations.


EC2 Global View is a tool where you can find and manage your EC2 and VPC resources across all AWS Regions from a single dashboard.  I could even narrow down my search by selecting global search. Without EC2 Global View, you'd have to switch between regions to track your resources.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-networks-security_b03ea6162)

---

---
