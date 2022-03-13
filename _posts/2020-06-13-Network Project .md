---
layout: post
title: Network Project 
date: 2020-06-13
Author: Ali Cheng
categories: 
tags: [Network System]
comments: true
---

# Project overview

> Our project is to design an information technology infrastructure for Optimus Consultants. In the past, Optimus Consultants has suffered a series of IT disasters, which caused the company to lose important information. Delayed project completion and lose of customer. Realizing the importance of information technology infrastructure, the new CEO of Optimus Consultants decided to deploy a reliable and scalable information technology infrastructure to ensure the company\'s efficient operations.
>
> Optimus Consultants will have multiple branches in Auckland, Whangarei, Thames, Tauranga, Rotorua, Palmerston North, and New Plymouth, and the company\'s headquarters will be located in Hamilton. The company will employ about 100 employees and their roles will be structural engineer, civil engineer, technician, management, accounting, payroll, marketing and office manager / receptionist. At the same time, the new information technology infrastructure can support employees to work from home.
>
> Optimus Consultants\' business is to provide specific designs for the construction of residential houses and commercial buildings, roads, subdivisions and public facilities. The company will establish contact with the client-builder or architect and carry out specific designs. For example, when designing a house beam, a project manager is assigned to the project, and one or more engineers use AutoCAD, MS Excel or other engineering software to design. Drawings and calculation reports are then generated and checked by senior engineers. Finally, issue a report invoice to the customer and deliver the report to the customer after the customer pays.
>
> I will divide the implementation of the entire project into 3 main phases:
>
> First of all, I will have a specific Proposed Design. The Proposed Design will present a more specific diagram of component connections and possible technologies used. Also, I will analyse the reasons for using these technologies.
>
> Second, I will use the GNS3 to create the entire project. I will use ASA firewalls, routers, and switches. And realize the construction of each server in computers.
>
> Finally, during the project stage, I will record the configuration, which will include the detailed deployment process, technical complexity, and working solution.

# Research

> There are many ways can be for fulfilling the needs of this project. Both Windows and Linux are very suitable platforms for deploying related servers. In this part, I will list the required service deployments and give several possible technologies to complete these deployments.

## Technology Analysis

-   **Directory services**

> **Active Directory** is a popular Directory service that can centrally manage users, computers, and other objects on the network. Its main function is to authenticate and authorize users and computers in the Windows domain (Rackspace Support ,2016, p.1). It is supported on both Linux and Windows. Compared with Linux, Windows Active Directory provides a good interface interaction.
>
> **OpenDJ** is a **directory server** written based on JAVA, supporting access control and function expansion. This software supports Linux and Windows. OpenDJ provides a high-performance Vertical Scalability directory server (vharseko,2020, p.1). it is known for the simplest and fastest directory to deploy and manage (p.1).
>
> Windows Active Directory provides a good interface interaction.

-   **Domain controller**

