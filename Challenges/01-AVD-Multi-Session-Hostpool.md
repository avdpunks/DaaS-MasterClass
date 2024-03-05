# Challenege 1: Create a host pool for multi-session

## Introduction

In this challenge you will create Microsoft Entra ID joined pooled desktops from a Microsoft Windows 11 Multi-Session Gallery Image. After the deployment you will connect to this session host with the native or web Remote Desktop client. 

## Challenge

Create multi-session hostpool joined in Azure Active Directory
- North Europe Region
- Metadata located in North Europe
- Mark as Validation environment
- Host Pool type: Pooled
- Choose Windows 11 Enterprise multi-session Version + Microsoft 365 Apps Gallery image  
- Domain to join: Microsoft Entra ID (Enroll with Intune “Yes”)
- Register desktop app group to new workspace
- Assign users

Login to the session host
- Log in as a user and verify that the operating system is a multi-session build

Create new Remote Apps
- Deploy Microsoft Edge and Word (or whatever) as Remote Apps

## Success Criteria
1.	Host Pools are created and Session Hosts are showing available
2.	Users are assigned to the appropriate application group of the host pool
3.	Able to show the Host Pool settings configured
4.	VMs are joined to Microsoft Entra ID
5.  Users can sign in to the VM
6.  Office Apps can be accessed via RemoteApp

## Learning Resources
- [Create Azure Virtual Desktop Hostpool](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace)
- [Manage app groups for Azure Virtual Desktop portal](https://learn.microsoft.com/en-us/azure/virtual-desktop/manage-app-groups)
- [Connect to Azure Virtual Desktop with the Remote Desktop client for Windows](https://learn.microsoft.com/en-us/azure/virtual-desktop/users/connect-windows?tabs=subscribe#install-the-windows-desktop-client)
