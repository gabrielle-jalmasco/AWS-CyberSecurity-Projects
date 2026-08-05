<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://nextwork.ai/projects/aws-networks-security)

**Author:** Gabrielle G. Jalmasco  
**Email:** jalmascogab002@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a virtual network dedicated to your AWS account where you can launch AWS resources in a logically isolated section of the AWS cloud. It is useful because it gives you full control over your network environment, including IP address ranges, subnets, route tables, and security settings, allowing you to securely manage and isolate your resources.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a secure and functional public subnet by setting up a VPC, creating a public subnet, attaching an Internet Gateway, configuring route tables, security groups, and network ACLs to control traffic flow and secure access to resources.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the detailed distinction and interplay between security groups and network ACLs, especially how network ACLs operate statelessly at the subnet level while security groups are stateful at the instance level

### This project took me...

This project took me approximately 60 minutes to complete, including setting up the network components, configuring security, and validating the setup through guided steps and quizzes.

---

## Route tables

Route tables are sets of rules that determine where network traffic from your subnet or VPC is directed. Each route specifies a destination IP range and a target (where to send the traffic).

Route tables are needed to make a subnet public because they define the path for outbound traffic to reach the internet. Without a route directing traffic to an Internet Gateway, resources in the subnet cannot communicate outside the VPC.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Routes are defined by their destination and target, which mean...

Destination: The IP address range or CIDR block that the route applies to (e.g., 0.0.0.0/0 means all IPv4 addresses).

Target: The gateway or resource where the traffic should be sent (e.g., an Internet Gateway for internet-bound traffic).

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 and a target of the Internet Gateway (IGW) attached to my VPC.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are virtual firewalls attached to AWS resources (like EC2 instances) that control inbound and outbound traffic at the instance level. They define which traffic is allowed to reach or leave the resource based on rules.

### Inbound vs Outbound rules

Inbound rules specify the types of incoming traffic that are allowed to reach the resource.
Inbound rules are the permissions that control what traffic can enter the resource. I configured an inbound rule that allows HTTP traffic (Type: HTTP, Port 80) from any IP address (0.0.0.0/0), enabling web access to the resource from the internet.

Outbound rules specify the types of outgoing traffic that are allowed to leave the resource.
Outbound rules are the permissions that control what traffic can exit the resource. By default, my security group's outbound rule allows all outbound traffic (all protocols, all ports) to any destination (0.0.0.0/0), enabling the resource to communicate freely with external networks.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs (Access Control Lists) are stateless, subnet-level firewalls that control inbound and outbound traffic to and from subnets within a VPC. They consist of numbered rules that allow or deny traffic based on protocol, port range, and source/destination IP.

### Security groups vs. network ACLs

The difference between a security group and a network ACL is that security groups are stateful and operate at the instance level, meaning they remember allowed traffic and automatically allow response traffic. Network ACLs are stateless and operate at the subnet level, requiring explicit rules for both inbound and outbound traffic.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will allow all traffic. The default ACL allows all inbound and outbound IPv4 and IPv6 traffic.

In contrast, a custom ACL’s inbound and outbound rules are automatically set to deny all traffic until you explicitly add rules to allow specific traffic. This means you must define rules to permit desired traffic flows.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

---

---