> [**Microsoft**](https://en.wikipedia.org/wiki/Microsoft_Servers) **Domain controllers** are used to control or manage all computers in the domain. You can create and delete user accounts from it, and grant or revoke access. It can provide a safe management mode. **Active Directory** can be used as a Domain controller.
>
> **Zentyal** is a Domain controller server based on Ubuntu system. Zentyal integrates many open source components, and it also has the Microsoft Exchange Server protocol (Wikipedia, 2020, p.1). Therefore, it supports the native compatibility of the Microsoft Outlook client.

-   **DHCP and DNS**

> By setting the IP address pool, **DHCP** can automatically assign IP addresses to devices on the network without manually configuring IP addresses, and can also avoid IP conflicts. **DNS** is used to connect to a specific network computer or the Internet. It can resolve domain names by IP address or IP by domain name. Both DNS and DHCP can create services on **Windows**.
>
> **ASA firewall and Router** can also quickly set up DNS and DHCP servers, it usually only needs a few codes to achieve. It is a very fast and efficient deployment method.

-   **Deployment/imaging Services**

> **Windows Deployment Services** supports the deployment of Windows operating systems. Users can use WDS to implement network-based installation to set up the client, so other users can directly install related systems through the network without relying on USB or CD for installation.
>
> **Microsoft Deployment Toolkit** is a tool for automating desktop and server deployment. It can reduce deployment time and standardize desktop and server images (Microsoft, n.d., p.1). MDT also enables you to manage security and ongoing configuration more easily (p.1). It can effectively reduce the complexity and time of deployment in an enterprise environment (p.1).

-   **Data Storage**

> As a **shared file**, because of the need to consider permissions, **FTP** server seems to be a very good choice. The authorization of FTP is clearer, and each file can be authorized intuitively.
>
> In addition, setting a **shared folder** directly on the network is also an option, but it is more complicated than FTP in setting permissions.

-   **Virtual Private Network**

> There are many popular **VPN** servers nowadays, and there are **remote connections** based on **PPPoE**, which can be easily created under **Windows**.
>
> **ASA firewall** provides an **SSL VPN** which is more secure. SSL is a popular remote VPN mode. It can provide **Web-based** connections and can automatically guide users to install related VPN clients via the Web (F5 GLOSSARY, n.d., p.1).

-   **Authentication server**

> **Network Policy Server** in **Windows** can provide an **Authentication server**. When a remote user connects, the Network Policy Server will start the authentication service.
>
> In addition, the **ASA firewall** has the **AAA** authentication protocol. Compared to creating a RADIUS server on Windows, the AAA server is easier to configure.

-   **Data backup**

> **Shadow Copy** is usually required for a file transfer server. It is very easy to open in **Windows**. Shadow Copy can be used to restore the functionality of earlier versions of files.
>
> If we are concerned about data security, we can rely on some open source backup software, such as **Areca Backup**.

# Project Methodology

## Waterfall

The Waterfall methodology was very helpful to this project. This project is divided into many small tasks. Each task can represent a stage. It is almost impossible to change the order between these tasks.

From Network Project Propal, from this task, we can understand the background, needs and plans of the entire project. First of all, I learned the basic information of the company and the overall project direction. The second is the Project scope, which can help me to conduct a demand analysis, for example, what services do I need to set up the server need to include. Then, you can have an understanding of the technology of the project, and finally consider how to plan the time. Network Project Propal allows me to have a good understanding of the project and clarify my goals.

Design document is an important plan document before the actual operation. We first need to plan a rough network topology diagram, and then start to design the server, such as Active Directory, we need to design its role in each site, and staff distribution. In addition, this task also allows us to conduct a lot of technical research and give at least two options for each requirement to increase the flexibility of the entire project.

After Design document, we really started to implement, according to our previous Desing document ideas, to implement the entire project. It can be said that Design Document provides great convenience for actual operation, it makes the actual operation very clear. If the use of Design document is not used, I may have no direction on the implementation.

Project Report can be said to be a review of the entire project, including the overall needs and goals of the project. It also includes our initial design ideas and final design results. Project Report depends on previous tasks. If any task is not completed, it will affect the Project Report.

## Effective

The Waterfall methodology defines a very clear working idea, it can serve my time plan well, because each task will stipulate the completion time, so the entire task will not appear very complicated and difficult to start.

Secondly, each task is actually serving the next task. For example, Design document plays a great role in guiding the implementation. It can make me more aware of what I need to accomplish and how to accomplish it in Implementation.

## Other methodology considerations

Agile is also an excellent methodology, but it is not very helpful for this project. Agile provides a very flexible management method, which is very suitable for projects with more changes. But the complexity of the project is not high, and the task assignment is very clear. Secondly, Agile generally does not have a clear fixed plan, which may make the progress management of the project very messy. Therefore, The Waterfall methodology is a very good choice for this project.

# Design

## Final network diagram

![img](https://github.com/AliChenggggg/blog/tree/main/images/2020-06-13-Project/image001.jpg)

Figure 1 Final network Diagram

## Technologies used

There are many ways can be for fulfilling the needs of this project. Both Windows and Linux are very suitable platforms for deploying related servers. However, for this project I will focus on using Windows. In this part, I will describe the technology that I use for this project.

-   **Active Directory**

Active Directory is a popular Directory service that can centrally manage users, computers, and other objects on the network. Its main function is to authenticate and authorize users and computers in the Windows domain (Rackspace Support ,2016,p.1). It is supported on both Linux and Windows. Compared with Linux, Windows Active Directory provides a good interface interaction.

-   **DNS and DHCP**

Both DNS and DHCP can create services on Windows。By setting the IP address pool, DHCP can automatically assign IP addresses to devices on the network without manually configuring IP addresses, and can also avoid IP conflicts. DNS is used to connect to a specific network computer or the Internet. It can resolve domain names by IP address or IP by the domain name.

-   **FTP**

As a shared file, because of the need to consider permissions, the FTP server seems to be a very good choice. The authorization of FTP is more clear, and each file can be authorized intuitively. In addition, setting a shared folder directly on the network is also an option, but it is more complicated than FTP in setting permissions.

-   **VPN**

There are many popular VPN servers nowadays, and there are remote connections based on PPPoE, which can be easily created under Windows. However, the ASA firewall provides a SSL VPN which is more secure. SSL is a popular remote VPN mode. It can provide Web-based connections and can automatically guide users to install related VPN clients via the Web (F5 GLOSSARY, n.d., p.1).

-   **AAA**

Network Policy Server in Windows can provide an Authentication server. When a remote user connects, the Network Policy Server will start the authentication service. In addition, the ASA firewall has the AAA authentication protocol. Compared to creating a RADIUS server on Windows, the AAA server is easier to configure.

-   **Shadow Copy and Areca Backup**

Shadow Copy is usually required for a file transfer server. It is very easy to open in Windows. Shadow Copy can be used to restore the functionality of earlier versions of files. To further increase data security, I used Areca Backup, an open-source backup software. It can provide good backup service and can generate a one-click backup script, and back up the data after appropriate.

## Design considerations

Network design needs to consider many factors, such as cost and complexity.

The overall network structure will be considered in a very simple way. In the early days, I did not need to consider redundant settings. Considering that the whole company has only about 110 employees, and Hamilton, which has the most employees, also has only 35 employees, so I do n't think the network topology should be very complicated. Based on the analysis of Hamilton with the largest number of employees, 35 employees will not be a heavy burden on the server. I think it is unnecessary to build redundant servers.

There are many aspects of cost. In addition to the cost of equipment, there are also heat dissipation, maintenance, and space settings for the equipment. If there are more equipment in the area, the required fan heating and maintenance costs will also increase. Therefore, in order to comprehensively consider the cost aspect and the security aspect, a firewall and a main switch can support a network structure with certain security and lower cost.

Physical design is also an important part of network design. If the network structure is complex and there are many devices, companies often consider setting up a data centre separately. This often adds a lot of cost. For the network structure I designed, the company only needs to consider buying a network equipment cabinet, which is large enough to fit into a firewall, two switches, and a server.

The difficulty of maintenance is also an important consideration. Considering that the entire company has only one IT staff, if the network structure and server are complex, the work will be very difficult. Although I gave up the consideration of redundancy, the entire network structure looks unreliable. However, the simple network structure is often easier to maintain. When a fault occurs, IT staff can quickly eliminate the problem and restore the network at a very fast rate.

## Meet/enhance the user requirements

-   **local server**

The local server needs to satisfy the authentication of all users, the assignment of permissions, and the access control to the server. Directory services such as Active Directory can be used to manage users very well. All company members will join the company\'s domain, so the company can control all employees.

After the employee joins the domain, everyone has a unique identity, and the employee needs to be authenticated to enter the system. Non-company members cannot log into the company domain and cannot access the server. DNS and DHCP are obtained automatically when the user successfully logs in to the company domain, and no manual configuration is required by employees.

The FTP server can perform very convenient rights management. For example, if an employee comes from the Structural Engineers group, when accessing the FTP server, only the Structural Engineers folder can be viewed. The FTP server also needs to be authenticated.

-   **Remote access**

VPN is a popular remote access technology. ASA provides any connect VPN that allows employees to work from home, and connecting to the company\'s internal network also requires authentication, which depends on the AAA server.

-   **Data security**

Data security is a very important factor, because the company has suffered serious losses due to data loss. Therefore, when considering data, I consider using both methods of data protection. The first is Shadow Copy, which is used to retrieve older version of documents. The second is data backup by using Areca Backup, which is an open source software with high security, and the second is that it generates backup scripts. We only need to run periodically, such as adding a backup task to the windows task scheduler, to let the system automatically run scripts periodically.

# Implementation

## Basic network configuration

### ISP Router

-   Set up the DNS server

1.  ip name-server 1.1.1.1  

2.  ip domain-lookup  

-   Give IP address for each port. Then set the port NAT settings, which stipulate the data flow direction when the router works

1.  interface F0/0  

2.  ip address dhcp  

3.  ip nat outside  

4.  no shutdown  

5.    

6.  interface F1/0  

7.  ip address 202.14.63.3 255.255.255.0  

8.  ip nat inside  

9.  no shutdown 

-   Set ACL to allow all traffic from 202.14.63.0 to pass

1.  access-list 10 permit 202.14.63.0 0.0.0.255  

-   Enable dynamic NAT for internal source address translation

1.  ip nat inside source list 10 **int** F0/0 overload  

### Router of Remote User

-   Set up the dns server

1.  ip name-server 1.1.1.1  

2.  ip domain-lookup  

-   Give IP address for each port. Then set the port NAT settings, which stipulate the data flow direction when the router works

1.  interface f 0/0  

2.  ip address 202.14.63.141 255.255.255.0  

3.  ip nat outside  

4.  no shutdown  

5.    

6.  interface f 0/1  

7.  ip address 192.168.0.1 255.255.255.0  

8.  ip nat inside  

9.  no shutdown  

-   Set a static route, the next hop address is 202.14.63.3

1.  ip route 0.0.0.0 0.0.0.0 202.14.63.3  

-   Set ACL to allow all traffic from 192.168.0.0 to pass

1.  access-list 10 permit 192.168.0.0 0.0.0.255  

-   Enable dynamic NAT for internal source address translation

1.  ip nat inside source list 10 **int** F0/0 overload  

### ASA Firwall

####  Hamilton

-   Set the inside port ip address, it will be used as the default gateway address, and set the Security-level to 70. This configuration is for FTP server area.

1.  ASA-H# conf t                       

2.  ASA-H(config)# **int** g0/0  

3.  ASA-H(config-if)# nameif FTP

4.  ASA-H(config-if)# security-**level** 70  

5.  ASA-H(config-if)# ip **add** 172.16.1.1 255.255.0.0  

-   Set the inside port ip address, it will be used as the default gateway address, and set the Security-level to 100. This configuration is for inside network area.

6.  ASA-H# conf t                       

7.  ASA-H(config)# **int** g0/1  

8.  ASA-H(config-if)# nameif inside  

9.  ASA-H(config-if)# security-**level** 100  

10. ASA-H(config-if)# ip **add** 172.15.1.1 255.255.0.0  

-   Set the out port ip address, and set Security-level to 0.

> Areas with high security levels can directly access areas with low security levels, but areas with low security levels cannot directly access areas with high security levels.

1.  ASA-H(config)# **int** management 0/0  

2.  ASA-H(config-if)# nameif outside  

3.  ASA-H(config-if)# security-**level** 0  

4.  ASA-H(config-if)# ip **add** 202.14.63.142 255.255.255.0  

5.  ASA-H(config-if)# **no** sh  

-   Set up a static route to allow the external port to find the address 202.14.63.3 to connect to the Internet.

1.  ASA-H(config)#route outside 0 0 202.14.63.3  

-   Configure address translation using PAT and network objects. By setting PAT, clients on the intranet can access the Internet through a public network address. This configuration is for FTP server area.

1.  ASA-H(config)#object network INSIDE-FTP  

2.  ASA-H(config-network-object)#subnet 172.16.0.0 255.255.0.0  

3.  ASA-H(config-network-object)#nat （inside,outside）**dynamic** interface  

4.  ASA-H(config-network-object)#end

-   Configure address translation using PAT and network objects. By setting NAT, clients on the intranet can access the Internet through a public network address. This configuration is for inside network area.

5.  ASA-H(config)#object network INSIDE-NET  

6.  ASA-H(config-network-object)#subnet 172.15.0.0 255.255.0.0  

7.  ASA-H(config-network-object)#nat （inside,outside）**dynamic** interface  

8.  ASA-H(config-network-object)#end

-   Set the ACL to allow the icmp protocol to pass. The Icmp protocol can allow ping packets to pass, which can be used for network connectivity testing.

1.  ASA-H(config)#access-list outside extended permit icmp any any   

2.  ASA-H(config)#access-**group** outside in interface outside   

####  Auckland

1.  ASA-A# conf t                  

2.  ASA-A(config)# **int** g0/0  

3.  ASA-A(config-if)# nameif inside  

4.  ASA-A(config-if)# security-**level** 100  

5.  ASA-A(config-if)# ip **add** 172.17.2.1 255.255.0.0  

6.  ASA-A(config-if)# **no** sh  

7.  ASA-A(config)# **int** mgt0/0  

8.  ASA-A(config-if)# nameif outside  

9.  ASA-A(config-if)# security-**level** 0  

10. ASA-A(config-if)# ip **add** 202.14.63.143 255.255.255.0  

11. ASA-A(config-if)# **no** sh  

12. ASA-A(config)#route outside 0 0 202.14.64.3  

>  

13. ASA-A(config)#object network INSIDE-NET  

14. ASA-A(config-network-object)#subnet 172.17.0.0 255.255.0.0  

15. ASA-A(config-network-object)#nat （inside,outside）**dynamic** interface  

16. ASA-A(config-network-object)#**end**  

>  

17. ASA-A(config)#access-list outside extended permit icmp any any   

18. ASA-A(config)#access-**group** outside in interface outside   

####  Whangarel               

1.  ASA-W# conf t 

2.  ASA-W(config)# **int** g0/0  

3.  ASA-W(config-if)# nameif inside  

4.  ASA-W(config-if)# security-**level** 100  

5.  ASA-W(config-if)# ip **add** 172.17.2.1 255.255.0.0  

6.  ASA-W(config-if)# **no** sh  

7.  ASA-W(config)# **int** mgt0/0  

8.  ASA-W(config-if)# nameif outside  

9.  ASA-W(config-if)# security-**level** 0  

10. ASA-W(config-if)# ip **add** 202.14.63.144 255.255.255.0  

11. ASA-W(config-if)# **no** sh  

12. ASA-W(config)#route outside 0 0 202.14.64.3  

>  

13. ASA-W(config)#object network INSIDE-NET  

14. ASA-W(config-network-object)#subnet 172.18.0.0 255.255.0.0  

15. ASA-W(config-network-object)#nat （inside,outside）**dynamic** interface  

16. ASA-W(config-network-object)#**end**  

>  

17. ASA-W(config)#access-list outside extended permit icmp any any   

18. ASA-W(config)#access-**group** outside in interface outside   

####  Thames

1.  ASA-T# conf t 

2.  ASA-T(config)# **int** g0/0  

3.  ASA-T(config-if)# nameif inside  

4.  ASA-T(config-if)# security-**level** 100  

5.  ASA-T(config-if)# ip **add** 172.17.2.1 255.255.0.0  

6.  ASA-T(config-if)# **no** sh  

7.  ASA-T(config)# **int** mgt0/0  

8.  ASA-T(config-if)# nameif outside  

9.  ASA-T(config-if)# security-**level** 0  

10. ASA-T(config-if)# ip **add** 202.14.63.145 255.255.255.0  

11. ASA-T(config-if)# **no** sh  

12. ASA-T(config)#route outside 0 0 202.14.64.3  

>  

13. ASA-T(config)#object network INSIDE-NET  

14. ASA-T(config-network-object)#subnet 172.19.0.0 255.255.0.0  

15. ASA-T(config-network-object)#nat （inside,outside）**dynamic** interface  

16. ASA-T(config-network-object)#**end**  

>  

17. ASA-T(config)#access-list outside extended permit icmp any any   

18. ASA-T(config)#access-**group** outside in interface outside   

## Site Server Configuration

###  Directory Services and Domain Controller

-   Active Directory is a relatively easy-to-use Directory Services. It will automatically generate a Domain Controller after the AD server is successfully installed. The installation of AD server is very simple, only need to choose to install Active Directory Domain Services in Server Manager.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image2.png){width="5.768055555555556in" height="4.057638888888889in"}

Figure 2 Active Directory Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image3.png){width="5.768055555555556in" height="4.020833333333333in"}

