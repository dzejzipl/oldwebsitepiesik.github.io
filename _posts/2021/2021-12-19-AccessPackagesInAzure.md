---
title: "Start using Access Packages to manage access in your organization!"
categories:
    - Azure
tags:
    - MEM
    - Access Packages

header-img: "/assets/images/top_images/AzureADTOP.jpg"
subtitle:   "Start using Access Packages to manage access in your organization!"
---
![Start using Access Packages to manage access in your organization!](/assets/images/top_images/AzureADTOP.jpg)Learn how to start using Access Packages to manage access in your organization - learn example how to provide access for beta testing Windows 11!

Last time I was on the Microsoft Workshops about Hybrid Identity. The trainer shows many great features - one of them was Access Packages and groups Management. I decided to learn something more about this feature - **Access Packages** and I want to show you, what I learned.

In many organizations, there are issues with requesting access to the new packages. IT needs to manually job and add users to the specific groups. Even if those groups are related to the group shares for example. Or applications. Or SharePoint websites.

But what if we can use for that purpose functionality named "Access Packages" on Microsoft 365?

In a couple of words this looks like this:

* IT creates a package with assigning proper groups, approvers, etc
* End-User requesting package using a specific website
* Approver(s) can approve or decline the request(s)
* End-User is receiving notification that request is done or canceled.

What is important, everything is automated. You can even request access to a specific package for a specific period of time. If you know that you need access to the specific SharePoint site for 2 months, you can set this period of time. And after that time, access will be automatically revoked.

Ah, there also exists Access Reviewing for Owners. Many of the options, what can be used to manage access to your organization.

But in this article, I will show you, how to request access to Windows 11 by Users in your organization.

The main requirement to use that feature is Azure AD Premium P2. Licensing topic is [described here](https://docs.microsoft.com/en-us/azure/active-directory/governance/entitlement-management-overview#license-requirements). Please read it before implementing it on your tenant.

## Identity Governance

The first thing in that step is logon to the Azure AD portal > Identity Governance > Access Packages.

On this page, you can view all existing packages or create a new one. When you're starting, there will be no access packages. So let's start with creating some.

Click on the **New access package** button and provide a name and description. Be informed, that that information will be displayed for end-users. I provided information:

* Name: Windows 11 Testing
* Description: If you want to upgrade your system to Windows 11, request access to this package.

For now, use a *General* catalog. Later, you can manage catalogs on the Identity Governance > Catalogs page. Please consider the creation of a proper structure for your organizations, like Operating Systems, Applications, Websites, Teams, Sharepoints, Groups, ShareDrives, etc...

But if you want you can create a new catalog during the creation of your package. You just need to click: *Create new catalog* and provide the necessary details.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/01.png)

In the next window, you need to select to what type of resource you're granting access.

Can be:

* Groups and Teams
* Applications
* SharePoint sites

I will select a proper group that will be assigned to the Windows 11 Testing phase. I already created that group.

So, I'm clicking on the *Groups and Teams* button, after that I'm selecting checkbox: "See all Group and Team(s) not in the 'General' catalog. You must have the correct permissions to add them to this access package." to see all groups and on the end, I'm choosing a proper group. It will be back to the main view, where you need to select a proper role. It can be a Member of the Owner. I will of course select a Member.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/02.png)

In the next tab, you need to:

* Who can request access (I will choose **For users in your directory**)
* Every user without guest can request this package
* If that is something that should have approval - for example, migration to Windows 11 you need to enable approval for that
* And you can choose if that form is active or not - I will select Yes for *Enable new requests*

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/03.png)

You can select how many steps of approvals you want. For example, the first step should be a Manager of End-User. After that, specific group owner. You can add also alternative approvers if the main approver is unavailable.

Another step is **requestor information**.

Here you can specify, what question the end-user need to fill.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/04.png)

The next step is to manage the lifecycle. What it does mean? You can select after which date the user will lose access to the specific Access Packages. For example, you can select that the user will lose access to the specific resource after the 01.01.2022 date - to the end of this year.

Another thing on this tab is **Access Reviews** - you need to specify if that access should be reviewed by the Manager, Self-review by end-user, or by the specific reviewer(s), for example, the Access Management team.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/05.png)

The last step is to create a rule to manage custom extensions if you're using any of them. In my lab I don't use it, so... I will be don't configuring it. They can be customized during a specific stage of request.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/06.png)

After that - you can review all settings and create a package.

## End-User side

When End-user wants to request something, should visit page: [https://myaccess.microsoft.com](https://myaccess.microsoft.com) and check the existing catalog of packages that were created.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/07.png)

In our example, we will use the existing Windows 11 Package. The end-user needs to click Request, provide necessary details.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/08.png)

After a while, Package Owners will receive an email where will be a link to approve or deny this specific request.

![Start using Access Packages to manage access in your organization!](/assets/images/posts/2021/AccessPackagesInAzure/09.png)

When the request will be approved, the user will be added to the proper group. When we set an expiration date, will be removed from a specific group after this time.

## Last words...

I have to admit that this feature looks pretty nice. From my perspective, it will allow **all** organizations to help with managing access to the specific packages. Like software, shares, and everything else for what we need control access.

In the next article, I will show you how to configure Update Rings and Feature Updates to implement Windows 11 in your organization.
