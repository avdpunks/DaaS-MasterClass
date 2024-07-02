# Challenge 2: Configure RDP Properties

[Previous Challenge](./01-AVD-Multi-Session-Hostpool.md) - **[Home](../../readme.md)** - [Next Challenge](./03-AVD-FSLogix.md)

## Introduction

Azure Virtual Desktop enables you to configure and customize Remote Desktop Protocol (RDP) properties for a host pool. 

Customizing a host pool's Remote Desktop Protocol (RDP) properties, such as multi-monitor experience and audio redirection, lets you deliver an optimal experience for your users based on their needs. 

If you'd like to change the default RDP file properties, you can customize RDP properties in Azure Virtual Desktop by either using the Azure portal or by using the -CustomRdpProperty parameter in the Update-AzWvdHostPool cmdlet.

## Challenge 

- Pooled (Desktop / Remote App) Host pool 
    - Allow Multiple Displays
    - Smart Sizing should be enabled
    - Deny Camera and Microphone  
    - Deny Copy&Paste, Storage, networkdrive and printer redirection

## Success Criteria

- You can not access local or networkdrives redirected from the session host
- You can not Copy and Paste from you local devices to the desktop or remote app

## Learning Resources
- [Customize RDP Properties](https://learn.microsoft.com/en-us/azure/virtual-desktop/customize-rdp-properties)
- [Supported RDP Properties](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/clients/rdp-files)
