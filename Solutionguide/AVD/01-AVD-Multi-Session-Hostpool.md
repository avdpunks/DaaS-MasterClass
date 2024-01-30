# Solutionguide 1: Create a host pool for multi-session

In this challenge you will create Azure AD joined pooled desktops from a Microsoft Windows 11 Multi-Session Gallery Image. After the deployment you will connect to this session host with the native or web Remote Desktop client. 

## Challenge

Create multi-session hostpool joined in Azure Active Directory
- West Europe Region
- Metadata located in West Europe
- Mark as Validation environment
- Host Pool type: Pooled
- Choose Windows 11 Enterprise multi-session Version + Microsoft 365 Apps Gallery image  
- Domain to join: Azure Active Directory (Enroll with Intune “Yes”)
- Register desktop app group to new workspace
- Assign users

Login to the session host
- Log in as a user and verify that the operating system is a multi-session build

Deploy Microsoft Word and Excel (or whatever) as Remote App

## Success Criteria
1.	Host Pools are created and Session Hosts are showing available
2.	Users are assigned to the appropriate application group of the host pool
3.	Able to show the Host Pool settings configured
4.	VMs are joined to Azure AD
5.  Users can sign in to the VM
6.  Office Apps can be accessed via RemoteApp

## Step 1 - Create a new Pooled Host Pool and Workspace

