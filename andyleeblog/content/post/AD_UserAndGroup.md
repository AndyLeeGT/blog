+++
date = "2024-03-01"
title = "Active Directory: Group and ShareFolder"
slug = "Active Directory: Group and ShareFolder"
categories = [ "Post"]
tags = [ "Active Directory", "Users and Computers"]
katex = true
+++

Welcome back to the post again! In this post, we will talk about creating and adding group members, and explore the shared folder features.


# Adding New Group

One powerful method for organizing the users is by incorporating Group Organizational Units (OUs). 
These OUs offer a structured approach to managing groups within your network, providing enhanced organization and control over permissions and policies.

To get started, follow these steps below:

1. Access Active Directory Users and Computers: Launch the Active Directory Users and Computers (ADUC) console. This can be found in the Administrative Tools section of your Windows Server or under the Tools bar in server manager application.

2. Navigate to the Domain: Expand the domain node within the ADUC console to access the organizational unit where you want to create the new group OU.

3. Create a New Organizational Unit: Right-click on the domain or an existing OU where you want to add the new group OU. From the context menu, select "New" and then "Organizational Unit."

4. Name the OU: Give your new OU a descriptive name that reflects the purpose or function of the groups it will contain. This will help you and others quickly identify its role within the directory structure.
    1. IMAGE: `Group OU setup`
![alt](/img/homeLab/RoleAndFeature/OUSetup.PNG)

5. Configure OU Properties (Optional): Depending on your requirements, you may want to configure additional properties for the OU, such as specifying group policies, delegating administrative permissions, or setting replication options.

6. Manage Group Membership: With your new group OU in place, you can now begin adding groups to it. This can be done by creating new groups directly within the OU or by moving existing groups into it using drag-and-drop or cut-and-paste operations.

    2. IMAGE: `group properties window for chaning group properties`
    ![alt](/img/homeLab/RoleAndFeature/NewGroup.PNG)
    3. IMAGE: `group properties window of Group members successfully added`
    ![alt](/img/homeLab/RoleAndFeature/AddGroupMemeber.PNG)
    4. IMAGE: `Pop-up window of Group members successfully added`
    ![alt](/img/homeLab/RoleAndFeature/NewGroupWithMembers.PNG)

By leveraging Group OUs in Active Directory, you can simplify group management, improve security, and ensure better organization within your network environment. Take the time to plan your OU structure carefully, considering factors such as departmental divisions, security boundaries, and administrative responsibilities.

# ShareFolder

Setting up shared folders in Windows Active Directory is essential for efficient file management and collaboration within a networked environment. administrator can add shareFolder functionality within domain network so that user can create shared folders that allow users to access, share, and collaborate on files. In this blog post, we'll walk through the process of creating shared folders in Windows Active Directory.

1. Accessing Active Directory Management Console: Launch the ADUC console.T his can be found in the Administrative Tools section of your Windows Server or under the Tools bar in server manager application.

2. Navigating to the Desired Organizational Unit (OU): In the Active Directory Management Console, expand the domain node to view the organizational units (OUs) within your domain.Navigate to the OU where you want to create the shared folder by clicking on it to select it.

3. Creating a New Shared Folder: Right-click on the selected OU will open up context menu. From the context menu, choose "New" and then select "Shared Folder". Enter the name for your shared folder in the "Name" field. Optionally, you can specify the path for the shared folder permissions in the "Permission Level" field.Click "OK" to create the shared folder.

    1. IMAGE: `Sharefolder property window`
    ![alt](/img/homeLab/RoleAndFeature/ShareFolder.PNG)

4. Setting Permissions for the Shared Folder: It is essential to set up permission levels when configuring the shared folder. You will have two options: Read and Read/Write. These are straightforward steps but are highly important as they are related to the security properties.
    1. IMAGE: `Sharefolder permission setup`
    ![alt](/img/homeLab/RoleAndFeature/ShareFolderToDomainUser.PNG)

5. Accessing the Shared Folder: Once the shared folder is created and permissions are set, users can access it from their computers.
Users can navigate to the shared folder by entering its network path in File Explorer (e.g., \servername\sharedfolder). In our example, the path is `\\DC\SharedFolder`
    1. IMAGE: `finishing up the Share Folder setup`
    ![alt](/img/homeLab/RoleAndFeature/SharedFolderFinish.PNG)

    2. IMAGE: `ShareFolder Access`
    ![alt](/img/homeLab/RoleAndFeature/ShareFolderinDC.PNG)

Creating shared folders in Windows Active Directory is a straightforward process that enhances collaboration and file management within a networked environment. 
you can create shared folders with ease, empowering users to access and share files with window server 2019
Incorporate shared folders into your Active Directory infrastructure to streamline workflow and enhance productivity across your organization.





