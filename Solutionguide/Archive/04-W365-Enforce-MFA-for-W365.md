# Solutionguide 4: Enforce MFA for Windows365

## Introduction

Conditional Access is the protection of regulated content in a system by requiring certain criteria to be met before granting access to the content. Conditional Access policies at their simplest are if-then statements. If a user wants to access a resource, then they must complete an action.

## Challenge

Create an conditional access policy for **your users** and ensure MFA is enforced when using the Windows 365 Client.

## Success Criteria
1.	A conditional access policy is created
2.  MFA is enforced when accessing Windows365 with the Windows365 Client.

## Step 1 Assign the right license

Assign your users an Azure Active Directory P1 or P2 license that enables the MFA feature with Conditional Access.

Open your AAD tenant and select **Licenses**. If you do not have Enterprise Mobility + Security licenses available, you can activate the time-limited trial. 

Next, select **All Products** and your Enterprise Mobility + Security license, and then click **Assign**. Select the users or your AAD group to whom you want to assign this license, and then activate **Azure Active Directoy Premium P1 or P2**.

![Configure MFA](../Images/SolutionGuide/AVD/09-Assign_License_1.png)

## Step 2 Create a conditional access policy

In this task we will create a conditional access policy to enforce MFA for the AVD client.

You need to be signed in as a **global administrator, security administrator, or conditional access administrator**.

Browse to **Security** within the Azure Active Directory and then to **Security > Conditional Access** 

![Configure MFA](../Images/SolutionGuide/W365/052-ConAccess.png)

within the Azure Portal and create a **new policy**.

![Configure MFA](../Images/SolutionGuide/W365/054-ConAccess.png)

You can target conditional access policies to different users or groups. 

![Configure MFA](../Images/SolutionGuide/W365/055-ConAccess.png)

**Assign the policy to your user group**, do not forget so exclude user accounts or groups you don't want to apply this policy to. 

![Configure MFA](../Images/SolutionGuide/W365/056-ConAccess.png)

Under **cloud apps or actions** choose **include** and then select **apps**. 
Choose the following app: **Windows 365 (App ID ...)**

![Configure MFA](../Images/SolutionGuide/W365/057-ConAccess.png)

Under Access controls select **Grant access**, **Require multi-factor authentication**, and then **Select**.

![Configure MFA](../Images/SolutionGuide/W365/058-ConAccess.png)

Under Access controls go to sessions and select **Sign-in frequency**, set the value to the time you want between prompts (For example, setting the value to 1 and the unit to Hours, will require multifactor authentication if a connection is launched an hour after the last one).

Confirm your settings and turn on **enable policy** before clicking on **create**.

![Configure MFA](../Images/SolutionGuide/W365/059-ConAccess.png)

## Learning Resources
- [Set conditional access](https://learn.microsoft.com/en-us/windows-365/enterprise/set-conditional-access-policies)
- [Setup MFA](https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-mfa)