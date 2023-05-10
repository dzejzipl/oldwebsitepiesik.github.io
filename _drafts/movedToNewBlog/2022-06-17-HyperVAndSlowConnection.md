---
title: "Hyper-V with External Switch and slow connection - part two"
categories:
    - Windows
tags:
    - Hyper-V
    - Windows 10
    - Windows 11
    - Intel Wi-Fi
    - Wi-Fi
header-img: "/assets/images/top_images/Windows10Top.jpg"
subtitle:   "Hyper-V with External Switch and slow connection - part two"
---
![Hyper-V with External Switch and slow connection - part two](/assets/images/top_images/Windows10Top.jpg)A long story to fix the issue related to the Slow connection after the creation of the external switch for Hyper-V.

A couple of days ago I started testing a new device - Zbook G8. A Very powerful device, oh, ah. Want it. 64GB of RAM. 11th of generation i9 processor...  I will be able to do anything on that device that I want. But...

After the installation of the Hyper-V role and the creation of an external switch, I wasn't able to work with an Internet connection. The connection was veeery poor. I remembered that I had already that issue. And was [described here](https://www.piesik.me/2020/08/12/HyperV-IntelWiFi/). But that doesn't help anymore. 

So I started looking for Google if anyone found a solution. I just found the information about how many people have this issue. The solution was easy - use an ethernet cable instead of a Wi-Fi connection if you want to work with Hyper-V. 

Oh, no! I didn't buy a laptop for using multiple cables!

So... I googled more... And more. Doing some magic stuff, commands, testing. Nothing.

Finally, I asked the Twitter that question:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Anyone faced issue with slow network connection after creation External Switch for new HP Devices and Windows 10 / 11? <br>Offload, RSC, update of drivers - nothing helps.<br>cc <a href="https://twitter.com/gwblok?ref_src=twsrc%5Etfw">@gwblok</a> <a href="https://twitter.com/hashtag/hp?src=hash&amp;ref_src=twsrc%5Etfw">#hp</a> <a href="https://twitter.com/hashtag/zbook?src=hash&amp;ref_src=twsrc%5Etfw">#zbook</a> cc <a href="https://twitter.com/HPSupport?ref_src=twsrc%5Etfw">@HPSupport</a></p>&mdash; Jakub Piesik (@dzejzipl) <a href="https://twitter.com/dzejzipl/status/1536821359925395456?ref_src=twsrc%5Etfw">June 14, 2022</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

And... 

Magic guy, Josh Hipple - [@joshuahipple](https://twitter.com/joshuahipple) - provided me information on how to fix that issue. But wait - I wasn't able to fix that, because the driver was missing.

So I decided to start from the beginning. Remove all network devices, switches, etc. 

And do the necessary steps:

1. Create External Switch with Wi-Fi card:

![Hyper-V with External Switch and slow connection - part two](/assets/images/posts/2022/HyperVAndSlowConnection/01.png)

2. Go to the Device Manager and select the **Microsoft Network Adapter Multiplexor Driver**.

![Hyper-V with External Switch and slow connection - part two](/assets/images/posts/2022/HyperVAndSlowConnection/02.png)

3. Go to the Properties tab > Advanced > and find two settings named: *Large Send Offload Version 2* for the IPv4 and IPv6. For both settings set up as **disabled**.

And it's everything!

Looks similar to the previous post? Of course. Here just need to select a different driver instead of the Wi-Fi card.

Works perfectly!
