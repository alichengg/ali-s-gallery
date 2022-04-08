---
layout: post
title: Active Directory Server Deployment
date: 2020-06-13
Author: Ali
categories: 
tags: [Project]
comments: true
---



Active Directory + DHCP + DNS + Windows Deployment Services+Group Policy



Active Directory is a relatively easy-to-use Directory Services. It will automatically generate a Domain Controller after the AD server is successfully installed. The installation of AD server is very simple, only need to choose to install Active Directory Domain Services in Server Manager.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image002.png){width="5.768055555555556in" height="4.057638888888889in"}

Figure 2 Active Directory Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image003.png){width="5.768055555555556in" height="4.020833333333333in"}

Figure 3 Active Directory Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image004.png){width="5.768055555555556in" height="4.0375in"}

Figure 4 Active Directory Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image005.png){width="5.768055555555556in" height="4.051388888888889in"}

Figure 5 Active Directory Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image006.png){width="5.768055555555556in" height="4.013888888888889in"}

Figure 6 Active Directory Installation

-   After the Active Directory installation is successful, you need to configure it, including the generated Forest settings and Root domain name.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image007.png){width="5.768055555555556in" height="4.034027777777778in"}

Figure 7 Active Directory Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image008.png){width="5.768055555555556in" height="3.890277777777778in"}

Figure 8 Active Directory Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image009.png){width="5.768055555555556in" height="4.2131944444444445in"}

Figure 9 Active Directory Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image010.png){width="5.768055555555556in" height="4.236805555555556in"}

Figure 10 Active Directory Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image011.png){width="5.768055555555556in" height="4.201388888888889in"}

Figure 11 Active Directory Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image012.png){width="5.768055555555556in" height="4.205555555555556in"}

Figure 12 Active Directory Configuration

-   After the Active Directory configuration is complete, you can start adding domain users and creating management groups, and then classify users by department. Users can be better managed after being classified, including authorization management, login management etc

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image013.png){width="5.768055555555556in" height="3.6902777777777778in"}

Figure 13 Active Directory user and group setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image014.png){width="5.768055555555556in" height="3.0506944444444444in"}

Figure 14 Active Directory user setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image015.png){width="5.768055555555556in" height="3.422222222222222in"}

Figure 15 Active Directory user setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image016.png){width="5.768055555555556in" height="3.44375in"}

Figure 16 Active Directory user setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image017.png){width="5.768055555555556in" height="4.538194444444445in"}

Figure 17 Active Directory group setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image018.png){width="5.768055555555556in" height="4.5472222222222225in"}

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image019.png){width="5.768055555555556in" height="3.6465277777777776in"}

###  DHCP 

-   The DHCP server can automatically provide IP address services for clients. Installing DHCP requires selecting and installing the DHCP server in server management.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image020.png){width="5.768055555555556in" height="4.077083333333333in"}

Figure 19 DHCP Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image003.png){width="5.768055555555556in" height="4.020833333333333in"}

Figure 20 DHCP Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image004.png){width="5.768055555555556in" height="4.0375in"}

Figure 21 DHCP Installation

NNN![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image021.png){width="5.768055555555556in" height="4.086805555555555in"}

Figure 22 DHCP Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image022.png){width="5.812696850393701in" height="5.528570647419072in"}

Figure 23 DHCP Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image023.png){width="5.768055555555556in" height="4.228472222222222in"}

Figure 24 DHCP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image024.png){width="5.768055555555556in" height="4.198611111111111in"}

Figure 25 DHCP Configuration

-   After the DHCP installation is complete, you need to configure it. The first step is to create a new scope, set the address range that the server can distribute, the address range that cannot be distributed, and the default gateway.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image025.png){width="5.768055555555556in" height="3.3645833333333335in"}

Figure 26 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image026.png){width="5.768055555555556in" height="3.5902777777777777in"}

Figure 27 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image027.png){width="5.768055555555556in" height="4.270833333333333in"}

Figure 28 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image028.png){width="5.768055555555556in" height="4.196527777777778in"}

Figure 29 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image029.png){width="5.768055555555556in" height="4.070138888888889in"}

Figure 30 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image030.png){width="5.768055555555556in" height="4.156944444444444in"}

