---
title: "Deploying new Remote Help app using PSAppDeployToolkit"
categories:
    - MEM
tags:
    - Intune
    - Remote Help
    - PSAppDeployToolkit

header-img: "/assets/images/top_images/Microsoft365TOP.png"
subtitle:   "Deploying new Remote Help app using PSAppDeployToolkit"
---
![Deploying new Remote Help app using PSAppDeployToolkit](/assets/images/top_images/Microsoft365TOP.png)Learn how to deploy new Remote Help application by Microsoft Endpoint Manager

A couple of weeks ago Microsoft released information about the new Remote Help application - The enterprise version of Quick Assist. If you want to read all information about this application, requirements, etc - please [go here](https://docs.microsoft.com/en-us/mem/intune/remote-actions/remote-help).

In meantime, I decided to deploy this application by **PSAppDeployToolkit** to have everything on the logs created by PSADT. I also used PSADT in a post about [Cisco AnyConnect VPN](https://www.piesik.me/2021/11/24/CiscoAnyConnectByIntune/)

As in my previous posts, I'm customizing the *Variables: Application* section and providing an installation and uninstallation command.

Also, I copied the EXE file to the Files folder.

So, my installation command looks like this:

```powershell
Execute-Process -Path "$dirFiles\Remotehelp.exe" -Parameters "/install /quiet acceptTerms=yes"
```

And uninstallation command:

```powershell
Execute-Process -Path "$dirFiles\Remotehelp.exe" -Parameters '/uninstall /quiet acceptTerms=Yes'
```

What is important, **acceptTerms=Yes** is case sensitive. Yep. Didn't know that and that was the issue for me earlier.

During the creating app in the MEM portal I provided information:

Install command

```text
%windir%\sysnative\windowspowershell\v1.0\powershell.exe -ExecutionPolicy Bypass -file "Deploy-Application.ps1"
```

Uninstall command

```text
%windir%\sysnative\windowspowershell\v1.0\powershell.exe -ExecutionPolicy Bypass -file "Deploy-Application.ps1 -DeploymentType Uninstall"
```

For a detection method I've used that kind of option:

![Deploying new Remote Help app using PSAppDeployToolkit](/assets/images/posts/2021/InstallRemoteHelpUsingPSADT/01.png)

And... Installed on all devices.

![Deploying new Remote Help app using PSAppDeployToolkit](/assets/images/posts/2021/InstallRemoteHelpUsingPSADT/02.png)

Any questions? Leave a comment!
