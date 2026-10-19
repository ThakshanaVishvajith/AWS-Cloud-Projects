<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Creating a Private Subnet

**Project Link:** [View Project](https://nextwork.ai/projects/4e96e29d-98b8-551e-ae93-da39c36e30fd)

**Author:** muluthukubura@gmail.com  
**Email:** muluthukubura@gmail.com

---

![Image](https://nextwork.ai/passionate_vermilion_joyful_wood_apple/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_afe1fdbd)

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is virtual private cloud create on the giant open space in the cloud. It is useful because the resources in the VPC can made private to you.You also get control over resources in a VPC, so you can organize how they communicate and integrate with each other without the public internet.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a public subnet and a private subnet.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is how easy it is to create inbound and outbound traffic rules for the subnet and their resources using network ACLs and security groups.

### This project took me...

This project took me 30 minutes to understand the core cloud concepts while doing practical examples.

## Private vs Public Subnets

The difference between public and private subnets is that the route table associated with the public subnet has a route to the internet gateway, and the route table associated with the private subnet does not have a route to the internet gateway; it only has a route that manages internal traffic within the VPC.

Having private subnets are useful because keeping resources away from the internet is extremely important for the security of confidential resource data

My private and public subnets cannot have the same IPv4 CIDR block, i.e., the same range of IP addresses. The CIDR block for every subnet must be unique and cannot overlap with another subnet.

![Image](https://nextwork.ai/passionate_vermilion_joyful_wood_apple/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_afe1fdbd)

## A dedicated route table

By default, my private subnet is associated with the default route table, i.e., a route table that has a route to an internet gateway.

I had to set up a new route table because my subnet can not have a route to an internet gateway.

My private subnet's dedicated route table only has one inbound and one outbound rule that allows internal communication, i.e., with a destination of another resource within VPC.

![Image](https://nextwork.ai/passionate_vermilion_joyful_wood_apple/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_b4b904b5)

## A new network ACL

By default my private subnet is associated with the default route table, i.e., a route table that has a route to an internet gateway.

I set up a dedicated network ACL for my private subnet because the private subnet cannot have a route to an internet gateway,

My new network ACL has two simple rules – inbound and outbound rules that allow internet communication, i.e., with a destination of another resource within my VPC.

![Image](https://nextwork.ai/passionate_vermilion_joyful_wood_apple/uploads/4e96e29d-98b8-551e-ae93-da39c36e30fd_1ed2cb07)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/4e96e29d-98b8-551e-ae93-da39c36e30fd)*
