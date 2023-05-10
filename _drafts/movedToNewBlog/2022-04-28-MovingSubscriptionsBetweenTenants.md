---
title: "Moving subscriptions between tenants"
categories:
    - Azure
tags:
    - Subscriptions
header-img: "/assets/images/top_images/AzureTOP.jpg"
subtitle:   "Moving subscriptions between tenants"
---
![Moving subscriptions between tenants](/assets/images/top_images/AzureTOP.jpg)A quick post about moving subscriptions between tenants.

It will be a very quick post. I needed to move my two subscriptions between tenants. One tenant - named A was expired and I created another tenant - named B. And that post will be about moving subscriptions between tenants A to B.

So, let's start.

The first part is creating an external guest account on tenant A for the user which is on tenant B. Not needed to add any roles right now. Just invite, accept the invitation as user@tenantB and go back to tenant A again.

![Moving subscriptions between tenants](/assets/images/posts/2022/MovingSubscriptionsBetweenTenant/01.png)

Second part is assign a Owner Role for user from tenant B for specific subscription. To do that, go to the tenant A > Subscriptions > Select Subscription > IAM > Role Assignments > Add > **Add role assignments**.

![Moving subscriptions between tenants](/assets/images/posts/2022/MovingSubscriptionsBetweenTenant/02.png)

Select an Owner role and assign that role to user@tenantB.

The third step is to move subscriptions on the new Tenant B from the old directory to the new directory. To do that, log on as user@tenantB, right-click on the username on the right top and select **switch organization**.

![Moving subscriptions between tenants](/assets/images/posts/2022/MovingSubscriptionsBetweenTenant/03.png)

Now from the top search bar, select Subscriptions and select subscription which you're the owner and what you want to move. To move the subscription, you need to click the **Change** button.

The last step is just a confirmation of moving those subscriptions to the new directory. Select the proper destination directory and click the Change button again.

![Moving subscriptions between tenants](/assets/images/posts/2022/MovingSubscriptionsBetweenTenant/04.png)

After some time, the subscription will be moved depending on the resources group, etc.
