---
title: "Deploying Cisco AnyConnect by MEM (without MSI!)"
categories:
    - MEM
tags:
    - Intune
    - VPN
    - Cisco

header-img: "/assets/images/top_images/Microsoft365TOP.png"
subtitle:   "Deploying Cisco AnyConnect by MEM (without MSI!)"
---
![Deploying Cisco AnyConnect by MEM (without MSI!)](/assets/images/top_images/Microsoft365TOP.png)Learn how to deploy Cisco AnyConnect - exe file by Microsoft Endpoint Manager

For some time I'm working with one external Client. He asked me to deploy Cisco AnyConnect by MEM but wasn't able to provide me proper installation files, like MSI and MST files, etc.

Everything that I had was an executable file - exe file.

So I decided to pack this using PSADT and be sure that also configuration will be copied to the end-user device.

I started with downloading PSADT, configuring necessary variables at the beginning of the file. Everything was described [here](https://www.piesik.me/2021/06/13/DeploySynologyVPNusingPSADT/#) and in the previous article.

After that I decided to copy the .exe file to the **Files** folder and configuration files from folder: *%ProgramData%\Cisco\Cisco AnyConnect Secure Mobility Client\Profile* to the **SupportFiles\Profile** folder.

So my Installation command was looking:

```powershell
Execute-Process -Path "$dirFiles/anyconnect-win-4.9.00086-core-vpn-webdeploy-k9.exe" -Parameters "/qn"
Copy-File -Path "$dirSupportFiles\Profile\*.*" -Destination "%ProgramData%\Cisco\Cisco AnyConnect Secure Mobility Client\Profile"
```

But you need to also remember about the uninstallation method for that. For now, Intune doesn't support uninstallation from the Company Portal, but maybe in the future that will work, so use that command:

```powershell
Execute-MSI -Action 'Uninstall' -Path '{EEC110C1-BB5C-477D-8F7F-E6781FBA2F18}'
```

![Deploying Cisco AnyConnect by MEM (without MSI!)](/assets/images/posts/2021/CiscoAnyConnectByIntune/01.png)

About the profile files - they were taken from a machine that has already configured VPN.

And it is everything. You don't need to have an MSI file to deploy this software. Of course, if you have it, you can do more customization of your installation of this software. But in this case is not required.

Any thoughts? Ping me in the comments!
