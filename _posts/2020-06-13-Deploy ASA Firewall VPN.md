---
layout: post
title: Deploy ASA Firewall VPN
date: 2020-06-13
Author: Ali
categories: 
tags: [Project]
comments: true
---

Site to site Virtual Private Network + Remote Virtual Private Network Configuration + URL filtering



### Site to site Virtual Private Network

-   The most convenient way to set up site to site virtual private network on the ASA firewall is through ASDM.

-   Before setting up ASDM, you need to apply an http server on the ASA firewall and allow specific IP addresses to access it.

1.  Ciscoasa (config)# http server enable

2.  Ciscoasa (config)# http 172.16.1.0 255.255.255.0 inside

    -   After the setting is completed, you can download and install ASDM by accessing the asa firewall address through http (ASDM requires java support, so you need to ensure that the system has Java programs when installing ASDM)

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image077.png){width="5.768055555555556in" height="3.56875in"}

Figure 78 ASDM Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image078.png){width="5.768055555555556in" height="4.092361111111111in"}

Figure 79 ASDM Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image079.png){width="5.33379593175853in" height="4.067018810148731in"}

Figure 80 ASDM Installation

-   After the ASDM installation is complete, you can access the ASA firewall through ASDM, and you can use the graphical interface to set up the entire ASA firewall in ASDM.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image080.png){width="5.895472440944882in" height="2.8036034558180227in"}

Figure 81 Site to site Virtual Private Network Configuration

-   To create a site to site VPN, we first need to add the range of target IP addresses that can be accessed in the Access Rule, so we need to add the internal IP addresses of all sites.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image081.png){width="5.768055555555556in" height="3.591666666666667in"}

Figure 82 Site to site Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image082.png){width="5.2004505686789155in" height="2.683566272965879in"}

Figure 83 Site to site Virtual Private Network Configuration

-   After the Access Rule is added, start to create site to site VPN

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image083.png){width="5.768055555555556in" height="1.6847222222222222in"}

Figure 84 Site to site Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image084.png){width="5.768055555555556in" height="3.157638888888889in"}

Figure 85 Site to site Virtual Private Network Configuration

-   Site to site vpn needs to fill in the peer ip address, which is the external network address of another site. At the same time, you need to fill in the intranet address range of another site.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image085.png){width="5.768055555555556in" height="3.171527777777778in"}

Figure 86 Site to site Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image086.png){width="5.768055555555556in" height="3.1930555555555555in"}

Figure 87 Site to site Virtual Private Network Configuration

-   Add pre-shared key to ensure the security of site to site vpn connection

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image087.png){width="5.768055555555556in" height="3.152083333333333in"}

Figure 88 Site to site Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image088.png){width="5.768055555555556in" height="3.1368055555555556in"}

Figure 89 Site to site Virtual Private Network Configuration

-   Set up other sites in the same way

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image089.png){width="5.768055555555556in" height="3.5520833333333335in"}

Figure 90 Site to site Virtual Private Network Configuration

### Remote Virtual Private Network and Authentication Service

-   Remote VPN needs to set up anyconnect VPN Wizard in ASDM.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image090.png){width="5.768055555555556in" height="2.512153324584427in"}

Figure 91 Remote Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image091.png){width="5.768055555555556in" height="3.5854166666666667in"}

Figure 92 Remote Virtual Private Network Configuration

-   Set profile name and VPN access interface, and upload client image, this image will be used as a vpn client for remote workers.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image092.png){width="5.768055555555556in" height="3.5590277777777777in"}

Figure 93 Remote Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image093.png){width="5.768055555555556in" height="3.546527777777778in"}

Figure 94 Remote Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image094.png){width="5.768055555555556in" height="3.573611111111111in"}

Figure 95 Remote Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image095.png){width="5.768055555555556in" height="3.515972222222222in"}

Figure 96 Remote Virtual Private Network Configuration

-   After that, you need to add users who can access the intranet. By default, the AAA server will be used. Then, you need to add an address range that can use VPN

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image096.png){width="5.768055555555556in" height="3.501388888888889in"}

Figure 97 Remote Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image097.png){width="5.768055555555556in" height="3.522222222222222in"}

Figure 98 Remote Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image098.png){width="5.768055555555556in" height="3.5229166666666667in"}

Figure 99 Remote Virtual Private Network Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image099.png){width="5.768055555555556in" height="3.5076388888888888in"}

Figure 100 Remote Virtual Private Network Configuration



### URL filtering

-   ASA firewall also supports URL filtering, first we need to find a URL filtering target.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image109.png){width="5.768055555555556in" height="3.0131944444444443in"}

