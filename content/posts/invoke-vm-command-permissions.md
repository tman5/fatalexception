---
title: "vROPS 8.0 Telegraph Agent"
date: 2020-03-16T17:00:43-05:00
draft: true
showFullContent: false
tags: ["VMware","vROPS", "Monitoring", "Agent"]
---

With a security update last year, the ```invoke-vm``` command can no longer pass credentials. You must specify a credential object or type in your credentials when using the command. This doesn't see documented all that well so I thought I'd bring it up here. It will drive you nuts trying to figure out why it doesn't pass through credentials any longer and you now must use the ```-GuestCredential```