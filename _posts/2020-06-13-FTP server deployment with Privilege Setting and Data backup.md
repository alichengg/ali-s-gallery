---
layout: post
title: FTP server deployment
date: 2020-06-13
Author: Ali
categories: 
tags: [Project]
comments: true
---



FTP server +  FTP Privilege Setting + Data backup

FTP is a very easy-to-use file sharing system. To install FTP, you first need to install Web server Role (IIS), then select FTP server in Role services.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image063.png){width="5.768055555555556in" height="5.501388888888889in"}

Figure 64 FTP Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image064.png){width="5.768055555555556in" height="5.481944444444444in"}

Figure 65 FTP Installation

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image065.png){width="5.768055555555556in" height="4.0625in"}

Figure 66 FTP Installation

-   After the Web server Role (IIS) is created, a new FTP server needs to be created in the internet information services manager.

-   Before creating FTP, you need to create the corresponding certificate, next to start creating the FTP site, you need to give the FTP site name and Content directory, then select the mapped IP address, port, and SSL certificate. Finally, choose Authentication and Authorization information.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image066.png){width="5.768055555555556in" height="2.957638888888889in"}

Figure 67 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image067.png){width="5.768055555555556in" height="2.9555555555555557in"}

Figure 68 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image068.png){width="5.768055555555556in" height="3.2104166666666667in"}

Figure 69 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image069.png){width="5.768055555555556in" height="5.061805555555556in"}

Figure 70 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image070.png){width="5.768055555555556in" height="2.948611111111111in"}

Figure 71 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image071.png){width="5.768055555555556in" height="4.54375in"}

Figure 72 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image072.png){width="5.768055555555556in" height="5.080555555555556in"}

Figure 73 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image073.png){width="5.768055555555556in" height="5.1090277777777775in"}

Figure 74 FTP Configuration

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image074.png){width="5.768055555555556in" height="5.0784722222222225in"}

Figure 75 FTP Configuration

-   After the FTP is created, you need to set the privilege. According to the requirements, three folders need to be created, Department, Project, and user.

-   "Department" should only allow relevant departments to access relevant folders, so each file needs to be authorized by a separate department. For example, the Accounting subfolder needs to be given read permission to group Accounting

-   "Pproject" can only be accessed by the project manager and related employees. Of course, Accounting needs to have the right to read. Therefore, you need to create a separate subfolder for each Project manager and give the permissions corresponding to each project. For example, under the Ajay Nash file, you need to allow Ajay Nash to read and write permissions, and give the group Accounting permission to read.

-   "User" folder can only allow employees to access their own folders. However, IT administrators have the authority to modify all folders. Therefore, each User needs to be individually authorized. For example, the Ajay Nash subfolder needs to authorize Ajay Nash read and write permissions, and give the group IT Administrator read and write permissions.

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image075.png){width="5.768055555555556in" height="3.9923611111111112in"}

Figure 76 FTP Privilege setting

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image076.png){width="5.768055555555556in" height="4.009027777777778in"}

Figure 77 FTP Privilege setting



# Testing

## File System Privilege Test

-   Methodology

The FTP server is an open server of the entire company network, and its security is very important. FTP provides a very convenient access authorization management interface, and administrators can easily perform authorization management. Therefore, the verification methods are:

1\. All sites can access the FTP server including remote access

2\. The user can only access the folder where the department is located and personal folders. Cannot access other user or department folders.

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image141.png){width="5.768055555555556in" height="4.533333333333333in"}

Figure 142 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image142.png){width="5.768055555555556in" height="4.685416666666667in"}

Figure 143 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image143.png){width="5.768055555555556in" height="4.49375in"}

Figure 144 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image144.png){width="5.768055555555556in" height="4.560416666666667in"}

Figure 145 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image145.png){width="5.768055555555556in" height="4.501388888888889in"}

Figure 146 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image146.png){width="5.768055555555556in" height="4.503472222222222in"}

Figure 147 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image147.png){width="5.768055555555556in" height="4.500694444444444in"}

Figure 148 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image148.png){width="5.768055555555556in" height="4.561111111111111in"}

Figure 149 File System Privilege Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image149.png){width="5.768055555555556in" height="4.533333333333333in"}

Figure 150 File System Privilege Test



### Data Backup

-   Methodology

The software-based data backup needs to be restored and tested. If the file is deleted after it has been backed up, and the backup service needs to be able to restore the files again.

1.  First, we need to create a test.txt file as a test file

2.  Then perform the backup server

3.  Next delete the test.txt file

4.  Finally, use the software to restore the file

-   result

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image167.png){width="5.768055555555556in" height="4.552777777777778in"}

Figure 172 Data Backup Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image168.png){width="5.768055555555556in" height="4.520138888888889in"}

Figure 173 Data Backup Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image169.png){width="5.768055555555556in" height="4.542361111111111in"}

Figure 174 Data Backup Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image170.png){width="5.768055555555556in" height="2.1104166666666666in"}

Figure 175 Data Backup Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image171.png){width="5.768055555555556in" height="3.4118055555555555in"}

Figure 176 Data Backup Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image172.png){width="5.768055555555556in" height="4.506944444444445in"}

Figure 177 Data Backup Test

![img](https://raw.githubusercontent.com/AliChenggggg/blog/main/images/2020-06-13-Project/image173.png){width="5.768055555555556in" height="4.559027777777778in"}

Figure 178 Data Backup Test





# References

Bradley M (2020). What Is a Virtual LAN (VLAN)? Retrieved from <https://www.lifewire.com/virtual-local-area-network-817357>

Cisco (n.d.). What is a VPN? - Virtual Private Network. Retrieved from <https://www.cisco.com/c/en/us/products/security/vpn-endpoint-security-clients/what-is-vpn.html>

[Esther,C](https://www.workamajig.com/blog/author/esther-cohen) (2019). The Definitive Guide to Project Management Methodologies. Retrieved from <https://www.workamajig.com/blog/project-management-methodologies>

F5 GLOSSARY (n.d.) What is SSL VPN? Retrieved from <https://www.f5.com/services/resources/glossary/ssl-vpn>

Microsoft (n.d). Get started with MDT .Retrieved from <https://docs.microsoft.com/en-us/windows/deployment/deploy-windows-mdt/get-started-with-the-microsoft-deployment-toolkit>

Rackspace Support (2016). Install Active Directory Domain Services on Windows Server 2008 R2 Enterprise 64-bit. Rackspace. Rackspace US, Inc. Retrieved from <https://support.rackspace.com/how-to/installing-active-directory-on-windows-server-2012/>

Vharseko (2020). OpenDJ. Retrieved from <https://www.openidentityplatform.org/opendj>

Wikipedia (2020). Zentyal. Retrieved from <https://en.wikipedia.org/wiki/Zentyal>
