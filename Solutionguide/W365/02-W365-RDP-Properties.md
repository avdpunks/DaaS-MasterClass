# Solutionguide 2: Configure RDP Properties

## Introduction

For **security** reasons, you want to override the default and block some devices from being redirected.

## Challenge

Your Security Team want to **prevent** that a user can **Copy & Paste** data from their local client to the Cloud PC.
In addition no local drive should be available in the remote session.

## Success Criteria

1. A new dynamic group with **your** Cloud PC is configured.
2. A new device configuration policy is created for your Cloud PC and **Copy & Paste** is not possible and **local drives** are **not** redirected.

## Step 1 - Configure your dynamic group for your Cloud PCs (Devices)

Open the Microsoft Intune Admin Center [https://in.cmd.ms/](https://in.cmd.ms/) and select **Groups** to view all Microsoft Entra ID groups. 

Then search for **Devices** (search mode should be enabled) and select your user device group.

![029-group.png](../../Images/SolutionGuide/W365/02-RDPSettings-Group-1.png)

Next, select **Dynamic Membership Rules** and add a new rule or modify the existing rule to include all devices with the display name that you have configured in the W365 provisioning profile. And then **Save**. 

![030-group.png](../../Images/SolutionGuide/W365/02-RDPSettings-Group-2.png)

Lastly, you need to check that the processing status of the dynamic rule is not "Paused", otherwise you need to change the processing pause value from **Yes to No**.

![030-group.png](../../Images/SolutionGuide/W365/02-RDPSettings-Group-3.png)

## Step 2 - Configure an Intune Device Configuration Profile for the RDP Settings

First open the **Devices** tab and select **Configuration profiles** then **Create profile** to create a new Intune Device Configuration Profile.

![RDPSettings-1.png](../../Images/SolutionGuide/W365/02-RDPSettings-1.png)

Select **Windows 10 and later** as Platform and **Settings catalog** as Profile type and click **Create**.

![RDPSettings-2.png](../../Images/SolutionGuide/W365/02-RDPSettings-2.png)

Enter your configuration profile name **CP-%PUNK%-TEXT**, e.g. CP-P1-RDP-Restrictions and click **Next**.

![RDPSettings-3.png](../../Images/SolutionGuide/W365/02-RDPSettings-3.png)

Click **+ Add settings** to add settings to your configuration profile. 

![RDPSettings-4.png](../../Images/SolutionGuide/W365/02-RDPSettings-4.png)

Next, search for **Remote Desktop** and open the catagory with **...\Device and Resource Redirection** then select **Do no allow Clipboard redirection** and **Do not allow drive redirection**.

After that you can close the settings picker.

![RDPSettings-5.png](../../Images/SolutionGuide/W365/02-RDPSettings-5.png)

On the Configuration Settings tab, you must enable both RDP settings and click **Next**.

![RDPSettings-6.png](../../Images/SolutionGuide/W365/02-RDPSettings-6.png)

The Scope Tags tab can be skipped, but the Assignment tab is important. Here you need to **Add Groups** add your specific Cloud PC device group, e.g. GRP-P1 devices.

Click **Next** and then **Create**.

![RDPSettings-7.png](../../Images/SolutionGuide/W365/02-RDPSettings-7.png)
## Learning Resources
- [Manage RDP Devices](https://learn.microsoft.com/en-us/windows-365/enterprise/manage-rdp-device-redirections)
- [Dynamic membership rules for groups in Azure Active Directory](https://learn.microsoft.com/en-us/azure/active-directory/enterprise-users/groups-dynamic-membership)
- [Create a device profile in Microsoft Intune](https://learn.microsoft.com/en-us/mem/intune/configuration/device-profile-create)