---
title: "vROPS for Physical Machines? Part 1"
date: 2020-05-17T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","vROPS", "EPOPS", "physical", "operations", "vRealize", "agent", "metrics", "custom"]
---

Is it possible? How does it work? Does it work well? The last question is the one you should ask before you embark on this vROPS on physical adventure. It does work. Now, as of this writing it ONLY works with the soon to be deprecated EPOPS agent. It is NOT currently supported with the newer telegraph agent yet (hopefully in the future). The agent mostly works without a hitch. Some of the in box alerts don't work for physicals because they are looking for VM specific metrics, so you have to create custom symptoms and alerts just for physical (like disk usage for instance). It's not a great solution as you'll find that vROPS is geared towards virtual very well and  it just so happens to work with physical.  Overall I don't like in vROPS how you have to make custom policies and enable/disable custom thresholds for groups and policies and sub-policies (it get's complicated quickly) and physical just makes it even more complicated. My overall advice would be to use another enterprise-grade product for monitoring physicals. But, other than getting less metrics and needing to customize some pieces, it does successfully monitor physical with the EPOPS agent. I will be writing more about some troubles encountered with it but this will suffice for now. Hopefully I'll be able to write about the telegraph agent on physicals soon!
