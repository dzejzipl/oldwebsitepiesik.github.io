---
title: "WAC on my HomeLab!"
categories:
    - HomeLab
tags:
    - WAC
    - Windows Admin Center
header-img: "/assets/images/top_images/HomeLab2.jpg"
subtitle:   "WAC on my HomeLab!"
---
![WAC on my HomeLab!](/assets/images/top_images/HomeLab2.jpg)So I decided to back to work with my HomeLab! And the first step was... Installing Windows Admin Center!

I need to back to work with My HomeLab. All machines have installed an operating system - depending on the type of machine: Windows Server 2022 or Windows 10 Enterprise for laptops.

Also, Hyper-V roles are installed, virtual machines are created, and has installed Windows Servers also.

DHCP, DNS, AD DS roles were also installed. Most important GPO policies are also created. Local Administrator groups, RDP settings, etc.

So, the next feature which should be implemented before AAD Connect is WAC - Windows Admin Center.

In this article, I will show you how to install it as a *Managed server*. The rest of the possibilities to install you can read [here](https://docs.microsoft.com/en-us/windows-server/manage/windows-admin-center/plan/installation-options#installation-types)

The first step of the installation is to choose what data are sent to the Microsoft, second step is to select the proper settings of the installation

![WAC on my HomeLab!](/assets/images/posts/2022/2022-01-06-WACOnMyLab/01.png)

I will be not using WinRM over HTTPS, because for now - I don't use PKI in my environment. Rest settings stay as it is.

I will be using default port: 443 and a self-generated certificate. Also, the option to redirect traffic from port 80 to 443 should be enabled.

After that... Start installing. And note your URL for that WAC.

![WAC on my HomeLab!](/assets/images/posts/2022/2022-01-06-WACOnMyLab/02.png)

So open the above URL, log on using accounts that have Local Administrative permissions on this machine, and...

![WAC on my HomeLab!](/assets/images/posts/2022/2022-01-06-WACOnMyLab/03.png)

WAC is now installed!

Two important things...

To start properly using WAC - read this article: [Windows Admin Center - without Domain Admin!](https://www.piesik.me/2020/08/22/UseWACWithouDomainAdmin/#) to avoid using a Domain Admin account, which is veeeery important.

Second: Basically, every user needs to add their connections which will be used. But you can add shared connections, which will be available for every user who will log on to the WAC. To do this, open WAC > go to settings > Shared connections and add necessary servers.

![WAC on my HomeLab!](/assets/images/posts/2022/2022-01-06-WACOnMyLab/04.png)

Good luck with the usage of WAC!
