---
title: "The '-ilities' of Design"
date: 2020-01-17T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","Design"]
---

I cannot take credit for this, but I wanted to put it out there for all to see and understand. It originally was shown to me by Jayson Block (VCDX). There are key areas that go into desining IT systems. We probably hear them all the time - realiblity, stability, etc. Let's outline them here. This specifically can relate to VMware in this case. There are a number of academic articles discussing engineering ilities but I thought it useful here to focus on VMware.

- Reliability
- Stability
- Usability
- Availability
- Security
- Adaptability
- Scalability

Now I want you to rank them for your organization. 1-10. You may be surprised. Every organization will be slightly different but I think there are trends. Doing this exercise every so often helps put priorities in perspective. I think generally that you will find a couple of trends:
- Security is usually near the middle
- Availability, reliability and stability are usually near the top. I would argue that availability should be higher. Point and case if a host dies (loss of reliability), you can rapidly recover thanks to VMware technologies, so maybe reliability shouldn't be that high.
- Usability may be low. This may be because a lot of these systems are just infrastructure and not user facing, but what if it was user facing?
- Scalability is often put near the top as well and it is very important in this phase. I often feel this gets missed and later we have to figure out how to scale a system that was designed for a much smaller workload. 

I want to keep coming back to the ideas in this post. For now this is a good start when thinking about design.  