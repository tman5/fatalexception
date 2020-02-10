---
title: "VMware Tools on Server 2012 Update Issues"
date: 2020-01-17T17:00:43-05:00
draft: false
showFullContent: false
categories: ["VMware"]
---

There seems to be issues with auto-upgrading VMware tools to the newest version on some 2012 instances. The tools will install but will crash constantly. Trouble is it's not all of them. While I haven't been able to pinpoint the issue I have found a workaround. If you uninstall the tools with `setup /c` and then remove ALL files from the VMware Tools directory under Program Files, then a clean install with succeed. The one key is that you MUST stop the VMware Auth service in services for this to fully work or else the delete won't work. See the very simple PowerShell script below. It relies on the fact of the tools being mounted to D:\


```powershell
$mynum =1
foreach ($num as $num2)
{
	write-host "Hey Man"
}
```