Figure 110 URL filtering Setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image110.png){width="5.768055555555556in" height="4.602083333333334in"}

Figure 111 URL filtering Setting

-   After determining the IP address to be filtered, add the URL filtering server in the ASA. After the addition is complete, you need to add a Web page filtering based on Https in Filter Rules.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image111.png){width="5.768055555555556in" height="4.790277777777778in"}

Figure 112 URL filtering Setting































# Testing

### Site to Site Virtual Private Network

-   Methodology

The purpose of site to site VPN is to allow other branches to access the FTP server. Therefore testing Site to site VPN requires:

1\. All branches internal clients can access the FTP server

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image150.png){width="5.768055555555556in" height="4.570833333333334in"}

Figure 151 Site to site Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image142.png){width="5.768055555555556in" height="4.685416666666667in"}

Figure 152 Site to site Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image151.png){width="5.768055555555556in" height="4.557638888888889in"}

Figure 153 Site to site Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image152.png){width="5.768055555555556in" height="4.555555555555555in"}

Figure 154 Site to site Virtual Private Network Test

### Remote Virtual Private Network

-   Methodology

Remote Virtual Private Network provides employees with a channel to remotely connect to the company\'s internal server. To verify Remote VPN, try to use the Cisco AnyConnect Secure Mobility Client in the remote client to connect to the company\'s internal network. Using VPN requires AAA server authentication. Therefore testing remote VPN requires:

1\. Remote users need to access the public network address of the ASA firewall to log in and install the VPN client.

2\. The remote client needs to be able to access the FTP server through a VPN connection.

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image153.png){width="5.768055555555556in" height="3.953472222222222in"}

Figure 155 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image154.png){width="5.768055555555556in" height="3.9125in"}

Figure 156 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image155.png){width="5.768055555555556in" height="3.8604166666666666in"}

Figure 157 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image156.png){width="5.150446194225721in" height="4.075353237095363in"}

Figure 158 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image157.png){width="5.125444006999125in" height="2.6252274715660544in"}

Figure 159 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image158.png) 

Figure 160 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image159.png){width="5.768055555555556in" height="4.586111111111111in"}

Figure 161 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image160.png){width="5.768055555555556in" height="4.595138888888889in"}

Figure 162 Remote Virtual Private Network Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image141.png){width="5.768055555555556in" height="4.533333333333333in"}

Figure 163 Remote Virtual Private Network Test

### Authentication service

-   Methodology

AAA service is installed on the ASA firewall and used to authenticate remote access users. There are two ways to authenticate AAA server:

1\. Test whether users can connect to the intranet through VPN

2\. Check whether the AAA server has user access records

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image161.png){width="5.768055555555556in" height="5.399305555555555in"}

Figure 164 Authentication service Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image157.png){width="5.125444006999125in" height="2.6252274715660544in"}

Figure 165 Authentication service Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image159.png){width="5.768055555555556in" height="4.586111111111111in"}

> Figure 166 Authentication service Test
>

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image162.png){width="5.768055555555556in" height="5.317361111111111in"}

Figure 167 Authentication service Test



### URL filtering

-   Methodology

For URL filtering, just open the web page to see if the filtered IP address can be displayed.

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image166.png){width="5.768055555555556in" height="4.570833333333334in"}

Figure 171 URL filtering Test

# References

Bradley M (2020). What Is a Virtual LAN (VLAN)? Retrieved from <https://www.lifewire.com/virtual-local-area-network-817357>

Cisco (n.d.). What is a VPN? - Virtual Private Network. Retrieved from <https://www.cisco.com/c/en/us/products/security/vpn-endpoint-security-clients/what-is-vpn.html>

[Esther,C](https://www.workamajig.com/blog/author/esther-cohen) (2019). The Definitive Guide to Project Management Methodologies. Retrieved from <https://www.workamajig.com/blog/project-management-methodologies>

F5 GLOSSARY (n.d.) What is SSL VPN? Retrieved from <https://www.f5.com/services/resources/glossary/ssl-vpn>

Microsoft (n.d). Get started with MDT .Retrieved from <https://docs.microsoft.com/en-us/windows/deployment/deploy-windows-mdt/get-started-with-the-microsoft-deployment-toolkit>

Rackspace Support (2016). Install Active Directory Domain Services on Windows Server 2008 R2 Enterprise 64-bit. Rackspace. Rackspace US, Inc. Retrieved from <https://support.rackspace.com/how-to/installing-active-directory-on-windows-server-2012/>

Vharseko (2020). OpenDJ. Retrieved from <https://www.openidentityplatform.org/opendj>

Wikipedia (2020). Zentyal. Retrieved from <https://en.wikipedia.org/wiki/Zentyal>
