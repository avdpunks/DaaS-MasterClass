# Challenege 4: Enforce MFA for AVD

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

## Learning Resources
- [Set conditional access](https://learn.microsoft.com/en-us/windows-365/enterprise/set-conditional-access-policies)
- [Setup MFA](https://learn.microsoft.com/en-us/azure/virtual-desktop/set-up-mfa)