<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://nextwork.ai/projects/aws-networks-vpc)

**Author:** Gabrielle G. Jalmasco  
**Email:** jalmascogab002@gmail.com

---

## Build a Virtual Private Cloud (VPC)

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project I'll create a new VPC and a public subnet, attach an Internet Gateway, and enable auto‑assign public IPv4 addresses for the subnet. I'll use an IAM user (not root), choose a nearby region, configure the VPC CIDR as 10.0.0.0/16 and the subnet as 10.0.0.0/24, and clean up/delete resources when finished to avoid charges.

### What is Amazon VPC?

Amazon VPC is a virtual network in AWS that provides isolated, secure, and customizable cloud infrastructure for launching and managing resources. It is useful because it provides secure, isolated, and customizable networking for AWS resources, enabling control over traffic and connectivity.

I used Amazon VPC to create a custom virtual network with public and private subnets, attached an Internet Gateway, and configured routing to enable secure internet access for resources.

### Personal reflection

This project took me about 30 minutes in total.

One thing I didn't expect in this project was how crucial attaching the Internet Gateway and configuring route tables are for enabling internet access in the VPC.

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step I will create a new VPC in the AWS Management Console. I’ll sign in as an IAM user (not root), switch to a nearby Region, open the VPC console, choose Create VPC → VPC only, name it NextWork VPC, and set the IPv4 CIDR to 10.0.0.0/16. I’ll confirm creation and record the VPC ID for later cleanup.

### How VPCs work

A Virtual Private Cloud (VPC) is a logically isolated section of a cloud provider's network, such as AWS, where you can launch and manage your cloud resources in a virtual network that you define. It provides you with control over your network environment, including IP address ranges, subnets, route tables, and network gateways.

### Why there is a default VPC in AWS accounts

The default VPC in myAWS account exists to provide a ready-to-use, pre-configured virtual network environment that allows me to immediately launch and run AWS resources without needing to set up a custom VPC.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

An IPv4 CIDR block is a way to specify a range of IP addresses using Classless Inter-Domain Routing (CIDR) notation. It defines the network portion and the host portion of an IP address range in a compact format.

---

## Subnets

### What I did in this step

In this step I will create a subnet in NextWork VPC named Public 1 in the first Availability Zone with CIDR 10.0.0.0/24, then enable auto-assign public IPv4 addresses so instances receive public IPs.

### Creating and configuring subnets

Subnets divide a VPC’s IP address range into smaller segments, allowing you to organize and isolate resources within the virtual network.

### Public vs private subnets

A subnet is not considered public until it has a route to an Internet Gateway in its route table, enabling direct internet access for resources within it.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Enabling auto-assign public IPv4 addresses ensures that instances launched in the subnet automatically receive public IPs, allowing them to communicate directly with the internet.

---

## Internet gateways

### What I did in this step

In this step I will create an Internet Gateway (NextWork IG) and attach it to the NextWork VPC so resources in the VPC can reach and be reached from the internet.

### Setting up internet gateways

An Internet Gateway is a VPC component that enables communication between the VPC and the internet by routing traffic and performing network address translation for public IP addresses.

Attaching an internet gateway to a VPC means enabling resources in the VPC to communicate with the internet; if I missed this step, instances with public IPs would not have internet access, keeping the subnet effectively private.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this secret mission, I am building a Virtual Private Cloud (VPC) in AWS by creating a custom VPC with a specific IPv4 CIDR block, setting up subnets (including a public subnet), attaching an Internet Gateway to enable internet access, and configuring the network so that resources within the VPC can communicate securely and efficiently both internally and with the internet.

### Exploring CloudShell and CLI

CloudShell is a browser-based shell environment for managing AWS resources, and CLI (Command Line Interface) is a tool to interact with AWS services via commands typed in a terminal.

### Debugging my setup

I ran into an error because a required step or configuration was missed or incorrect, such as missing permissions, incorrect CIDR blocks, or not attaching necessary components like the Internet Gateway.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Setting up VPC resources in CloudShell allows for quick, scriptable, and repeatable infrastructure management compared to manual console setup, improving efficiency and automation.

---

---
