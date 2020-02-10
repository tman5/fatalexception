---
title: "VMware Tools on Server 2012 Update Issues"
date: 2020-01-17T17:00:43-05:00
draft: false
showFullContent: false
tags: ["VMware","Troubleshooting"]
---

There seems to be issues with auto-upgrading VMware tools to the newest version on some 2012 instances. The tools will install but will crash constantly. Trouble is it's not all of them. While I haven't been able to pinpoint the issue I have found a workaround. If you uninstall the tools with `setup /c` and then remove ALL files from the VMware Tools directory under Program Files, then a clean install with succeed. The one key is that you MUST stop the VMware Auth service in services for this to fully work or else the delete won't work. See the very simple PowerShell script below. NOTE: It relies on the fact of the tools being mounted to D:\ (which can be done via PowerCLI with `mount-tools` though I guess it depends if you've re-mapped that disk drive in Windows to something else... future improvement!)


```powershell
d:/setup64/exe /c
Remove-Item "c:\program files\vmware"
```