# Challenege 1: Provisioning a Cloud PC

## Introduction

Windows 365 is a new cloud-based service offered by Microsoft that allows businesses to stream a virtualized version of Windows 10 or Windows 11 to any device with an internet connection. Essentially, it is a subscription-based service that enables users to access a cloud-based Windows desktop from any device, including laptops, tablets, and smartphones, without needing to install Windows locally. The service is designed to provide greater flexibility and scalability to businesses, allowing them to quickly and easily provision Windows-based virtual machines to their employees as needed.

With Windows 365, users can log in to their cloud-based Windows desktop from anywhere, using any device, and access all their apps, files, and settings as if they were using a physical computer. The service is particularly useful for businesses with remote workers, as it enables employees to work from any location and on any device, while still providing the same Windows experience and security they would have in the office.

## Challenge

You have purchased one Windows 365 licenses. At this point, you can start with the provisioning of Cloud PCs.

To set up your system to provision on-demand Cloud PCs for you, you need to:

- An AAD group with **GRP-PUNK[count]-Users**, e.g. GRP-P1-Users, is already created.
- Assign licenses to your user/group.
- Your User should have local admin rights for his Cloud PC.
- Create an Azure network connection (ANC) so that the cloud PC runs on a self-hosted network.
- Create a provisioning policy.
- **Make sure your Cloud PC has a custom name that is not the default.**

## Success Criteria
1.  A Windows365 & Intune License is automatically assigned to your users.
2.  Your User has local admin rights.
3.  (If one of the first 10) An ANC is created and the Cloud PC is deployed into a self-hosted network
4.  A provisioning policy with **PP-PUNK[count]-YourPolicyName** is created.
5.  A Cloud PC deployment is running.

## Learning Resources
- [Deployment overview](https://learn.microsoft.com/en-us/windows-365/enterprise/deployment-overview)
- [Group Assignments](https://learn.microsoft.com/en-us/azure/active-directory/enterprise-users/licensing-groups-assign)
- [Create a provisioning policy](https://learn.microsoft.com/en-us/windows-365/enterprise/create-provisioning-policy)
