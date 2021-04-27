# Intro to Security Groups
Intro
-----

Security Groups are the fundamental of network security in AWS

They control how traffic is allowed into or out of our EC2 Machines

![](Intro%20to%20Security%20Groups/image.png)

it is the most fundamental skill to learn to troubleshoot netowrking issues

in this lecture we will learn how  to use them to allow, inbound and outbound ports

Deeper
------

Security Groups are basically “firewalls” on an EC2 instance

they regulate:

*   Access to Ports
*   Authorized IP ranges - IPv4 & IPv6
*   Control of inbound network (from other to the instance) 
*   Control of outbound network (from the instance to other)

### Good to know

*   Can be attached to multiple instances
*   Locked down to region / VPC compination
*   Lives outside of EC2 instance - if traffic is blocked by security group the EC2 instance won't see it
*   It's good to maintain one separate security group for SSH access
*   if you application is not accessible (time out) then it's a security group issue
*   if app gives a connection refused error then it's an application error
*   All inbound traffic is blocked and all outbound traffic is authorized

Referencing other security groups

![](Intro%20to%20Security%20Groups/2_imag