1.  Sign in to the [Azure Portal](https://portal.azure.com/).

2.  Search for **Azure Virtual Desktop** and select it from the list.

3.  Under Manage, select **Host pools** and select **+ Create**.
   
![This image shows where to select host pools under manage and select add to add a new host pool.](../../Images/SolutionGuide/AVD/01-avdHostPool.png "Azure Virtual Desktop blade")

4.  On the Basics page, refer to the following screenshot to fill in the required fields. Select your Subscription, Resource Group and define a Hostpool name. As Location choose **West Europe**. 

> **Info:** This will only effect metadata. The Datacenter location for virtual machines will follow. 

Change **Validation environment** to **Yes**.
Once complete, select **Next: Virtual Machines**.

![This image shows where you will enter the information for the host pool.](../../Images/SolutionGuide/AVD/02-Hostpool_create_multisession_2.png "Create pooled host pool page")

5. Navigate to **Virtual Machines** at the top and select **Show All Images** to find your recently created image. 

![Create Image](../../Images/SolutionGuide/AVD/02-Hostpool_create_sessionhosts_2.png)

6. Next, go to **My Items** then select **Shared Images** and click on your recently created image.

![Create Image](../../Images/SolutionGuide/AVD/02-Hostpool_create_sessionhosts_3.png)

7. Now your recently created image should be displayed as an image parameter. Click **Next: Workspace**.

![Create Image](../../Images/SolutionGuide/AVD/02-Hostpool_create_sessionhosts_4.png)
     ![This image shows the image that you need for your host pool virtual machine.](../../Images/SolutionGuide/AVD/01-vmwith365_3.png "Host pool Virtual Machine with image")
 
8.  On the Workspace page, select **Yes** to register a new desktop app group. Select **Create new** and provide a **Workspace name**. Select **OK** and **Review + create**.

   ![This image shows how from the create a host pool workspace tab, enter the required information.](../../Images/SolutionGuide/AVD/02-hostpoolWorkspace.png "Create a host pool workspace tab")

9.  On the Create a host pool page, select **Create**.

> **Note**: If you are trying to access your virtual desktop from Windows devices or other devices that are not connected to Azure AD, add **targetisaadjoined:i:1** as a custom RDP property to the host pool. [More information here](https://learn.microsoft.com/en-us/azure/virtual-desktop/deploy-azure-ad-joined-vm#access-azure-ad-joined-vms)


## Step 2 - Assign user access to host pool

After you've created your host pool, you must assign users access to the desktop application group. We recommend that you use user groups instead of individual users wherever possible. As you already assigned the Virtual Machine User Login or Virtual Machine Administrator Login permissions in Challenge 1 on the resource group level, this task is not necessary here anymore. If you didn´t do it yet, or if you use another resource group, go ahead and assign these roles to the users who should be able to login to the pooled desktops.

1. Assign your users or groups to the **HP-PooledVMs-DAG** desktop application group.

2. Assign your users the **Virtual Machine User Login** role so they can sign in to the VMs.

3. **optional** Assign administrators who need local administrative privileges the Virtual Machine Administrator Login role.
To grant users access to Azure AD-joined VMs, you must [configure role assignments for the VM](https://docs.microsoft.com/en-us/azure/active-directory/devices/howto-vm-sign-in-azure-ad-windows#configure-role-assignments-for-the-vm). 


## Step 3 - Create Remote Apps

To make only a single application available to the user, instead of the full desktop, so that only the application is rendered on your host device from which you are currently working from, you need to create a remote application group. Follow the guidance:

1. Navigate to the Azure Virtual Desktop and select **Application Groups** and click **Create**.

![Create Image](../../Images/SolutionGuide/AVD/02-Hostpool_RemoteApp-1.png)

![Create Image](../../Images/SolutionGuide/AVD/02-Hostpool_RemoteApp-2.png)

Create a new Application group
- **Select your Resource group**
- **Select your multi-session AVD Host pool**
- Application group type: **Remote App (RAIL)**
- Application group name: **HP-PooledVMs-RAG**
- click **Next: Applications**

2. Click on **Add applications**

![Create Image](../../Images/SolutionGuide/AVD/03-Hostpool_RemoteApp-1.png)

Select:
- Application source: **Start Menu**
- Application: **Visual Studio Code**

![Create Image](../../Images/SolutionGuide/AVD/03-Hostpool_RemoteApp-4.png)

- Click on **Save** and add another application.

Select:
- Application source: **Filepath**

> **Note**: The reason why you can´t use the start menu as **Application Source** this time is because the "++" is interpreted by the AVD agent and the application is therefore not found. But if we use the **File path** option it works.

- Application path: **C:\Program Files\Notepad++\notepad++.exe**
- Application name: **NotepadPP** 
- Icon Path: **C:\Program Files\Notepad++\notepad++.exe**
- Icon Index: 0

![Create Image](../../Images/SolutionGuide/AVD/03-Hostpool_RemoteApp-3.png)


- Click on **Save** and **Next: Assignments**

3. Assign the AVDUsers group to the Application group which should have access to the Notepad++ RemoteApp.

![Create Image](../../Images/SolutionGuide/AVD/03-Hostpool_RemoteApp-2.png)

Click **Next: Workspace**

4. Toggle **Register Application Group** to yes and click **Review + create**.

![Create Image](../../Images/SolutionGuide/AVD/02-Hostpool_RemoteApp-2-1.png)

> If another application group in the AVD host pool has already been registered then this app group will also be registered to that same workspace.

Next, start your Remote Desktop Client App, refresh the AVD Workspace and launch the Notepad++ application.

> **Note**: If you are trying to access your virtual desktop from Windows devices or other devices that are not connected to Azure AD, add **targetisaadjoined:i:1** as a custom RDP property to the host pool. [More information here](https://learn.microsoft.com/en-us/azure/virtual-desktop/deploy-azure-ad-joined-vm#access-azure-ad-joined-vms)


## Learning Resources
- [Create Azure Virtual Desktop Hostpool](https://learn.microsoft.com/en-us/azure/virtual-desktop/create-host-pools-azure-marketplace)
- [Manage app groups for Azure Virtual Desktop portal](https://learn.microsoft.com/en-us/azure/virtual-desktop/manage-app-groups)
- [Connect to Azure Virtual Desktop with the Remote Desktop client for Windows](https://learn.microsoft.com/en-us/azure/virtual-desktop/users/connect-windows?tabs=subscribe#install-the-windows-desktop-client)
