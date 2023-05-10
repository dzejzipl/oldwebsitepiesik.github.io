---
title: "Intune Settings vs. GPO"
categories:
    - MEM
tags:
    - Intune
    - GPO

header-img: "/assets/images/top_images/Microsoft365TOP.png"
subtitle:   "Intune Settings vs. GPO"
---
![Intune Settings vs. GPO](/assets/images/top_images/Microsoft365TOP.png)How to work on the Hybrid Environment when we have those same settings on the Intune and GPO?

Another post from implementation which I did for my external Client.

Because he has now fully on-premise environment we decided to implement some Intune functionality.

For example, Bitlocker settings. Due to the old environment, they are now configured by GPO. I prefer to have this on the Intune. Of course, those machines will be also Hybrid AD joined so they will have access to the local AD, but... Yes, some policies should be in the Intune for me.

The main purpose of this post is to show you how to configure Intune vs. GPO.

By default, GPO policy is winning. But as I write earlier, we need to set up that every policy what is already exists in the GPO will be overwritten by MEM policy what will be doing this same thing.

Everything you need to do is create a new *Custom Configuration profile* with OMA-URI: 

```text
./Device/Vendor/MSFT/Policy/Config/ControlPolicyConflict/MDMWinsOverGP
```

With configuration:

* Data type: Integer
* Value: 1

![Intune Settings vs. GPO](/assets/images/posts/2021/IntuneSetttingsVSGPO/01.png)

If you set up this value to 0 - default settings will be used, which means GPO will be winning.
