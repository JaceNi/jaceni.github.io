---
layout:     post
title:      How To Automate Linux Operation and Maintenance
subtitle:   From Operation and Maintenance Basics to High-concurrency Architecture for Large Websites
date:       2018-01-04
author:     Yuchen Ni
header-img: https://cdn.pling.com/img/8/a/d/a/f9d48d4daa1872534114eab6655f3be0cd56.png
catalog: true
tags:
    - Yuchen Ni
    - Linux
    - Cloud Computing
---


![](https://cdn.pling.com/img/8/a/d/a/f9d48d4daa1872534114eab6655f3be0cd56.png)

After this learning you will be confident to be a Linux Architect/Cloud Computing Architect/System Engineer, and other important roles in the computer industry.

To be honest, linux combines a lot of other subjects of other computer brunches. eg: Website, System, Development, Security, Application Architecture, Data Storage etc. It provides a very good platform for linux Aechitect to develop their career with diverse profissions and potential opportunities.

Actually, everyone needs to interact with linux from mobile phones, online shopping, online course, embedded development etc. Nearly all of those applications have to use linux!

Today, computing industry has growing so fast, and the big giants such as google clouds, amazon aws, microsoft azure all develop theri cloud coputing for catering the market, which potentially needs thousands of Linux Architect in the future! As internet industry grows, the web development is getting bigger and their architect is getting more complicated, the need for the linux architects is becoming more urgent.

Especially for those experienced talents of operation and maintainance who are increasing becoming more important and getting more salary as they work consistently.

In my personal experience, the requirements for techinical experience are becoming higher, and the architects are thsoe people who deeply know and familair with the architecture and application in a company, they are getting more attensions


## Outline
- Basics(1)(2)(3)
- Shell(1)(2)
- NoSQL(1)(2)
- High-Concurrency Architecture For Large Websites(1)(2)


## Baics(1)
- What is Operation and Maintenance？
Operation and Maintenance refers to the Internet Operation and Maintenance, which belongs to the technical department. The four big departments for the intenet prodcution are Technical Department, R & D Department, Testing Department, and System Management Department.

Internet Operation and Maintenance is service centred, and it is supported by **Stability**, **Security**, **Efficiency**, which ensures the company can 7*24 hours operate to provide high quality service.

As a linux architect 20% of the time will be dealing with the urgent problems, and 80% will be doiing other less urgent works.

- Career Development:
   
   **Technical**:  1. Linux Intermediate Architect -> Senior Architect
                   2. Linux Intermediate Architect -> Puthon Automation Developer
                   3. Linux Intermediate Architect -> MySQL Senior DBA
   
   **Management**: Operations Manager -> Operations Director -> CTO/Vice President -> Entrepreneur

- Classifiactions of Operation and Maintainance:
   1. Applicaton(SRE)
   2. System(SYS)
   3. R&D(DEV)
   4. Database(DBA)
   5. Security(SEC)
   
- What can you do after learning?
   1. Familiar with environment deployment, Backup, Monitor, and other tasks.
   2. Familiar with automation operation and maintenance.
   3. Ability to achieve architecture optimization.
   4. Able to handle Operation and Maintenance Engineer, Architect, and other jobs.
   
- Knowledge Structure and Importance:
   1. Operation and Maintainance Basics
   2. Shell
   3. NoSQl
   4. High-Concurrency Architecture For Large Websites
   5. Autoate Operation and Maintainance
   6. KVM Virtualization
   7. Security of Operation
   8. Version management and continuous integration
   9. Interview Preparation
   
## Cron 
- Environment we need:
   1. OS / CentOS 7.6
   2. Remote management tools: xshell, xftp
   3. System Optimization: Reference Documentation
   
- Introduction to Scheduled Tasks：
   Enable automatic process of certain service and command at particular time without human interation with the system, which are the periodic tasks to prepare the data storage regularly.
   
- How to use **at**: 
```linux
at [OPTION] TIME
```
TIME can be in different forms:
    1. HH:MM [YYYY-mm-dd]  
    2. noon, midnight, teatime
    3. tomorrow
    4. now+#
    5. UNIL: minute, hours, days, OR weeks
     
**Examples:**

- now +5munites (tasks will be excuted in 5 minutes)
- now +1hours   (tasks will be excuted in 1 hour)
- now +31days   (tasks will be excuted in 1 month)
- now +1weeks   (tasks will be excuted in 1 week)
- 12:32         (tasks will be excuted at 12:32 today)

**Example: (Open web service at 11:30pm tonight)**

- Assumption: System has started atd service
```linux
[root@kongd ~]# yum install at
[root@kongd ~]# systemctl start atd.service
[root@kongd ~]# systemctl enable atd.service
```
- Set:
```linux
[root@kongd ~]# at 23:30
at> systemctl restart httpd
at> <EOT>
job 1 at Mon Sep 23 23:30:00 2019
```

- Scheduled Stask Introduction:
   1. One Time Scheduled Task:** `Control+D` key combination to end the task
   2. `at` command receives the previous `echo` command info, enbabling non-interatcive wat to establish an one time task.
```linux
[root@kongd ~]# echo "systemctl restart httpd" | at 23:30
job 2 at Mon Sep 23:30:00 2019
```
   3. check: `at -l`
```linux
[root@kongd ~]# at -l
1 Mon Sep 23:30:00 2019 a root
2 Mon Sep 23:30:00 2019 a root
```
   4. delete: atrm
```
[root@kongd ~]# atrm 2
```
   
   
   
   
   
   
## Summury:
This is the Introduction to Linux Automation Operation and Maintenance which might provide a good understanding for you to understand some basic concepts, the further infomation will be added in other posts with tag linux/cloud computing.


--- By Yuchen Ni



