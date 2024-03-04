+++
date = "2024-02-29"
title = "Active Directory: Configuration and Set up"
slug = "Active Directory: Configuration and Set up"
categories = [ "Post"]
tags = [ "Active Directory", "Users and Computers"]
katex = true
+++
# Introduction
Thank you for visiting my blog once again. In this post, we will discuss the setup of Active Directory, DHCP configuration, and account setup. It's important to note that this setup drew significant inspiration from Josh Madakor's HomeLab tutorial, which you can find at using belwo link:
> "https://www.youtube.com/watch?v=MHsI8hJmggI&t=1904s".

# laboratory Network Setup
Let's start by exploring the HomeLab setup. Our HomeLab utilizes Oracle VM VirtualBox to host virtual machines, including Windows 10 for client-side computers and Server 2019 for server hosting.

Within the Windows Server 2019 OS, we've implemented a `Domain Controller (DC)` with dual `Network Interface Card (NIC)` adapters, utilizing `DHCP` for dynamic IP configuration.

![alt](/img/homeLab/configurationSetup/window10.PNG)

To enhance security, we've segregated the network into internal and external segments, with the internal network incorporating additional security features.

Regarding the internal network configuration for the server OS, we've configured one NIC with a `static IP address of 172.16.0.1`, `subnet mask of 255.255.255.0`, and `DNS of 127.0.0.1`. 

Additionally, the external network (internet-facing) employs `DHCP with a range of 172.16.0.100 to 172.16.0.200`, `subnet mask of 255.255.255.0`, `gateway of 172.168.0.1`, and `DNS pointing to 172.16.0.1`.

For the Active Directory installation, a domain with the `Fully Qualified Domain Name (FQDN)` of `mydomain.com` has been created.

**The images below represent the overall structure for our HomeLab setup and Virtual Machine setup**
1. HomeLab structure Diagram
![alt](/img/homeLab/configurationSetup/ADsetup.drawio.PNG) 
2. Virtual Machine Setup
![alt](/img/homeLab/configurationSetup/setup.PNG) 
3. DNS setup
![alt](/img/homeLab/configurationSetup/DNSSetup.PNG) 
4. DHCP setup
![alt](/img/homeLab/configurationSetup/DHCPSetup.PNG) 

# Account and Group Setup

For the account setup, we utilized pre-built Organizational Units (OUs): one for users and another for administrators. For security purposes, the admin OU is exclusively managed by me. The images below provide examples of the user accounts and permissions.

1. User account OU setup
![alt](/img/homeLab/configurationSetup/accountSetup.PNG) 
2. Admin account setup
![alt](/img/homeLab/configurationSetup/adminAccountSetUp.PNG) 

# Computer Setup

Currently, we have one computer connected via the internal network within the domain. We'll be expanding our network as needed in the future if necessary.

1. User account OU setup
![alt](/img/homeLab/configurationSetup/computerSetup.PNG) 

**Thank you for taking the time to visit my post. I hope you found the information valuable and insightful. Stay tuned for more updates and articles on Active Directory Post. Until next time, take care!**