Figure 3 Active Directory Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image4.png){width="5.768055555555556in" height="4.0375in"}

Figure 4 Active Directory Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image5.png){width="5.768055555555556in" height="4.051388888888889in"}

Figure 5 Active Directory Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image6.png){width="5.768055555555556in" height="4.013888888888889in"}

Figure 6 Active Directory Installation

-   After the Active Directory installation is successful, you need to configure it, including the generated Forest settings and Root domain name.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image7.png){width="5.768055555555556in" height="4.034027777777778in"}

Figure 7 Active Directory Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image8.png){width="5.768055555555556in" height="3.890277777777778in"}

Figure 8 Active Directory Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image9.png){width="5.768055555555556in" height="4.2131944444444445in"}

Figure 9 Active Directory Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image10.png){width="5.768055555555556in" height="4.236805555555556in"}

Figure 10 Active Directory Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image11.png){width="5.768055555555556in" height="4.201388888888889in"}

Figure 11 Active Directory Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image12.png){width="5.768055555555556in" height="4.205555555555556in"}

Figure 12 Active Directory Configuration

-   After the Active Directory configuration is complete, you can start adding domain users and creating management groups, and then classify users by department. Users can be better managed after being classified, including authorization management, login management etc

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image13.png){width="5.768055555555556in" height="3.6902777777777778in"}

Figure 13 Active Directory user and group setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image14.png){width="5.768055555555556in" height="3.0506944444444444in"}

Figure 14 Active Directory user setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image15.png){width="5.768055555555556in" height="3.422222222222222in"}

Figure 15 Active Directory user setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image16.png){width="5.768055555555556in" height="3.44375in"}

Figure 16 Active Directory user setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image17.png){width="5.768055555555556in" height="4.538194444444445in"}

