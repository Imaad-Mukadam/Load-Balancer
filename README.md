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

## Load Balancer terms
Typically terms for Load Balancers are

*Frontend IP Configurations* - private or public IP

*Backend Pools* - Group of servers

*Health probes* - monitoring of backend pool health

*Load Balancing rules* - Traffic distribution of backend pool

*Inbound NAT rules* - binding of specific IP/port to specific instance in backend pool

*Outbound rules* - control outgoing traffic

## Steps
drag & drop screenshots here or use imgur and reference them using imgsrc

Every screenshot should have some text explaining what the screenshot is about.

Example below.

*Ref 1: Network Diagram*
