# Challenege 2: Configure RDP Properties

[Previous Challenge](./01-W365-Provisioning-CPC.md) - **[Home](../../readme.md)** - [Next Challenge](./03-W365-App-Deployment.md)

## Introduction

With the Remote Desktop Protocol (RDP) you can create redirections that let users connect to peripherals (like cameras, USB drives, and printers) from remote devices like Cloud PCs. By default, these redirections are enabled for Cloud PCs. 

For **security** reasons, you want to override the default and block some devices from being redirected.

In General there are two ways to manage these redirections:

**Settings Catalog**: Use a device configuration policy in Microsoft Endpoint Manager. Supports both Azure Active Directory (Azure AD) join and hybrid Azure AD join Cloud PCs.

**Group Policy Object (GPO)**: Use GPOs in Windows Server Active Directory. Supports hybrid Azure AD join Cloud PCs only.

## Challenge

Your Security Team want to **prevent** that a user can **Copy & Paste** data from their local client to the Cloud PC.

In addition **no local drive** should be available in the remote session.

## Success Criteria

1. A new dynamic group with **your** Cloud PC is configured.
2. A new device configuration policy is created for your Cloud PC and **Copy & Paste** is not possible and **local drives** are **not** redirected.

## Learning Resources
- [Manage RDP Devices](https://learn.microsoft.com/en-us/windows-365/enterprise/manage-rdp-device-redirections)
- [Dynamic membership rules for groups in Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/enterprise-users/groups-dynamic-membership)
- [Create a device profile in Microsoft Intune](https://learn.microsoft.com/en-us/mem/intune/configuration/device-profile-create)