Figure 17 Active Directory group setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image18.png){width="5.768055555555556in" height="4.5472222222222225in"}

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image19.png){width="5.768055555555556in" height="3.6465277777777776in"}

###  DHCP 

-   The DHCP server can automatically provide IP address services for clients. Installing DHCP requires selecting and installing the DHCP server in server management.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image20.png){width="5.768055555555556in" height="4.077083333333333in"}

Figure 19 DHCP Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image3.png){width="5.768055555555556in" height="4.020833333333333in"}

Figure 20 DHCP Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image4.png){width="5.768055555555556in" height="4.0375in"}

Figure 21 DHCP Installation

NNN![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image21.png){width="5.768055555555556in" height="4.086805555555555in"}

Figure 22 DHCP Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image22.png){width="5.812696850393701in" height="5.528570647419072in"}

Figure 23 DHCP Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image23.png){width="5.768055555555556in" height="4.228472222222222in"}

Figure 24 DHCP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image24.png){width="5.768055555555556in" height="4.198611111111111in"}

Figure 25 DHCP Configuration

-   After the DHCP installation is complete, you need to configure it. The first step is to create a new scope, set the address range that the server can distribute, the address range that cannot be distributed, and the default gateway.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image25.png){width="5.768055555555556in" height="3.3645833333333335in"}

Figure 26 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image26.png){width="5.768055555555556in" height="3.5902777777777777in"}

Figure 27 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image27.png){width="5.768055555555556in" height="4.270833333333333in"}

Figure 28 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image28.png){width="5.768055555555556in" height="4.196527777777778in"}

Figure 29 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image29.png){width="5.768055555555556in" height="4.070138888888889in"}

Figure 30 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image30.png){width="5.768055555555556in" height="4.156944444444444in"}

Figure 31 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image31.png){width="5.768055555555556in" height="4.355555555555555in"}

Figure 32 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image32.png){width="5.768055555555556in" height="4.352777777777778in"}

Figure 33 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image33.png){width="5.768055555555556in" height="4.315277777777778in"}

Figure 34 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image34.png){width="5.768055555555556in" height="4.293055555555555in"}

Figure 35 DHCP Scope setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image35.png){width="5.768055555555556in" height="4.352777777777778in"}

Figure 36 DHCP Scope setting

###  DNS

-   The main function of DNS is to perform IP address resolution. To install dns, you need to select and install a DNS server from service management.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image36.png){width="5.768055555555556in" height="5.45625in"}

Figure 37 DNS Installation

-   After the installation is complete, basic configuration of the DNS server is required, including the name given to the Zone, and DNS server Forwarders. Forwarders are used to send resolution requests to other DNS servers when the local DNS server cannot resolve the address.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image37.png){width="5.768055555555556in" height="2.9625in"}

Figure 38 DNS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image38.png){width="5.768055555555556in" height="3.966666666666667in"}

Figure 39 DNS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image39.png){width="5.768055555555556in" height="4.747222222222222in"}

Figure 40 DNS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image40.png){width="5.768055555555556in" height="4.750694444444444in"}

Figure 41 DNS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image41.png){width="5.768055555555556in" height="4.715277777777778in"}

Figure 42 DNS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image42.png){width="5.768055555555556in" height="4.725694444444445in"}

Figure 43 DNS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image43.png){width="5.768055555555556in" height="4.710416666666666in"}

Figure 44 DNS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image44.png){width="5.768055555555556in" height="2.901388888888889in"}

Figure 45 DNS Configuration

-   After the basic configuration of the DNS server is completed, a New Zone needs to be created. This Zone is to add the address to be resolved or forward.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image45.png){width="5.768055555555556in" height="3.716666666666667in"}

Figure 46 DNS Function setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image46.png){width="5.768055555555556in" height="4.745138888888889in"}

Figure 47 DNS Function setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image47.png){width="5.768055555555556in" height="4.741666666666666in"}

Figure 48 DNS Function setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image48.png){width="5.768055555555556in" height="3.7444444444444445in"}

Figure 49 DNS Function setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image49.png){width="5.768055555555556in" height="4.764583333333333in"}

Figure 50 DNS Function setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image50.png){width="5.768055555555556in" height="4.73125in"}

Figure 51 DNS Function setting

###  Deployment/Imaging Services

-   The WDS server can provide a window system installation channel through the network. To install WDS, you need to choose to install Windows deployment services in Service management, and check Deployment Server and transport server in Role services.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image51.png){width="5.768055555555556in" height="4.096527777777778in"}

Figure 52 WDS Server Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image52.png){width="5.768055555555556in" height="5.461805555555555in"}

Figure 53 WDS Server Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image53.png){width="5.768055555555556in" height="5.468055555555556in"}

Figure 54 WDS Server Installation

-   After the WDS server is installed, you need to create a group, then add the windows install image and boot image.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image54.png){width="5.768055555555556in" height="3.326388888888889in"}

Figure 55 WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image55.png){width="5.768055555555556in" height="5.2125in"}

Figure 56 WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image56.png){width="5.768055555555556in" height="3.290277777777778in"}

Figure 57 WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image57.png){width="5.768055555555556in" height="3.317361111111111in"}

Figure 58 WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image58.png){width="5.768055555555556in" height="4.148611111111111in"}

Figure 59 WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image59.png){width="5.768055555555556in" height="4.151388888888889in"}

Figure 60 WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image60.png){width="5.768055555555556in" height="4.50625in"}

Figure 61WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image61.png){width="5.768055555555556in" height="4.502083333333333in"}

Figure 62 WDS Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image62.png){width="5.768055555555556in" height="4.507638888888889in"}

Figure 63 WDS Configuration

###  Storage Server

-   FTP is a very easy-to-use file sharing system. To install FTP, you first need to install Web server Role (IIS), then select FTP server in Role services.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image63.png){width="5.768055555555556in" height="5.501388888888889in"}

Figure 64 FTP Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image64.png){width="5.768055555555556in" height="5.481944444444444in"}

Figure 65 FTP Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image65.png){width="5.768055555555556in" height="4.0625in"}

Figure 66 FTP Installation

-   After the Web server Role (IIS) is created, a new FTP server needs to be created in the internet information services manager.

-   Before creating FTP, you need to create the corresponding certificate, next to start creating the FTP site, you need to give the FTP site name and Content directory, then select the mapped IP address, port, and SSL certificate. Finally, choose Authentication and Authorization information.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image66.png){width="5.768055555555556in" height="2.957638888888889in"}

Figure 67 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image67.png){width="5.768055555555556in" height="2.9555555555555557in"}

Figure 68 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image68.png){width="5.768055555555556in" height="3.2104166666666667in"}

Figure 69 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image69.png){width="5.768055555555556in" height="5.061805555555556in"}

Figure 70 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image70.png){width="5.768055555555556in" height="2.948611111111111in"}

Figure 71 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image71.png){width="5.768055555555556in" height="4.54375in"}

Figure 72 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image72.png){width="5.768055555555556in" height="5.080555555555556in"}

Figure 73 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image73.png){width="5.768055555555556in" height="5.1090277777777775in"}

Figure 74 FTP Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image74.png){width="5.768055555555556in" height="5.0784722222222225in"}

Figure 75 FTP Configuration

-   After the FTP is created, you need to set the privilege. According to the requirements, three folders need to be created, Department, Project, and user.

-   "Department" should only allow relevant departments to access relevant folders, so each file needs to be authorized by a separate department. For example, the Accounting subfolder needs to be given read permission to group Accounting

