---
layout: post
title:Bvp47 Top-tier Backdoor
date: 2022-03-07
Author: Ali
categories: This article is only used for cyber security research, please do not use it for improper purposes.
tags: [cyber security]
comments: true
---

# Bvp47 - a Top-tier  API Backdoor 


This cyber attack has been covertly attacking 287 targets in 45 countries for 10 years. And most of the targets are government departments or schools.

After analyzing all attack methods, it is determined that the attack originates from the Equation Group of the NAS.Usually, cyber attacks cannot be targeted because attackers can use proxies or VPNs to jump to other countries or regions to launch obfuscated cyber attacks. But this incident was an exception. In 2016, Equation Group's network attack tool was leaked, and the private key that could start bvp47 was found in the attack tool package.

The attack was named "Operation Telescreen".



### Sequence of events:

In 2013, it was discovered and collected by Pangu Lab. But the investigation was suspended because the private key of the asymmetric encryption could not be cracked.

In 2015, a customer deployed IDS to detect Bvp47 attacks. The attack steps and harm of Bvp47 were confirmed.

In 2016, The Shadow Brokers announced the Equation Group tool, and the asymmetric encryption private key of BVP47 was cracked. The production team of BVP47 has been confirmed.

On February 23, 2022, the complete chain of evidence that the US "top backdoor" attacked 45 countries  was exposed by Pangu Lab.



2013年就已经被盘古实验室发现并取证。但调查因非对称加密私钥无法被破解而暂停。

2015年某客户部署IDS检测到了Bvp47 的攻击行为。Bvp47 的攻击步骤以及危害被确认。

2016年The Shadow Brokers公布了方程式组织的工具，BVP47的非对称加密私钥被破解。BVP47的制作团体被确认。

2022年2月23日，美国“顶级后门”攻击中国等国家和地区的完整证据链条，被盘古实验室首次曝光。



### File structure:

**ELF+Payload**

Bvp47 is a backdoor with a remote console. This backdoor is entirely for **linux**. File  including loader and payload, Loader is mainly used to decrypt and execute payload. From the data unpacked by Pangu Lab, the payload is compressed and encrypted, with a total of **18 fragments**（they have different functions）.

For a detailed introduction to the functions of each component, it is recommended that you read the official documentation:

https://www.pangulab.cn/en/post/the_bvp47_a_top-tier_backdoor_of_us_nsa_equation_group/



Bvp47 是一个带有控制端的后门程序。这个后门完全是针对linux的。文件结构 loader 和 payload，Loader主要用于解密和执行Payload。从盘古实验室解包的数据来看，Payload被压缩和加密，一共18个分片。

具体介绍各个部件的功能,建议您去看官方文档：

https://www.pangulab.cn/files/The_Bvp47_a_top-tier_backdoor_of_us_nsa_equation_group.zh-cn.pdf



### Attack method:

1. The attacker of Bvp47  first sends a **SYN packet** with **payload (136 bytes)** of length to port 1357（may be other port） of the victim host A.
2. The SYN packet connects to port 2468 (may be other port) of the attacker (**reverse connection** and establishes an encrypted channel for information transmission).
3. Open a backdoor **python http server** on the victim host A. Do some enumeration tests to get PowerShell execute permissions.
4. The backdoor web server in the victim host A initiates **data exchange** to other internal servers through the SMB service port.
5. After obtaining the data, victim host A will **synchronize** the data with the attacker (steal the data).



### Technology:

Avoid BPF's censorship rules for SYN packets

Kernel module anti-detection:Bvp47 will modify the first four bytes of the elf file of the kernel module to avoid the memory search elf, and load it through its own lkm loader.

Create encrypted communication links based on asymmetric algorithms RSA and RC-X algorithms

##### Some others that I don't understand. I gave it up.........T T



### Detective and Defense

Because the BVP47 toolkit and attack console have been leaked, it is likely that some random attacks will be triggered in the future.

You can use the following information to detect whether it has compromised your server.

| file name   | initserial or other              |
| ----------- | -------------------------------- |
| Hash（MD5） | 58b6696496450f254b1423ea018716dc |
| size        | 299,148 bytes                    |
| file path   | /usr/bin/modload                 |
| platform    | Linux                            |





### Reference 

Pangu Lab(2022). The Bvp47 - a Top-tier Backdoor of US NSA Equation Group. https://www.pangulab.cn/en/post/the_bvp47_a_top-tier_backdoor_of_us_nsa_equation_group/
