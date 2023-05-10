---
title: "Disable Azure AD Connect on your tenant"
categories:
    - Azure AD
tags:
    - AD Sync
header-img: "/assets/images/top_images/AzureADTOP.jpg"
subtitle:   "Disable Azure AD Connect on your tenant"
---
![Disable Azure AD Connect on your tenant](/assets/images/top_images/AzureADTOP.jpg)Learn how to disable synchronization between your on-premise environment and AAD

Today I needed to disable synchronization between one of my tenant and the on-premise environment which was removed earlier. The reason was that I still receiving emails like the below:

*Your identity synchronization from on-premises is unhealthy*

So I decided to turn off that synchronization. This can be done by using three PowerShell commands with the account that has proper permissions to do that.

First, you need to install the **MSOnline** module if you don't have installed on your device.

```powershell
Install-Module MSOnline
```

The next step was logging in to this Module

```powershell
Connect-MsolService
```

After that - you need to disable synchronization by using this command:

```powershell
Set-MsolDirSyncEnabled -EnableDirSync $false
```

To check if synchronization was disabled you can execute this command:

```powershell
Get-MsolCompanyInformation | select DirectorySynchronizationEnabled
```

Should return **False**

And it's everything. Synchronization was turned off.