-   "Pproject" can only be accessed by the project manager and related employees. Of course, Accounting needs to have the right to read. Therefore, you need to create a separate subfolder for each Project manager and give the permissions corresponding to each project. For example, under the Ajay Nash file, you need to allow Ajay Nash to read and write permissions, and give the group Accounting permission to read.

-   "User" folder can only allow employees to access their own folders. However, IT administrators have the authority to modify all folders. Therefore, each User needs to be individually authorized. For example, the Ajay Nash subfolder needs to authorize Ajay Nash read and write permissions, and give the group IT Administrator read and write permissions.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image75.png){width="5.768055555555556in" height="3.9923611111111112in"}

Figure 76 FTP Privilege setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image76.png){width="5.768055555555556in" height="4.009027777777778in"}

Figure 77 FTP Privilege setting

## Security

### Site to site Virtual Private Network

-   The most convenient way to set up site to site virtual private network on the ASA firewall is through ASDM.

-   Before setting up ASDM, you need to apply an http server on the ASA firewall and allow specific IP addresses to access it.

1.  Ciscoasa (config)# http server enable

2.  Ciscoasa (config)# http 172.16.1.0 255.255.255.0 inside

    -   After the setting is completed, you can download and install ASDM by accessing the asa firewall address through http (ASDM requires java support, so you need to ensure that the system has Java programs when installing ASDM)

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image77.png){width="5.768055555555556in" height="3.56875in"}

Figure 78 ASDM Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image78.png){width="5.768055555555556in" height="4.092361111111111in"}

Figure 79 ASDM Installation

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image79.png){width="5.33379593175853in" height="4.067018810148731in"}

Figure 80 ASDM Installation

-   After the ASDM installation is complete, you can access the ASA firewall through ASDM, and you can use the graphical interface to set up the entire ASA firewall in ASDM.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image80.png){width="5.895472440944882in" height="2.8036034558180227in"}

Figure 81 Site to site Virtual Private Network Configuration

-   To create a site to site VPN, we first need to add the range of target IP addresses that can be accessed in the Access Rule, so we need to add the internal IP addresses of all sites.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image81.png){width="5.768055555555556in" height="3.591666666666667in"}

Figure 82 Site to site Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image82.png){width="5.2004505686789155in" height="2.683566272965879in"}

Figure 83 Site to site Virtual Private Network Configuration

-   After the Access Rule is added, start to create site to site VPN

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image83.png){width="5.768055555555556in" height="1.6847222222222222in"}

Figure 84 Site to site Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image84.png){width="5.768055555555556in" height="3.157638888888889in"}

Figure 85 Site to site Virtual Private Network Configuration

-   Site to site vpn needs to fill in the peer ip address, which is the external network address of another site. At the same time, you need to fill in the intranet address range of another site.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image85.png){width="5.768055555555556in" height="3.171527777777778in"}

Figure 86 Site to site Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image86.png){width="5.768055555555556in" height="3.1930555555555555in"}

Figure 87 Site to site Virtual Private Network Configuration

-   Add pre-shared key to ensure the security of site to site vpn connection

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image87.png){width="5.768055555555556in" height="3.152083333333333in"}

Figure 88 Site to site Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image88.png){width="5.768055555555556in" height="3.1368055555555556in"}

Figure 89 Site to site Virtual Private Network Configuration

-   Set up other sites in the same way

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image89.png){width="5.768055555555556in" height="3.5520833333333335in"}

Figure 90 Site to site Virtual Private Network Configuration

### Remote Virtual Private Network and Authentication Service

-   Remote VPN needs to set up anyconnect VPN Wizard in ASDM.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image90.png){width="5.768055555555556in" height="2.512153324584427in"}

Figure 91 Remote Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image91.png){width="5.768055555555556in" height="3.5854166666666667in"}

Figure 92 Remote Virtual Private Network Configuration

-   Set profile name and VPN access interface, and upload client image, this image will be used as a vpn client for remote workers.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image92.png){width="5.768055555555556in" height="3.5590277777777777in"}

Figure 93 Remote Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image93.png){width="5.768055555555556in" height="3.546527777777778in"}

Figure 94 Remote Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image94.png){width="5.768055555555556in" height="3.573611111111111in"}

Figure 95 Remote Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image95.png){width="5.768055555555556in" height="3.515972222222222in"}

Figure 96 Remote Virtual Private Network Configuration

-   After that, you need to add users who can access the intranet. By default, the AAA server will be used. Then, you need to add an address range that can use VPN

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image96.png){width="5.768055555555556in" height="3.501388888888889in"}

Figure 97 Remote Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image97.png){width="5.768055555555556in" height="3.522222222222222in"}

Figure 98 Remote Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image98.png){width="5.768055555555556in" height="3.5229166666666667in"}

Figure 99 Remote Virtual Private Network Configuration

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image99.png){width="5.768055555555556in" height="3.5076388888888888in"}

Figure 100 Remote Virtual Private Network Configuration

### Group Policy

-   Group policy can be used to publish some software that companies need. To set up a software release policy, you need to first create a shared file and put the software in the shared file.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image100.png){width="5.417135826771654in" height="5.3838003062117235in"}

Figure 101 Group Policy Setting

-   Group policy can be used to publish some software that companies need. To set up a software release policy, you need to first create a shared file and put the software in the shared file.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image101.png){width="5.768055555555556in" height="3.736111111111111in"}

Figure 102 Group Policy Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image102.png){width="5.768055555555556in" height="3.7708333333333335in"}

Figure 103 Group Policy Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image103.png){width="5.768055555555556in" height="4.256944444444445in"}

Figure 104 Group Policy Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image104.png){width="5.768055555555556in" height="4.166666666666667in"}

Figure 105 Group Policy Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image105.png){width="5.768055555555556in" height="4.697916666666667in"}

Figure 106 Group Policy Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image106.png){width="5.768055555555556in" height="4.129166666666666in"}

Figure 107 Group Policy Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image107.png){width="5.768055555555556in" height="3.640277777777778in"}

Figure 108 Group Policy Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image108.png){width="4.58373031496063in" height="4.900424321959755in"}

Figure 109 Group Policy Setting

### URL filtering

-   ASA firewall also supports URL filtering, first we need to find a URL filtering target.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image109.png){width="5.768055555555556in" height="3.0131944444444443in"}

Figure 110 URL filtering Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image110.png){width="5.768055555555556in" height="4.602083333333334in"}

Figure 111 URL filtering Setting

-   After determining the IP address to be filtered, add the URL filtering server in the ASA. After the addition is complete, you need to add a Web page filtering based on Https in Filter Rules.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image111.png){width="5.768055555555556in" height="4.790277777777778in"}

Figure 112 URL filtering Setting

### Data Backup

-   Data back can be used in many ways, Areca Backup can provide a software-based backup service, first of all we need to create a new backup for backup FTP server.

-   First, you need to be in the Open workspace and select the location you want to back up.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image112.png){width="5.768055555555556in" height="3.2645833333333334in"}

Figure 113 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image113.png){width="5.768055555555556in" height="4.779166666666667in"}

Figure 114 Data Backup Setting

-   Then right click in the blank space of the software to create New Group

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image114.png){width="4.21875in" height="1.5416666666666667in"}

Figure 115 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image115.png){width="5.768055555555556in" height="4.377777777777778in"}

Figure 116 Data Backup Setting

-   After the group is created, you can add a target for backup. Select the target location to be backed up in sources.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image116.png){width="4.708333333333333in" height="1.7083333333333333in"}

Figure 117 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image117.png){width="5.768055555555556in" height="4.229166666666667in"}

Figure 118 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image118.png){width="5.768055555555556in" height="3.8777777777777778in"}

