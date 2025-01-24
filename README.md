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

# SUMMARY

In this project, I will launch two virtual machines (VMs), install the IIS web server on both, and host a website on each server. Then, I will configure a load balancer. Once the load balancer is set up, I will test its functionality by determining which VM it redirects traffic to. For example, if the load balancer redirects traffic to Web-1, I will shut down the Web-1 VM to verify that the load balancer seamlessly redirects traffic to the second VM (Web-2) without any issues.


## Step - 1

Creating 2 VMs and adding a load Blancer on VMs

*Creating First VM*(Web-1)

*Keep in Avaibility set*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/2dbf0b0c856c88c494057b3df10d3a73c47dd752/web-1-1.PNG)

*Create an availability set with any name of your choice*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/ba45cb7da980a3e09670a5f31d7776e3050be24e/AvailabilitySet.PNG)

*Select these ports to access the website hosted on the VM.*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/55a2ae50ec676fc1b2c9ad76ca9726f3115c55c9/ports.PNG)

*Proceed with 'Review and Create' now.*




## Step - 2




*Create another virtual machine with the same configurations.*(Web-2)

(Ensure both VMs are deployed in the same availability set and resource group.)

Connect your Web-1 VM 

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e20d18c6fed13a8323d016cc3e411814db34b010/connect-web-1.PNG)

Now, download the RDP file or use an alternative method to connect.

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/f0df842b7fbce7a6777c22a280ed08ac59d3c71f/RDP.PNG)

*Do similar for the 2nd VM*

Navigate to 'Add Roles and Features' (follow the same process on both VMs).

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/4b861cdb4c338606864a36c508b5a16572dcb565/roles.PNG)

*click next to add IIS server*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/4b861cdb4c338606864a36c508b5a16572dcb565/next.PNG)

*click on Web Server IIS*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/4b861cdb4c338606864a36c508b5a16572dcb565/IIS.PNG)

*click on Add Features*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/4b861cdb4c338606864a36c508b5a16572dcb565/AddFeatures.PNG)

*INSTALL WEB SERVER IIS*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/4b861cdb4c338606864a36c508b5a16572dcb565/install.PNG)




## Step - 3




*open file manager, go into C Drive*

*click on inetpub folder*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/21449ae5768426429876eabbe33a552812516b27/inpt.PNG)

*Go into wwwroot folder*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/21449ae5768426429876eabbe33a552812516b27/wwwroot.PNG)

*Now open the iisstart file with notepad*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/21449ae5768426429876eabbe33a552812516b27/openW.PNG)

**"Make changes so we can identify where we are redirected."**

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/21449ae5768426429876eabbe33a552812516b27/edit.PNG)




## Step - 4





*Lets configure LOAD BALANCER*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/loadbalCreate.PNG)

*configure basic information*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/basic.PNG)

*Frontend-IP configuration*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/frontendIP.PNG)

*Add IP configuration to Backend Pool*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/backendpool.PNG)

*Configure Inbound Rules*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/inbound.PNG)

*Click on 'Review and Create'.*

*Click on 'Go to Resources'.*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/lbComplete.PNG)

*Copy the IP address and paste it into the browser.*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/LBIP.PNG)

*The traffic is currently directed to Web-1.*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/Result.PNG)

*We will shut down the Web-1 VM to verify whether the load balancer redirects us to Web-2.*

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/Web1Stop.PNG)

**"The load balancer successfully redirects us to Web-2."**

![image alt](https://github.com/Imaad-Mukadam/Load-Balancer/blob/e694671340656a5777a7b4abe9fd5bb0809b2bf8/2ndResult.PNG)
