# Challenge 1: Provisioning a Cloud PC

[Previous Challenge](../AVD/03-AVD-FSLogix.md) - **[Home](../../readme.md)** - [Next Challenge](./02-W365-RDP-Properties.md)

## Introduction

Windows 365 is a new cloud-based service offered by Microsoft that allows businesses to stream a virtualized version of Windows 10 or Windows 11 to any device with an internet connection. Essentially, it is a subscription-based service that enables users to access a cloud-based Windows desktop from any device, including laptops, tablets, and smartphones, without needing to install Windows locally. The service is designed to provide greater flexibility and scalability to businesses, allowing them to quickly and easily provision Windows-based virtual machines to their employees as needed.

With Windows 365, users can log in to their cloud-based Windows desktop from anywhere, using any device, and access all their apps, files, and settings as if they were using a physical computer. The service is particularly useful for businesses with remote workers, as it enables employees to work from any location and on any device, while still providing the same Windows experience and security they would have in the office.

## Challenge

You have purchased one Windows 365 licenses. At this point, you can start with the provisioning of Cloud PCs.

To set up your system to provision on-demand Cloud PCs for you, you need to:

- An Entra ID group with **GRP-P[count]-Users**, e.g. GRP-P1-Users, is already created.
- Assign licenses to your user or group.
- Your User should have local admin rights for his Cloud PC.
- Your Cloud PC is using the Microsoft Hosted Networks.
- Create a provisioning policy.
- **Make sure your Cloud PC has a custom name that is not the default, for example: CPC-P1-%RAND:5%"**

## Success Criteria
1.  A Windows365 & Intune License is automatically assigned to your users.
2.  Your User has local admin rights.
3.  A provisioning policy with **PP-P[count]-YourPolicyName** is created.
4.  A Cloud PC deployment is running.

## Learning Resources
- [Deployment overview](https://learn.microsoft.com/en-us/windows-365/enterprise/deployment-overview)
- [User settings](https://learn.microsoft.com/en-us/windows-365/enterprise/assign-users-as-local-admin)
- [Create a provisioning policy](https://learn.microsoft.com/en-us/windows-365/enterprise/create-provisioning-policy)