Figure 31 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image031.png){width="5.768055555555556in" height="4.355555555555555in"}

Figure 32 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image032.png){width="5.768055555555556in" height="4.352777777777778in"}

Figure 33 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image033.png){width="5.768055555555556in" height="4.315277777777778in"}

Figure 34 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image034.png){width="5.768055555555556in" height="4.293055555555555in"}

Figure 35 DHCP Scope setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image035.png){width="5.768055555555556in" height="4.352777777777778in"}

Figure 36 DHCP Scope setting

###  DNS

-   The main function of DNS is to perform IP address resolution. To install dns, you need to select and install a DNS server from service management.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image036.png){width="5.768055555555556in" height="5.45625in"}

Figure 37 DNS Installation

-   After the installation is complete, basic configuration of the DNS server is required, including the name given to the Zone, and DNS server Forwarders. Forwarders are used to send resolution requests to other DNS servers when the local DNS server cannot resolve the address.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image037.png){width="5.768055555555556in" height="2.9625in"}

Figure 38 DNS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image038.png){width="5.768055555555556in" height="3.966666666666667in"}

Figure 39 DNS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image039.png){width="5.768055555555556in" height="4.747222222222222in"}

Figure 40 DNS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image040.png){width="5.768055555555556in" height="4.750694444444444in"}

Figure 41 DNS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image041.png){width="5.768055555555556in" height="4.715277777777778in"}

Figure 42 DNS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image042.png){width="5.768055555555556in" height="4.725694444444445in"}

Figure 43 DNS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image043.png){width="5.768055555555556in" height="4.710416666666666in"}

Figure 44 DNS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image044.png){width="5.768055555555556in" height="2.901388888888889in"}

Figure 45 DNS Configuration

-   After the basic configuration of the DNS server is completed, a New Zone needs to be created. This Zone is to add the address to be resolved or forward.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image045.png){width="5.768055555555556in" height="3.716666666666667in"}

Figure 46 DNS Function setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image046.png){width="5.768055555555556in" height="4.745138888888889in"}

Figure 47 DNS Function setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image047.png){width="5.768055555555556in" height="4.741666666666666in"}

Figure 48 DNS Function setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image048.png){width="5.768055555555556in" height="3.7444444444444445in"}

Figure 49 DNS Function setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image049.png){width="5.768055555555556in" height="4.764583333333333in"}

Figure 50 DNS Function setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image050.png){width="5.768055555555556in" height="4.73125in"}

Figure 51 DNS Function setting

###  Deployment/Imaging Services

-   The WDS server can provide a window system installation channel through the network. To install WDS, you need to choose to install Windows deployment services in Service management, and check Deployment Server and transport server in Role services.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image051.png){width="5.768055555555556in" height="4.096527777777778in"}

Figure 52 WDS Server Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image052.png){width="5.768055555555556in" height="5.461805555555555in"}

Figure 53 WDS Server Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image053.png){width="5.768055555555556in" height="5.468055555555556in"}

Figure 54 WDS Server Installation

-   After the WDS server is installed, you need to create a group, then add the windows install image and boot image.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image054.png){width="5.768055555555556in" height="3.326388888888889in"}

Figure 55 WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image055.png){width="5.768055555555556in" height="5.2125in"}

Figure 56 WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image056.png){width="5.768055555555556in" height="3.290277777777778in"}

Figure 57 WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image057.png){width="5.768055555555556in" height="3.317361111111111in"}

Figure 58 WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image058.png){width="5.768055555555556in" height="4.148611111111111in"}

Figure 59 WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image059.png){width="5.768055555555556in" height="4.151388888888889in"}

Figure 60 WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image060.png){width="5.768055555555556in" height="4.50625in"}

Figure 61WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image061.png){width="5.768055555555556in" height="4.502083333333333in"}

Figure 62 WDS Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image062.png){width="5.768055555555556in" height="4.507638888888889in"}

Figure 63 WDS Configuration



### Group Policy

-   Group policy can be used to publish some software that companies need. To set up a software release policy, you need to first create a shared file and put the software in the shared file.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image100.png){width="5.417135826771654in" height="5.3838003062117235in"}

Figure 101 Group Policy Setting