Figure 119 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image119.png){width="5.768055555555556in" height="4.006944444444445in"}

Figure 120 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image120.png){width="5.768055555555556in" height="4.010416666666667in"}

Figure 121 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image121.png){width="5.768055555555556in" height="4.083333333333333in"}

Figure 122 Data Backup Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image122.png){width="5.645833333333333in" height="3.0625in"}

Figure 123 Data Backup Setting

-   After completing the backup settings, you can start the first backup.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image123.png){width="5.768055555555556in" height="4.297916666666667in"}

Figure 124 Data Backup Setting

-   In addition, Areca also provides backup script generation and backup strategy creation.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image124.png){width="5.768055555555556in" height="2.275in"}

Figure 125 Data Backup Setting

-   Shadow Copies is an almost necessary service in a shared file server. It can create a mirror history file and allow folders to be reverted at any time.

-   To open shadow copies, just right-click on the disk that needs to be opened and select Configure Shadow Copies, and select create now in Volume.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image125.png){width="5.768055555555556in" height="4.354166666666667in"}

Figure 126 Shadow Copies Setting

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image126.png){width="5.09375in" height="6.59375in"}

Figure 127 Shadow Copies Setting

### Security policy

> ⚫ **Identification and authentication policies**

-   The company\'s internal FTP is developed for all employees, and the FTP server has specific authorization settings.

-   All users need to log in to the FTP server using the account and password.

> Password policies
>
> ⚫ **Password policies**

-   Please modify your account password every month.

-   Your password should not be shorter than 7 characters.

-   The password for logging into the FTP server and the intranet should not be the same.

> ⚫ **Acceptable use policies**

-   Any malicious attack on the server will be investigated.

-   Don't share your password.

-   Don't try to log in with someone else's account.

> ⚫ **Remote access policies**

-   All users can access the company\'s internal resources by installing the vpn client, the most

-   It requires employees to carry out account and password to authorize access.

> ⚫ **Network maintenance policies**

-   Please do not install or update related software by yourself. The network management is responsible for updating together.

-   We will release a new version of the software to the client through the server and update it uniformly.

> ⚫ **Incident handling policies**

-   When a network failure occurs, please contact the network administrator in time

> for troubleshooting, please do not make changes to the settings yourself.

### Enterprise Security Strategy

> ⚫ **Internal training**
>
> Employee training is a means to maintain network security, it can make employees consciously prevent some social engineering attacks, such as phishing websites, spam ect.
>
> At the same time, it is necessary to train employees to have professional ethics and not to act beyond their authority
>
> ⚫ **Update security components in time**
>
> Cisco will provide anti-virus signature updates, so such information needs to be reviewed and updated in a timely manner.
>
> ⚫ **Pay attention to information security incidents**
>
> Be vigilant against the new types of cyber attacks nowadays, and implement them in a timely manner after the release of defense strategies. For example, the wannacry ransomware virus that occurred a few years ago, when it is confirmed to propagate through TCP port 445, we need to close the port in time to ensure security.

-   

# Testing

## Basic Service Test

### Directory Services and Domain Controller

-   Methodology

> Active Directory Domain Services is a combination of Directoty services and Domain controller. We can test whether the client can join the company\'s domain to test whether the server works normally. Active Directory can add domain users, so users should be able to use the users stored in Active Directory to Log in to the client. So the test can be divided into 2 parts:

1.  Test whether the client can join the domain

2.  Test whether the user created in AD server can log in to the client

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image127.png){width="5.768055555555556in" height="4.021527777777778in"}
>
> Figure 128 Active Directory Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image128.png){width="5.768055555555556in" height="4.5569444444444445in"}
>
> Figure 129 Active Directory Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image129.png){width="5.768055555555556in" height="4.529166666666667in"}
>
> Figure 130 Active Directory Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image130.png){width="5.768055555555556in" height="4.550694444444445in"}
>
> Figure 131 Active Directory Test

### DHCP

-   Methodology

> The DHCP server should be able to automatically give the client an ip address. DHCP requires the client to be set to DHCP mode, so you need to verify that DHCP requires:

1.  Test whether the client can obtain the correct IP address in the automatic address acquisition mode

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image131.png){width="5.768055555555556in" height="3.988888888888889in"}
>
> Figure 132 DHCP Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image132.png){width="5.768055555555556in" height="4.554861111111111in"}
>
> Figure 133 DHCP Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image133.png){width="5.768055555555556in" height="4.579166666666667in"}
>
> Figure 134 DHCP Test

### DNS

-   Methodology

> DNS can provide an address resolution service. In this project, DNS is set up to resolve local websites. It should need to have the ability to resolve IP addresses by domain name, and it can send requests to other DNS servers to resolve more Domain name or IP address. So verify DNS requirements:
>
> 1\. Use the "nslookup" command to test the area resolution service
>
> 2\. Test whether the client can browse the web normally
>
> 3\. Test whether the client can access the local website through the domain name.

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image134.png){width="5.768055555555556in" height="3.3256944444444443in"}
>
> Figure 135 DNS Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image135.png){width="5.768055555555556in" height="4.313194444444444in"}
>
> Figure 136 DNS Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image136.png){width="5.768055555555556in" height="4.543055555555555in"}
>
> Figure 137 DNS Test

### Deployment/Imaging service

-   Methodology

> Windows Deployment Services is a network-based installation server for window systems. For clients joining the domain, you need to be able to select the network through the bios interface to install the window system：
>
> 1\. Test whether the client can install windows from the network option in the BIOS.

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image137.png){width="5.768055555555556in" height="4.050694444444445in"}
>
> Figure 138 WDS Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image138.png){width="5.768055555555556in" height="3.829861111111111in"}
>
> Figure 139 WDS Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image139.png){width="5.768055555555556in" height="4.5375in"}
>
> Figure 140 WDS Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image140.png){width="5.768055555555556in" height="4.388888888888889in"}
>
> Figure 141 WDS Test

## File System Privilege Test

-   Methodology

> The FTP server is an open server of the entire company network, and its security is very important. FTP provides a very convenient access authorization management interface, and administrators can easily perform authorization management. Therefore, the verification methods are:
>
> 1\. All sites can access the FTP server including remote access
>
> 2\. The user can only access the folder where the department is located and personal folders. Cannot access other user or department folders.

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image141.png){width="5.768055555555556in" height="4.533333333333333in"}
>
> Figure 142 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image142.png){width="5.768055555555556in" height="4.685416666666667in"}
>
> Figure 143 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image143.png){width="5.768055555555556in" height="4.49375in"}
>
> Figure 144 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image144.png){width="5.768055555555556in" height="4.560416666666667in"}
>
> Figure 145 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image145.png){width="5.768055555555556in" height="4.501388888888889in"}
>
> Figure 146 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image146.png){width="5.768055555555556in" height="4.503472222222222in"}
>
> Figure 147 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image147.png){width="5.768055555555556in" height="4.500694444444444in"}
>
> Figure 148 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image148.png){width="5.768055555555556in" height="4.561111111111111in"}
>
> Figure 149 File System Privilege Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image149.png){width="5.768055555555556in" height="4.533333333333333in"}
>
> Figure 150 File System Privilege Test

## Server Security Test

### Site to Site Virtual Private Network

-   Methodology

> The purpose of site to site VPN is to allow other branches to access the FTP server. Therefore testing Site to site VPN requires:
>
> 1\. All branches internal clients can access the FTP server

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image150.png){width="5.768055555555556in" height="4.570833333333334in"}
>
> Figure 151 Site to site Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image142.png){width="5.768055555555556in" height="4.685416666666667in"}
>
> Figure 152 Site to site Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image151.png){width="5.768055555555556in" height="4.557638888888889in"}
>
> Figure 153 Site to site Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image152.png){width="5.768055555555556in" height="4.555555555555555in"}
>
> Figure 154 Site to site Virtual Private Network Test

