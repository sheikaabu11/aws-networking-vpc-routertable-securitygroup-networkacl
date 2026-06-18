<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-security)

**Author:** Sheika Abuthair  
**Email:** sheikaabuthaircyber11@gmail.com

---

## VPC Traffic Flow and Security

![Image](http://learn.nextwork.org/compassionate_red_daring_abiu/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a service that allows you to create your own private network within AWS where you can launch and manage resources such as EC2 instances, databases, and applications. It gives you control over networking features like IP address ranges, subnets, route tables, security groups, and internet access.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a custom private network for my AWS resources. I created a VPC, configured public subnets, attached an Internet Gateway, and set up route tables to enable internet connectivity. I also worked with security groups and network ACLs to control network traffic and improve security. This allowed me to understand how AWS networking components work together to provide secure and controlled access to resources within the cloud environment.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how many components are required to enable internet access for resources in a VPC. I initially thought that attaching an Internet Gateway would be enough, but I learned that route tables, subnet associations, and security rules also need to be configured correctly. This project showed me how multiple AWS networking components work together to provide secure and reliable connectivity.

### This project took me...

This project took me 30 mins


---

## Route tables

Route tables are networking components in Amazon VPC that contain a set of rules, called routes, which determine where network traffic is directed. They control how data travels between resources within a VPC, other networks, and the internet.

A route table is required to make a subnet public because it provides the routing instructions that allow resources in the subnet to reach the internet. Even if an Internet Gateway is attached to the VPC, the subnet will not have internet access unless its route table contains a route that directs internet-bound traffic (0.0.0.0/0) to the Internet Gateway.

![Image](http://learn.nextwork.org/compassionate_red_daring_abiu/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

A route's destination specifies the range of IP addresses that the traffic is intended for, while the target defines where that traffic should be sent. For example, in a public subnet, a route with the destination 0.0.0.0/0 represents all IPv4 addresses on the internet, and the target is the Internet Gateway (IGW) attached to the VPC.

My new route's destination is 0.0.0.0/0, which represents all IPv4 addresses on the internet. The target is the Internet Gateway (IGW) attached to the VPC.

![Image](http://learn.nextwork.org/compassionate_red_daring_abiu/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are virtual firewalls in Amazon VPC that control inbound and outbound traffic for AWS resources such as EC2 instances.

### Inbound vs Outbound rules

An inbound rule is a rule in a security group that controls the incoming traffic allowed to reach an AWS resource, such as an EC2 instance. It specifies the type of traffic, protocol, port number, and source that are permitted to connect to the resource.

An outbound rule is a rule in a security group that controls the traffic leaving an AWS resource,

![Image](http://learn.nextwork.org/compassionate_red_daring_abiu/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs (Access Control Lists) are an additional layer of security in Amazon VPC that control inbound and outbound traffic at the subnet level. T

### Security groups vs. network ACLs

A Security Group acts like a security guard at the door of your house (EC2 instance). It decides who can enter or leave that specific house. If you allow someone in, the return traffic is automatically allowed as well.

A Network ACL acts like a security checkpoint at the entrance of the entire neighborhood (subnet). It checks all traffic coming into and leaving the neighborhood. Unlike a security group, it requires separate rules for both incoming and outgoing traffic.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a Network ACL in AWS allows all inbound and outbound traffic. This means the default Network ACL contains rules that permit any traffic to enter and leave the subnet, regardless of protocol, port, or source/destination IP address. The default rules are designed to ensure that resources can communicate without restrictions until custom security rules are added. However, AWS also includes a final catch-all rule that denies any traffic not explicitly matched by an allow rule.

A custom Network ACL allows you to define specific rules that either allow or deny network traffic entering or leaving a subnet. Each inbound and outbound rule specifies a protocol, port range, and source or destination IP address range. Based on these conditions, the rule determines whether the traffic is permitted or blocked. Unlike the default Network ACL, which allows all traffic, a custom Network ACL gives you more control by letting you explicitly allow only the traffic you need and deny unwanted traffic for better security.

![Image](http://learn.nextwork.org/compassionate_red_daring_abiu/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

---

---
