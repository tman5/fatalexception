---
title: "vRLI Key Error"
date: 2020-04-27T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","vRLI", "Key", "Issue", "Upgrade", "Java"]
---

Upgrade your vRLI and find issues connecting to AD or to your vSphere? When you try to connect do you find some sort of key error? Fear not! This fairly easy to fix but there isn't a lot of info online about this. I got these steps from VMware and pasted them here exactly. In the future supposedly there will be an article published about this, but until then here we go. I'll update once it becomes available. Just know I can't take credit for these steps but they were IMMENSLY helpful. 

Confirm the truststore is corrupt by listing the contents of the truststore.

In vRealize Log Insight 8.0, the truststore is located here:
```/usr/java/jre-vmware/lib/security/cacerts```

To list the contents of the truststore, run keytool using the following command:
```/usr/java/jre-vmware/bin/keytool -list -keystore cacerts```
If an error is encountered, the truststore is corrupt and needs to be replaced.

A corrupt truststore can be replaced by using a copy from a healthy vRealize Log Insight node from the same cluster, the old SLES partition after upgrading to vRealize Log Insight 8.0. 

Methods:
- Use a working trust-store from a working node to replace the existing one in the following directory:
```/usr/java/jre-vmware/lib/security/cacerts```

- Copy the old trust-store from the old SLES partition from the 4.8 vRealize Log Insight build to the vRealize Log Insight 8.0 instance on the Photon partition:
1. Log into the affected node as root
2. Enter the following commands to mount the old partition and copy over the old truststore:
```mkdir test
mount /dev/sda3/ test
cp test/usr/java/jre1.8.0_202-amd64/lib/security/cacerts /usr/java/jre-vmware/lib/security/cacerts```
3. Run the following commands to unmount the old partition and delete the recently mounted directory:
```umount /dev/sda3
rm -r test```