-   Group policy can be used to publish some software that companies need. To set up a software release policy, you need to first create a shared file and put the software in the shared file.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image101.png){width="5.768055555555556in" height="3.736111111111111in"}

Figure 102 Group Policy Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image102.png){width="5.768055555555556in" height="3.7708333333333335in"}

Figure 103 Group Policy Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image103.png){width="5.768055555555556in" height="4.256944444444445in"}

Figure 104 Group Policy Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image104.png){width="5.768055555555556in" height="4.166666666666667in"}

Figure 105 Group Policy Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image105.png){width="5.768055555555556in" height="4.697916666666667in"}

Figure 106 Group Policy Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image106.png){width="5.768055555555556in" height="4.129166666666666in"}

Figure 107 Group Policy Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image107.png){width="5.768055555555556in" height="3.640277777777778in"}

Figure 108 Group Policy Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image108.png){width="4.58373031496063in" height="4.900424321959755in"}

Figure 109 Group Policy Setting

### 

































# Testing

### Directory Services and Domain Controller

-   Methodology

Active Directory Domain Services is a combination of Directoty services and Domain controller. We can test whether the client can join the company\'s domain to test whether the server works normally. Active Directory can add domain users, so users should be able to use the users stored in Active Directory to Log in to the client. So the test can be divided into 2 parts:

1.  Test whether the client can join the domain

2.  Test whether the user created in AD server can log in to the client

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image127.png)

Figure 128 Active Directory Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image128.png){width="5.768055555555556in" height="4.5569444444444445in"}

Figure 129 Active Directory Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image129.png){width="5.768055555555556in" height="4.529166666666667in"}

Figure 130 Active Directory Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image130.png){width="5.768055555555556in" height="4.550694444444445in"}

Figure 131 Active Directory Test

### DHCP

-   Methodology

The DHCP server should be able to automatically give the client an ip address. DHCP requires the client to be set to DHCP mode, so you need to verify that DHCP requires:

1.  Test whether the client can obtain the correct IP address in the automatic address acquisition mode

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image131.png){width="5.768055555555556in" height="3.988888888888889in"}

Figure 132 DHCP Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image132.png){width="5.768055555555556in" height="4.554861111111111in"}

Figure 133 DHCP Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image133.png){width="5.768055555555556in" height="4.579166666666667in"}

Figure 134 DHCP Test

### DNS

Methodology

DNS can provide an address resolution service. In this project, DNS is set up to resolve local websites. It should need to have the ability to resolve IP addresses by domain name, and it can send requests to other DNS servers to resolve more Domain name or IP address. So verify DNS requirements:

1\. Use the "nslookup" command to test the area resolution service

2\. Test whether the client can browse the web normally

3\. Test whether the client can access the local website through the domain name.

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image134.png){width="5.768055555555556in" height="3.3256944444444443in"}

Figure 135 DNS Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image135.png){width="5.768055555555556in" height="4.313194444444444in"}

Figure 136 DNS Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image136.png){width="5.768055555555556in" height="4.543055555555555in"}

Figure 137 DNS Test

### Deployment/Imaging service

-   Methodology

Windows Deployment Services is a network-based installation server for window systems. For clients joining the domain, you need to be able to select the network through the bios interface to install the window system：

1\. Test whether the client can install windows from the network option in the BIOS.

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image137.png){width="5.768055555555556in" height="4.050694444444445in"}

Figure 138 WDS Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image138.png){width="5.768055555555556in" height="3.829861111111111in"}

Figure 139 WDS Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image139.png){width="5.768055555555556in" height="4.5375in"}

Figure 140 WDS Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image140.png){width="5.768055555555556in" height="4.388888888888889in"}

Figure 141 WDS Test





### Group Policy

-   Methodology

Group Policy is used to publish Auto CAD software on the internal network to verify the success of the Group Policy. You need to check whether the software installation program from the server can be found in programs and Features in the intranet client.

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image163.png){width="5.768055555555556in" height="4.247222222222222in"}

Figure 168 Group Policy Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image164.png){width="5.768055555555556in" height="4.5881944444444445in"}

Figure 169 Group Policy Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image165.png){width="5.768055555555556in" height="4.516666666666667in"}

Figure 170 Group Policy Test
