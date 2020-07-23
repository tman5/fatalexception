---
title: "0x2 Storage Issues Make Host Go Unresponsive"
date: 2020-07-22T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","storage", "HBA", "unresponsive", "qlogic", "driver", "bug", "management", "0x2"]
---

The dreaded 0x2 errors on the Qlogic driver! When will this be fixed! I cry this because I find very little information online about it. We've all experienced storage issues. Maybe some severe others not so much. But, how many of us have experienced a storage issue only to find that an ESXi host goes unresponsive after the issue is fixed or during the issue. Now your VMs may or may not keep running. More often than not I find them to keep running. But sometimes they don't. Having worked with support and others extensively it seems like there may be some race style bug in the QLogic driver for HBAs where certain storage errors like 0x2 can cause the hostd to eventually become unresponsive. It's like it can't handle the glut of logs. You may get lucky and the host come back. but maybe not. Regardless, this is still happening with the newest builds of 6.7. Maybe in 7.0 this is addressed but it is still a frustration with 6.7. I don't know why the hostd is so sensitive to storage issues and gives up so easily. Maybe someone else can enlighten me?