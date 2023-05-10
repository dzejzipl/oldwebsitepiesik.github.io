---
title: "Create profile for Data Collection for Devices in MEM"
categories:
    - MEM
tags:
    - Intune
header-img: "/assets/images/top_images/Microsoft365TOP.png"
subtitle:   "Create profile for Data Collection for Devices in MEM"
---
![Create profile for Data Collection for Devices in MEM](/assets/images/top_images/Microsoft365TOP.png)How to start collecting data from devices that are used with MEM?

Last time, when I was playing with Feature Updates I realized that on one of the tenants I didn't enable Data Collection for enrolled devices in MEM. But what does mean? For example, if you will be creating settings for Windows Update for Business or Endpoint Analytics - those data will be not available because devices are not configured to return anything.

So I started to fix my issue and created profile by going to: *Windows* > *Devices* > *Configuration profiles* > **Create profile**

As a platform, you need to select *Windows 10 and later* and for profile type: *Templates > Windows Health Monitoring*.

Select a proper name and description and continue. On the next window, you have the option to select what data you want to collect:

* Windows Update
* Endpoint Analytics

In my case, I will select both because I will be using both options in the future. In the next step, I assigned that option for my all devices and saved my profile.

After some time, the profile was properly applied to the devices.

![Create profile for Data Collection for Devices in MEM](/assets/images/posts/2022/DataCollectionIntune/01.png)

And now I can back to work with Feature Updates and Ring Updates configuration! :)
