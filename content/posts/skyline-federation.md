---
title: "Skyline Federated Authentication"
date: 2020-03-09T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","Cloud", "Skyline"]
---
I want to post this because I've found the documentation and steps very unclear from VMware in regards to this. Say your security policy requires federated identities. Put simply you CANNOT just use a VMware account you create in the cloud; you MUST use your on-prem credentials (we'll use AD in this case). So how do you do that? Well it's a combination of VMware Identity Manager Connector and a VMware Identity Manager* tenant in the cloud. 

This is a great resource as a one stop shop for information. It's not 100% complete but it's a huge help. You'll need to make sure the URLs are accessible by the on-prem connector - https://kb.vmware.com/s/article/76201

In this case we're going to use ADFS to do the federation. This isn't required but it does make it easier to do pass-thru authentication and multi-factor auth. This assumes you already have ADFS setup and externally accessible. Here are the high-level steps. 

1 - Stand up a Windows server and make sure it can get to the required cloud URLs

2 - Open a ticket in the VMware cloud console** to start the vIDM process. This will trigger what VMware calls the "white-glove" onboarding. They will then setup a cloud tenant for the vIDM instance. Note this is at no cost to the customer (well, assuming youre already using their products on-prep). You MUST use the cloud console to open the ticket. The regular My VMware portal will NOT work. I also recommend specifying in the ticket you want an Identity Manager Federation setup or something along those lines so they route it properly. 

3 - You will then schedule a meeting where support will come in and step you through the setup of the vIDM instance. In my case I used ADFS for the federation but you can use straight domain syncing as well. Just note that for the pass-through Kerberos you'll need ADFS. 

4 - After the vIDM is setup and properly talking to your on-prem vIDM Connector VM you'll schedule the next meeting to actually switch over your cloud console to use the vIDM instance. They essentially register your domain with the vIDM instance. I should note that I already had the cloud console setup for my org since I was testing Skyline advisor earlier. This is a required step. You keep your original account as a fail safe in case the identity manager is unavailable. You'll also need to link your newly synced accounts to the console with your MyVMware account. This is also required for support. 

A final note is that depending on how you setup your attribute syncing in vIDM and ADFS you may need to login to the cloud console with your internal domain username, not your email.

I hope this helps. It's not a step by step but the 'white glove' treatment helps with that since they guide you through the setup. 


** VMware inconsistently refers to Identity Manager as Workspace One Access. I think going forward it's supposed to be called Workspace One Access, but documentation and support still mostly call it Identity Manager. 

**** I should note I had to actually make a non-federated account in the VMware cloud to be able to open a ticket. You also need to keep this account after the initial setup. 