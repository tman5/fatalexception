---
title: "MTUs"
date: 2020-04-06T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","network", "MTU", "dvs", "switch"]
---

If you've ever wondered about that MTU health check on a dV switch, fear not! One piece I've noticed is that if the full path (between hosts in the case of VSAN) is NOT the same MTU, this alert will fire. The "fix" is to ensure all network switches in the path have the MTU of that size or "jumbo frames" enabled. Generally you don't want mismatched MTUs anyway as it can cause other issues, but as a general troubleshooting step a good switch check doesn't hurt. Note this isn't for NSX specifically (though it does require MTU 1600 minimum which is above the normal default) but instead a general tip for dv switches. If you see those errors come and go, check your switches (also check them before you go messing with it on the VMware side too!)