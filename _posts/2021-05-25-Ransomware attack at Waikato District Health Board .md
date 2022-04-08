---
layout: post
title: Ransomware attack at Waikato District Health Board
date: 2021-05-25
Author: Ali
categories: 
tags: [cyber security]
comments: true
---



**Event**: On May 19, 2021, hospital computer systems and phone lines operated by the Waikato District Health Board (DHB) in New Zealand were attacked by **ransomware**.

**Result**: Computer systems and telephone lines collapsed. Part of the data was stolen and posted on the dark web.



# About Conti:

1\. This virus was first discovered in 2020

2\. Adopt the dual extortion strategy of \"threat exposing corporate data + extorting encrypted data\".

3\. Mainly spread through phishing activities or system Vulnerability or brute force attacks.

4\. Like other ransomware, it has the function of encrypting files and able to spread on the subnet through port 445.

5\. Analyze the samples, Conti is loaded with the TrickBot Trojan for spreading.

If you want to learn more about Conti, I recommend you check: https://labs.vipre.com/how-conti-ransomware-works-and-our-analysis/



# Emergency Response

Actually，the solution for ransomware and worms are similar.



### Step 1 	Control virus spread

Our experience at wannacry 2017 taught us that unplugging the network cable is the fastest way.

The best way is :

1. cut off the data exchange between network devices (routers or switches) to form several network areas.
2. Unplug the network cable of the user\'s computer.

After the network is partitioned, recovery each network area one by one.



### Step 2 	Start Safe mode to repair

If the virus has never been found before, you can start  system restore directly. After restoration, use data recovery for rescue. There is no point in booting into Safe Mode to fix it.

If the virus is known, you can choose to backup encrypted files first, if you full of wish. and Start the safe mode to delete the virus directly.

the files of Conti are composed of **\*,doc.CONTI**. Find these files and delete them. This requires you to troubleshoot all devices in the network.



### Step 3 	Data Recovery

If you have some advanced backup methods, such as backing up your data on the cloud, you can now use it to restore your data.

If your backup is also encrypted, you can perform some data recovery operations and use some software to retrieve lost documents.



### Step 4 	 Security reinforcement

After the recovery is complete you need to consider a few questions:

1\. Do the login passwords of the system and employees need to be changed? 

2\. Do some high-risk ports need to be closed?

3\. Do you need new Intrusion Detection System (IDS) ?

4\. Do the system firewall rules need to be updated?

5\. Did backup play a good role in recovery in this attack?

6\. Do employees need further cybersecurity training?

7\. If you have antivirus software, does it work well?





#### ***This is Ali*** 

#### ***Please feel free to contact me if you have any further information or you find some mistakes in my article.***





### Reference

1. RNZ (2021). *Cyber attack at Waikato hospitals: Patients anxiously wait for updates*. https://www.rnz.co.nz/news/national/442850/cyber-attack-at-waikato-hospitals-patients-anxiously-wait-for-updates

2. VIPRE Labs (2021).*How Conti Ransomware Works and Our Analysis.* https://labs.vipre.com/how-conti-ransomware-works-and-our-analysis/





