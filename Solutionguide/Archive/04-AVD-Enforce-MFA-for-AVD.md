# Solutionguide 4: Enforce MFA for AVD

## Introduction
The Windows client for Azure Virtual Desktop is an excellent option for integrating Azure Virtual Desktop with your local machine. 

However, when you configure your Azure Virtual Desktop account into the Windows Client, there are certain measures you'll need to take to keep yourself and your users safe.
Multi Factor Authentication or MFA and conditional access enables you to add an additional layer of security.

Conditional Access is the protection of regulated content in a system by requiring certain criteria to be met before granting access to the content. Conditional Access policies at their simplest are if-then statements. If a user wants to access a resource, then they must complete an action.

## Challenge

Create an conditional access policy for **your users** and ensure MFA is enforced when using the AVD (Remote Desktop) Client.

## Success Criteria
1.	A conditional access policy is created
2.  MFA is enforced when accessing Azure Virtual Desktop with the ADV (Remote Desktop) Client.


## Step 1 - Assign Azure Active Directory P1 or P1 license

Assign your users an Azure Active Directory P1 or P2 license that enables the MFA feature with Conditional Access.

Open your AAD tenant and select **Licenses**. If you do not have Enterprise Mobility + Security licenses available, you can activate the time-limited trial. 

Next, select **All Products** and your Enterprise Mobility + Security license, and then click **Assign**. Select the users or your AAD group to whom you want to assign this license, and then activate **Azure Active Directoy Premium P1 or P2**.

![Configure MFA](../Images/SolutionGuide/AVD/09-Assign_License_1.png)

## Step 2 - Create a Conditional Access policy
In this task we will create a Conditional Access policy to enforce MFA for the AVD client.

You need to be signed in as a **global administrator, security administrator, or conditional access administrator**.

In Azure Active Directory **create a group and add your AVD users** to that group.

Now browse to Security within the Azure Active Directory and then to **Security > Conditional Access** within the Azure Portal and create a **new policy**.

![Configure MFA](../Images/SolutionGuide/AVD/09-Create_CA_Policy_1.png)

**Assign the policy to your user group** and click **Done**.

Under **cloud apps or actions** choose **include** and then select **apps**. 
Choose the following app: **Azure Virtual Desktop (App ID 9cdead84-a844-4324-93f2-b2e6bb768d07)**

![Configure MFA](../Images/SolutionGuide/AVD/09-Create_CA_Policy_2.png)

Go to Conditions and then to the configure section in **client apps** and choose **yes** where you want to apply the policy (browser and/or mobile apps and desktop clients).

![Configure MFA](../Images/SolutionGuide/AVD/09-Create_CA_Policy_3.png)

Under Access controls select **Grant access**, **Require multi-factor authentication**, and then **Select**.

![Configure MFA](../Images/SolutionGuide/AVD/09-Create_CA_Policy_4.png)

Under Access controls go to sessions and select **Sign-in frequency**, set the value to the time you want between prompts (For example, setting the value to 1 and the unit to Hours, will require multifactor authentication if a connection is launched an hour after the last one).

Confirm your settings and turn on **enable policy** before clicking on create.

## Learning Resources
- [Set conditional access](https://learn.microsoft.com/en-us/windows-365/enterprise/set-conditional-access-policies)
- [Setup MFA](https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-mfa)
