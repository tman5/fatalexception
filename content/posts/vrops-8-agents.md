---
title: "vROPS 8.0 Telegraph Agent"
date: 2020-03-16T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","vROPS", "Monitoring", "Agent"]
---

With the impending demise of the EPOPS agent, I was hopeful the newer lighter Telegraph agent would fully replicate the functionality. While the new agent is relatively easy to push from the console and it does a great job with built-in apps, monitoring custom services does not appear to be a feature. With EPOPS you could monitoring custom Windows services, even use a custom script. Now (with Linux as well), it appears this functionality is gone. You can still check ICMP, TCP ports and such but not like before. Please, if anyone can find any more info about this let me know but for custom monitoring, it looks like this new Telegraph agent is very 1.0. I should note that again, this is not a very highly documented feature from VMWare. That seems to be a trend where they'll release a new version of a product and tout features but the documentation on them is very little (until much later!).