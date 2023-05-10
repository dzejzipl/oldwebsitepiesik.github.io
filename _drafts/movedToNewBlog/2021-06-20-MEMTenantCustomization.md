---
title: "Customize your MEM Tenant"
categories:
    - MEM
tags:
    - Customization
    - Intune

header-img: "/assets/images/posts/2021/LearnMEMandMEMC/top.jpg"
subtitle:   "Customize your MEM Tenant"
---
![Customize your MEM Tenant](/assets/images/posts/2021/TenantCustomization/top.jpg)Show branding of your organization to your users on the Company Portal app!

Branding is very important.

It is important to our users. Can show to what organization they are log in. If we have multiple enironments (like test, uat or prod) we can for example, set a background color to RED to show users that they will be working on test environment etc.

Using Branding we can also configure HelpDesk information for end-users to help them to contact with us if they have any issues.

There are two possibilites to configure Branding for our tenant.

The first is Company Branding in the Azure AD portal - it will be described on the next post.

The second one is configure branding for Company Portal application. About this one I will show you now how to configure it.

By default, Company Branding is empty. For example, there is web version of Company Portal which by default looks like this:

![Customize your MEM Tenant](/assets/images/posts/2021/TenantCustomization/01.png)

But I will you show you how to configure it looks like on below screen:

![Customize your MEM Tenant](/assets/images/posts/2021/TenantCustomization/02.png)

By default, there is no even HelpDesk information!

Ok, let's configure those options.

To do this, open MEM portal, go to the *Tenant Administration* and find **Customization** tab.

First, you need to configure general settings for all of users. After that - you can overwrite specific settings for different groups. For example, IT users should have options to reset own devices etc.

![Customize your MEM Tenant](/assets/images/posts/2021/TenantCustomization/03.png)

There are multiple options to configure. You should configure Company Logo, description, HelpDesk information etc. - that things are important to end users.

Also, you can disable resetting own devices by users using this settings also.

![Customize your MEM Tenant](/assets/images/posts/2021/TenantCustomization/04.png)

It is easy to configure, but as you can see - can help a lot for end-user.
