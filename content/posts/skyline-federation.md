---
title: "Skyline Federated Authentication"
date: 2020-01-17T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","Cloud", "Skyline"]
---
I want to post this because I've found the documentation and steps very unclear from VMware in regards to this. Say your security policy requires federated identities. Put simply you CANNOT just use a VMware account you create in the cloud; you MUST use your on-prem credentials (we'll use AD in this case). So how do you do that? Well it's a combination of VMware Identity Manager Connector and a VMware Identity Manager tenant in the cloud. 

In this case we're going to use ADFS to do the federation. This isn't required but it does make it easier to do pass-thru authentication and multi-factor auth. This assumes you already have ADFS setup and externally accessible. Here are the high-level steps. 

1 - Stand up a Windows server and make sure it can get to the required cloud URLs
2 - Open a ticket in the VMware cloud console* to start the vIDM process. This will trigger what VMware calls the "white-glove" onboarding. They will then setup a cloud tenant for the vIDM instance. Note this is at no cost to the customer (well, assuming youre already using their products on-prep)



* I should note I had to actually make a non-federated account in the VMware cloud to be able to open a ticket. You also need to keep this account after the initial setup (though I'm still working on doubly confirming this as I dislike leaving these backdoor accounts)