### Remote Virtual Private Network

-   Methodology

> Remote Virtual Private Network provides employees with a channel to remotely connect to the company\'s internal server. To verify Remote VPN, try to use the Cisco AnyConnect Secure Mobility Client in the remote client to connect to the company\'s internal network. Using VPN requires AAA server authentication.Therefore testing remote VPN requires:
>
> 1\. Remote users need to access the public network address of the ASA firewall to log in and install the VPN client.
>
> 2\. The remote client needs to be able to access the FTP server through a VPN connection.

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image153.png){width="5.768055555555556in" height="3.953472222222222in"}
>
> Figure 155 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image154.png){width="5.768055555555556in" height="3.9125in"}
>
> Figure 156 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image155.png){width="5.768055555555556in" height="3.8604166666666666in"}
>
> Figure 157 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image156.png){width="5.150446194225721in" height="4.075353237095363in"}
>
> Figure 158 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image157.png){width="5.125444006999125in" height="2.6252274715660544in"}
>
> Figure 159 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image158.png){width="5.768055555555556in" height="4.714583333333334in"}
>
> Figure 160 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image159.png){width="5.768055555555556in" height="4.586111111111111in"}
>
> Figure 161 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image160.png){width="5.768055555555556in" height="4.595138888888889in"}
>
> Figure 162 Remote Virtual Private Network Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image141.png){width="5.768055555555556in" height="4.533333333333333in"}
>
> Figure 163 Remote Virtual Private Network Test

### Authentication service

-   Methodology

> AAA service is installed on the ASA firewall and used to authenticate remote access users. There are two ways to authenticate AAA server:
>
> 1\. Test whether users can connect to the intranet through VPN
>
> 2\. Check whether the AAA server has user access records

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image161.png){width="5.768055555555556in" height="5.399305555555555in"}
>
> Figure 164 Authentication service Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image157.png){width="5.125444006999125in" height="2.6252274715660544in"}
>
> Figure 165 Authentication service Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image159.png){width="5.768055555555556in" height="4.586111111111111in"}
>
> Figure 166 Authentication service Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image162.png){width="5.768055555555556in" height="5.317361111111111in"}
>
> Figure 167 Authentication service Test

### Group Policy

-   Methodology

> Group Policy is used to publish Auto CAD software on the internal network to verify the success of the Group Policy. You need to check whether the software installation program from the server can be found in programs and Features in the intranet client.

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image163.png){width="5.768055555555556in" height="4.247222222222222in"}
>
> Figure 168 Group Policy Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image164.png){width="5.768055555555556in" height="4.5881944444444445in"}
>
> Figure 169 Group Policy Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image165.png){width="5.768055555555556in" height="4.516666666666667in"}
>
> Figure 170 Group Policy Test

### URL filtering

-   Methodology

> For URL filtering, just open the web page to see if the filtered IP address can be displayed.

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image166.png){width="5.768055555555556in" height="4.570833333333334in"}
>
> Figure 171 URL filtering Test

### Data Backup

-   Methodology

> The software-based data backup needs to be restored and tested. If the file is deleted after it has been backed up, and the backup service needs to be able to restore the files again.

1.  First, we need to create a test.txt file as a test file

2.  Then perform the backup server

3.  Next delete the test.txt file

4.  Finally, use the software to restore the file

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image167.png){width="5.768055555555556in" height="4.552777777777778in"}
>
> Figure 172 Data Backup Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image168.png){width="5.768055555555556in" height="4.520138888888889in"}
>
> Figure 173 Data Backup Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image169.png){width="5.768055555555556in" height="4.542361111111111in"}
>
> Figure 174 Data Backup Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image170.png){width="5.768055555555556in" height="2.1104166666666666in"}
>
> Figure 175 Data Backup Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image171.png){width="5.768055555555556in" height="3.4118055555555555in"}
>
> Figure 176 Data Backup Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image172.png){width="5.768055555555556in" height="4.506944444444445in"}
>
> Figure 177 Data Backup Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image173.png){width="5.768055555555556in" height="4.559027777777778in"}
>
> Figure 178 Data Backup Test

## Network Penetration Test

In order to prevent the test from negatively affecting the server, we set up an identical test environment.

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image174.png){width="5.768055555555556in" height="4.068260061242345in"}

Figure 179 Network Penetration Test

### Social Engineering

-   Methodology

> For the testing of social engineering attacks, we can use the Kali Penetration test Tool -SET. Use SET to create a website similar to the Google login page and publish the website to the intranet for testing. This test can feedback employees\' awareness of social engineering attacks.

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image175.png){width="5.768055555555556in" height="3.8493055555555555in"}
>
> Figure 180 Social Engineering Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image176.png){width="5.768055555555556in" height="3.85625in"}
>
> Figure 181 Social Engineering Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image177.jpeg){width="5.768055555555556in" height="3.9055555555555554in"}

Figure 182 Social Engineering Test

### Brute Force

-   Methodology

> The tool we use is kali tool -Hydra. Hydra is a very easy-to-use blasting attack. It supports login tests based on account and password for SSH, FTP, and even Cisco.

1.  First, you need to verify the connectivity to the target FTP server.

> 2\. Enter the code in the kali terminal for blasting test

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image178.png){width="5.768055555555556in" height="3.8375in"}
>
> Figure 183 Brute Force Test
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image179.png){width="5.768055555555556in" height="3.9652777777777777in"}
>
> Figure 184 Brute Force Test

### Port scan

-   Methodology

> The tool we use is kali tool -Nmap. Nmap is a very powerful information collection tool, able to scan open ports or services of the target

1.  Enter the code in the kali terminal for blasting test

-   result

> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image180.png){width="5.768055555555556in" height="5.872222222222222in"}
>
> Figure 185 Port scan

## Design adjustment

From the results of penetration testing, the network system needs to be further improved. For example, make some more secure settings on the FTP server and the window internal firewall.

-   Relieve Brute Force attack

> From the results of penetration testing, the network system needs to be further improved. Suck as, make some more secure settings on the FTP server and the window internal firewall.
>
> The Brute Force attack has a great impact on the FTP server, although the success rate of the Brute Force attack depends on the dictionary strength. Therefore, if the Brute Force attack is not restricted, it is only a matter of time before the account or password is cracked.
>
> The FTP server provides the Logon Attempt Restrictions server, which can reduce the possibility of Brute Force attack success by setting the maximum number of failed login attempts.
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image181.png){width="5.768055555555556in" height="3.6868055555555554in"}
>
> Figure 186 FTP Server Adjustment
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image182.png){width="5.768055555555556in" height="5.334722222222222in"}

Figure 187 FTP Server Adjustment

-   Filter unnecessary port traffic

> Unnecessary open ports may also be used by hackers. According to the results of Nmap scanning, a port service such as http is relatively easy to be used by hackers. For the FTP server, only the FTP port needs to be opened.
>
> Therefore, we can create a New Rule in Windows Firewall with Advanced securiy, and then add the traffic of the port that needs to be filtered out.
>
> After setting the server, its port will still be scanned by Nmap, but any filtered port traffic will be discarded, so it will not be used by hackers.
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image183.png){width="5.768055555555556in" height="4.648611111111111in"}
>
> Figure 188 Filter unnecessary port traffic
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image184.png){width="5.768055555555556in" height="3.9972222222222222in"}
>
> Figure 189 Filter unnecessary port traffic
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image185.png){width="5.768055555555556in" height="3.9972222222222222in"}
>
> Figure 190 Filter unnecessary port traffic
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image186.png){width="5.768055555555556in" height="3.975in"}
>
> Figure 191 Filter unnecessary port traffic
>
> ![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image187.png){width="5.768055555555556in" height="3.963888888888889in"}
>
> Figure 192 Filter unnecessary port traffic

