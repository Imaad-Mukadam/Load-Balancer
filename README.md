# Lets Learn how to setup Azure load Balancer

## Objective
The main objective of setting up an Azure Load Balancer is to distribute incoming network traffic across multiple backend resources to ensure high availability, scalability, and fault tolerance. 

## What is Azure Load Balancer Service?
Azure load Balancer Allows efficent distribution of load or incoming network traffic across a group of backend rescources or servers.

## How it works?

Backend Pool is a group of VMs that will handle the request.

In case of scale sets backend pool is updated automatically.

A static public (virtual) IP can be assigned thus making it a public load balancer.

Otherwise for private IP it is internal load balancer.

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/fe6d5b2ac3f7c5788d6d54807b0fafb7f431ba4f/loadbalancer.PNG)

## Load Balancer terms
Typically terms for Load Balancers are

*Frontend IP Configurations* - private or public IP

*Backend Pools* - Group of servers

*Health probes* - monitoring of backend pool health

*Load Balancing rules* - Traffic distribution of backend pool

*Inbound NAT rules* - binding of specific IP/port to specific instance in backend pool

*Outbound rules* - control outgoing traffic

## Step - 1

Creating 2 VMs and adding a load Blancer on VMs

*Creating First VM*(Web-1)

*Keep in Avaibility set*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/2dbf0b0c856c88c494057b3df10d3a73c47dd752/web-1-1.PNG)

*Create a availibility set with any name*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/ba45cb7da980a3e09670a5f31d7776e3050be24e/AvailabilitySet.PNG)

*Select these ports to access website we host on VM*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/55a2ae50ec676fc1b2c9ad76ca9726f3115c55c9/ports.PNG)

*Do review and create now*

## Step - 2

*Create another Virtual Machine with same configurations*(Web-2)
(Make sure you depoy both VMs in same avaibility set and Resource Group)

Connect your Web-1 VM 

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e20d18c6fed13a8323d016cc3e411814db34b010/connect-web-1.PNG)

Now download the RDP file or use other method to connect

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/f0df842b7fbce7a6777c22a280ed08ac59d3c71f/RDP.PNG)
