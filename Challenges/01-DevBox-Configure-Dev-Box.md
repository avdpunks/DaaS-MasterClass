# Challenege 1: Configure Microsoft Dev Box

## Introduction

Microsoft Dev Box gives developers self-service access to ready-to-code cloud workstations called dev boxes. You can configure dev boxes with tools, source code, and prebuilt binaries that are specific to a project, so developers can immediately start work. You can create your own customized image, or use a preconfigured image from Azure Marketplace, complete with Visual Studio already installed.

If you're a developer, you can use multiple dev boxes in your day-to-day workflows. You can access your dev boxes through a remote desktop client, or through a web browser, like any virtual desktop.

## Challenge

You have some developers in your company, and they need developer machines, sometimes just for some hours to review and commit code.

To set up your Azure Dev Center to provide Dev Boxes to your developers, you need to do the following:

- Create a dev center 
- Create **two dev box definition** with the following specs:
    - Windows 11 Enterprise 23h2
    - Visual Studio 2022 Enterprise and Microsoft 365 are pre-installed
    - 8 vCPU, 32 GB RAM and 16 vCPU, 64 GB RAN
    - 256 GB disk storage
- Create for each definition a dev box pools with Microsoft hosted network, Local Administrator rights and Auto-stop at 7:00pm
- Assign the project to your user group
- Dev box limit is set to 2

## Success Criteria
1. Two dev box size options are available in the Microsoft developer portal. 
2. Your User has local admin rights.
3. A dev box deployment is running.

## Learning Resources
- [What is Microsoft Dev Box?](https://learn.microsoft.com/en-us/azure/dev-box/overview-what-is-microsoft-dev-box)
- [Quickstart: Configure Microsoft Dev Box](https://learn.microsoft.com/en-us/azure/dev-box/quickstart-configure-dev-box-service)
- [Use a remote desktop client to connect to a dev box](https://learn.microsoft.com/en-us/azure/dev-box/tutorial-connect-to-dev-box-with-remote-desktop-app?tabs=windows)