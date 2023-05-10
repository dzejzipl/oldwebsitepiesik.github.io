---
title: "Distribute Self-Generated certificate from WAC by GPO"
categories:
    - HomeLab
tags:
    - WAC
    - Windows Admin Center
header-img: "/assets/images/top_images/HomeLab2.jpg"
subtitle:   "Distribute Self-Generated certificate from WAC by GPO"
---
![Distribute Self-Generated certificate from WAC by GPO](/assets/images/top_images/HomeLab2.jpg)Last time I showed you how I deployed WAC on my HomeLab. Now I will show you how to deploy a Self-Signed certificate from WAC to other devices.

The article related to deploying WAC on my HomeLab can be read [here](https://www.piesik.me/2022/01/05/WACOnMyLab/).

But whenever I'm trying to log on to the WAC from a different machine, for example, my laptop I'm receiving information that this certificate is not valid, etc... Annoying situation.

So, the first step was exporting the certificate from the machine where WAC was installed. It's on the Machine\Personal and the certificate needs to be exported as *DER encoded binary*. Without the primary key. After that, save it to the shared location and save this shared location to your notes.

![*Distribute Self-Generated certificate from WAC by GPO](/assets/images/posts/2022/2022-01-05-DistributeCertificateFromWAC/01.png)

Now you need to create a GPO policy for your machines. Navigate to the *Computer Configuration > Windows Settings > Security Settings > Public Key Policies*. Right-click on the *Trusted Root Certification Authorities* and select **Import** to import exported in the last step certificate. Use the .cer file which was exported and select option *Place all certificates in the following store* and finish importing.

![*Distribute Self-Generated certificate from WAC by GPO](/assets/images/posts/2022/2022-01-05-DistributeCertificateFromWAC/02.png)

The last step is to do a magical **gpupdate /force** with a user who has administrative access on this machine / or restart the device to apply this certificate.

After that - there is no more information about this certificate!