# Reflection

The entire project is very challenging for me, almost all the knowledge required is almost new to the future.

-   What went well

> Moving the project to GNS3 is not very easy, but we also have a better time schedule, allowing us to freely choose the time to do the project. This is a good guarantee for the quality of our project.It didn\'t take a lot of time to build the server, and the server was built very smoothly. Although it is almost brand new knowledge for me, you can find a lot of related building logs from the Internet.

-   What went wrong

> When the project was switched from physical device operation to use GNS3 simulation, the whole project also added a little difficulty. Of course most of the reason is because I don't know enough about GNS3. Although I have done some GNS3-based projects myself, Some settings are still unfamiliar. This has led to problems such as VMnet allocation problems.

-   Different considerations

> I have made a lot of considerations on the security of the network. For example, when considering the Shared folder, I prefer to use an FTP server because it is more secure than setting up a shared file directly in Windows. FTP has a more convenient authorization method, and FTP can Provide an authentication and authorization service, so it is more secure.
>
> The second is network maintenance considerations, considering that the number of users is not large, so no redundancy is considered when designing the network topology. And I want a simple network topology map, so that it is easier to maintain, and once a failure occurs, it can be resolved quickly.

-   Problems encountered and solutions

> At the beginning of GNS3, virtual machines often reported errors. This causes many virtual machines to fail to start automatically in GNS3. If you perform manual other operations, the virtual machine cannot access the Internet.
>
> Most of the errors can be solved by reporting errors. I checked the VMnet according to the error prompt and finally found that the problem was caused by a conflict in the Vmnet . If two virtual machines occupy the same Vmnet at the same time, it will cause the virtual machine to fail to start, and at the same time, manual startup will cause network conflicts. Therefore, I assigned the Vmnet to solve the problem.
>
> GNS3\'s device image also has support problems, and some versions do not support certain functions well. For example, the router version I originally used was 7200. When I use NAT, I find that NAT does not work properly, resulting in virtual access to the network. I always think that there is a problem with the setting of the ASA firewall.
>
> I was almost troubled by this problem for a month, and finally, when rebuilding the topology map, I found that it may be a router version problem. It causes NAT to not work perfectly. So the 7200 version of the router was replaced by the 3200 version. NAT works fine.

-   How did you use of technologies change over time

> I changed the use of technologies in most cases because I learned a new knowledge point and found it to help my project.
>
> When designing the entire network topology, the ASA firewall was adopted as the most important network device. However, the ASA firewall is new knowledge for me. Due to the slow progress of my network security course, I must self-learn the firewall configuration to complete my project before learning the ASA firewall.
>
> However, due to the self-learning configuration of the ASA, it is not possible to fully learn the wider use of the ASA. Due to the lack of understanding of the ASA firewall, during the design of the network, no more perfect security solutions were considered, such as DMZ technologies in ASA.
>
> Unlike my initial design topology, the final network topology diagram FTP server is separate from the internal network. After learning the DMZ technology, I imhttps://github.com/AliChenggggg/blog/tree/main/images/Project%20Reporttely modified the project.

# Conclusions

The network designed for Optimus Consultants will tend to a streamlined structure. The company does not have many employees and considers maintainability, cost, and safety. This structure is more suitable for Optimus Consultants.

When designing the server, there are many options to choose from. After collecting some data, I decided to use windows 2012 as the server and chose Active Directory as the core server. Windows because many servers are connected, such as the Active Directory server, once the Active Directory is set up, almost everything else depends on the Active Directory server for work.

ASA firewall also plays a very important role in the project. Some services such as AAA server, site to site Virtual Private Network, Remote Virtual Private Network, and URL filtering are all designed based on ASA firewall.

Considering that there have been data loss incidents in the company, I particularly focused on the data section. First, I set up security, established a DMZ zone on the ASA, and protected the FTP server and internal network. Secondly, in data backup, Shadow copy and software backup are used at the same time.

Penetration testing also gives some ways to make the network more secure. Phishing is a common social engineering attack. Informing employees of this attack method can well avoid such attacks. Secondly, blasting attacks, blasting attacks are almost inevitable for the server, but FTP provides login protection, which can greatly reduce the success rate of blasting attacks. Finally, port scanning found many unused ports, which may give hackers more opportunities to invade. Therefore, closing these ports can better maintain the security of the server.

As far as the entire project is concerned, more bugs come from GNS3 itself, but GNS3-based projects also provide great flexibility in time. We can configure and troubleshoot projects almost anywhere, anytime. In addition, in this project, I also learned a lot of new knowledge and exercised my self-learning ability.

# Appendix: Time management

## Time log

![](https://github.com/AliChenggggg/blog/tree/main/images/Project%20Report/image188.jpeg){width="6.058333333333334in" height="1.0763888888888888in"}

Figure 193 Final Time log

The whole project started at 18 February 2020.For the first task, I spent two weeks to finished initial project proposal.

On 5 March 2020, I started the technical design document, it finished at 16 March 2020.

Then, the implementation of prototype start 17 March 2020 and finish at 31 April 2020.

After implementation, I started work on Practical demonstration.it spent four days for preparation.

On 24 April 2020, I started to write my project report.

Finally, on 11 June 2020, I will start working on presentation preparation.

## Compare to my initial time management plan

Judging from the steps. There are no special changes in the steps of the entire project. The only difference is that I started writing the report in advance, because I realized that there are a lot of contents in the report that need to explain the steps. So at the end of the implementation of prototype, the project started to collect step information and used this information in the report.

In terms of time, the progress of the project has been delayed. It occurred when the implementation of the prototype task was completed. Due to many problems, it was not particularly smooth, so I spent a longer time to complete this task.

# References

Bradley M (2020). What Is a Virtual LAN (VLAN)? Retrieved from <https://www.lifewire.com/virtual-local-area-network-817357>

Cisco (n.d.). What is a VPN? - Virtual Private Network. Retrieved from <https://www.cisco.com/c/en/us/products/security/vpn-endpoint-security-clients/what-is-vpn.html>

[Esther,C](https://www.workamajig.com/blog/author/esther-cohen) (2019). The Definitive Guide to Project Management Methodologies. Retrieved from <https://www.workamajig.com/blog/project-management-methodologies>

F5 GLOSSARY (n.d.) What is SSL VPN? Retrieved from <https://www.f5.com/services/resources/glossary/ssl-vpn>

Microsoft (n.d). Get started with MDT .Retrieved from <https://docs.microsoft.com/en-us/windows/deployment/deploy-windows-mdt/get-started-with-the-microsoft-deployment-toolkit>

Rackspace Support (2016). Install Active Directory Domain Services on Windows Server 2008 R2 Enterprise 64-bit. Rackspace. Rackspace US, Inc. Retrieved from <https://support.rackspace.com/how-to/installing-active-directory-on-windows-server-2012/>

Vharseko (2020). OpenDJ. Retrieved from <https://www.openidentityplatform.org/opendj>

Wikipedia (2020). Zentyal. Retrieved from <https://en.wikipedia.org/wiki/Zentyal>
