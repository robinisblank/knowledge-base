# Users, Groups, and Permissions

## Introduction to Users and Groups
- Windows combined with NTFS gives tremendous control over resources.
- A group is a container for user accounts. You can also have groups within groups.
- NTFS permissions (Full control, Modify, Read, Write, etc.) are assigned to groups instead of individual user accounts for easy administration.
- A user can be a member of multiple groups. That user will have cumulative permissions if multiple groups have the same resource.

## Managing Users and Groups
- Settings, Control Panel, and Local Users and Groups all directly or indirectly enable creating user accounts.
- Accounts in Settings and User Accounts in the Control Panel don't offer many features and account control. It only has two account types: Administrator and Standard.
- Local Users and Groups (`lusrmgr.msc`) provides the most control over users and groups.
- An administrator account is a member of the Administrators group. They have complete control over the PC. They can change any settings and access all files and programs stored on the PC.
- A standard account is a member of the Users group. They can use most software and change system settings that don't affect other users or the security of the PC.
- Power Users are just below Administrators. They can do everything, but cannot take control over other account's stuff.
- Groups like Backup Operators, Performance Log Users, or Performance Monitor Users are for programs and not for people.

## NTFS Permissions
- All files and folders on an NTFS formatted drive have NTFS permissions.
- You'll find NTFS permissions under the Security tab in the Properties of that file/folder.
- NTFS Permissions Attributes for a Folder:
	- **Full Control**: Enables you to do anything you want.
	- **Modify**: Enables you to read, write, and delete both files and subfolders.
	- **Read and Execute**: Enables you to see the contents of the folder and any subfolders as well as run any executable programs or associations in the folder.
	- **List Folder Contents**: Enables you to see the contents of the folder and any subfolders.
	- **Read**: Enables you to view a folder's contents and open any file in the folder.
	- **Write**: Enables you to write files and create new files and folders.
- NTFS Permissions Attributes for a File:
	- **Full Control**: Enables you to do anything you want to do with the file.
	- **Modify**: Enables you to read, write, and delete the file.
	- **Read and Execute**: Enables you to open and run the file.
	- **Read**: Enables you to view a folder's contents and open any file in the folder.
	- **Write**: Enables you to open and write to the file.
- Inheritance is when a subfolder or file gets the permissions of the folder in which it was created.
- Deny enables explicit permissions to stop inheritance.
- NTFS permissions are tied to user accounts and security principals (like users or groups). They are enforced at the filesystem level and don't directly care whether you're logged in locally, remotely, or virtually. They are applied based on the SID (Security Identifier) of the user or group accessing the file or folder.

## Linux and macOS Permissions
- Linux and macOS permissions use the owner, group, and others.
- The owner is the user who created the file/directory by default.
- The others (everyone) refers to all users on the system who are not the owner or in the group associated with the file or directory.
- Each of these three can have read (R), write (W), or execute (X) permissions.
- These are assigned by changing the file or folder properties.
- The administrator does not receive default permissions for newly created files unless they are the ones that created the file.

## File Explorer
- File Explorer is the primary tool for folder and file manipulation in Windows.
- You can turn on/off the navigation pane, details pane, and preview pane.
- The Quick Access entry within the Navigation pane shows pinned and frequently used files and folders.
- You can access the system information by opening properties of This PC.
- This PC shows any installed and mapped drives.
- In Folder Options, under the View tab, you can "Show hidden files, folders, or drives".
- You can set/unset attributes (read-only or hidden) to a file.
- To set/unset attributes to a file, open its properties, then under the General tab you'll find Attributes settings.
- File association refers to the program used to open that particular type of file.
- To change the file association of a file, open its properties, then under the General tab you'll find a change button next to the Opens with settings.

## Sharing Resources
- Windows networking has both NTFS and share permissions.
- Network Share is used for sharing resources. It doesn't care about the file system.
- Resources are first offered for sharing, and then users can do things with that resource according to permissions they have.
- Shared resources use the Universal Naming Convention (UNC). If the network path is `C:\Docs`, then the UNC can be `\\RobinPC\DocsC`. So in general `\\server\share`.
- To open Network access of a resource, right-click> Give access to > Specific people...
- Share permissions are not as granular and powerful as NTFS permissions.
- Microsoft best practices recommend sharing resources with everyone with read/write permission level, not using share permissions, and instead use NTFS permissions.
- When sharing resources via workgroups, remember each computer has its own login information.
- Shared resources can be mapped to a drive letter. Right-click > Map network drive...

## Security Policies
- Security policies define a broad spectrum of security features.
- We use the Local Security Policy application to manage policies.
- Local Security Policy sets policies for a single computer.
- Account Policies enable login and password rules.
- Under Account Policies > Password Policy, the "Enforce password history" policy setting controls the number of unique passwords a user must create before they can reuse an old password.
- Under Account Policies > Account Lockout Policy, the "Reset account lockout counter after" policy setting determines the number of minutes that must elapse from the time a user fails to sign in before the failed sign-in attempt counter is reset to 0.
- Domain policies override local policies. If your computer is part of a domain, and you can't modify something on local security policy, that's because your domain administrators have implemented group/domain policies that override local policies.