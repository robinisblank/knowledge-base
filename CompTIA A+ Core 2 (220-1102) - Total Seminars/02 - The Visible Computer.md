# The Visible Computer

## Common Safety Procedures
- ESD mats prevent electrical components from getting damaged by static electricity.
- Disconnect power before repairing to practice proper power handling.
- Consider what tools you need before performing the job.
- Have proper lighting so that each component is properly visible.
- Compliance with government regulations according to the environment in which you are working. For example, wearing safety goggles or an air filtration mask.
- Properly unbox a device and practice proper component handling and storage.
- Don't throw away those manuals.
- Antistatic bag protects a component from static electricity till it's needed.

## What is an Operating System?
- An OS controls all the programs on a computer.
- The core of an OS is the kernel. It handles the primary memory management.
- Running programs are called processes. Each gets a unique Process ID (PID).
- In Windows, you can see these processes in Resource Monitor.
- To meet the growing need for more programs running simultaneously, built into every CPU is an ability to address memory. Some wires are dedicated to talk to the memory. Earlier these wires were 8-bits, then 32-bits for some time, and now 64-bits.
- OSes use device drivers to talk to hardware.
- Every OS has its own device drivers.
- A device driver is an interface between an OS and hardware.
- In Windows, you can see these device drivers in Device Manager.
- Every OS stores programs/data as files and folders.
- Today, OSes combine networking capabilities, and you don't need to install networking as a third-party tool.

## Users and Super Users
- All OSes have user accounts with encoded passwords.
- All OSes have super user accounts that have complete access to everything.
- The Windows super user is called the Administrator.
- The Linux and macOS super user is called Root.
- User Account Control (UAC) prevents usage of powerful programs by users with limited permissions.

## Why Windows?
- Microsoft invented the concept of per-processor agreements. These agreements created a strong user base as they were forced to have Windows when they purchased Intel processors.
- Microsoft did a great job of building networking into their OS.
- In a network, you must have the same username and password on each computer to share and access resources. This is tedious to set up and use.
- Microsoft introduced "Domain". In a network, a computer is dedicated to running Windows Server and is a Domain Controller. This domain controller has a set of usernames and passwords. So, whenever you log in to a computer, you are not logging in locally but into the domain. You don't need to set up the same user accounts on each computer. You only need to set up one domain account.
- Domains are typically managed by Windows Server with Active Directory (AD).
- SSO enables users to log in using their domain accounts anywhere on the network.
- Both OS X and Linux use Windows networking for SSO.
- File Sharing and Printer Sharing (macOS); Samba (Linux).

## Touring Windows 10 and 11
- The hardware requirements have increased with Windows 11. So, if you have an older PC, it's better to use Windows 10.
- Windows 11 requires double the amount of RAM and TPM 2.0.
- Windows 11 features a more refined and sleeker look.
- Widgets are back in Windows 11.
- The new Microsoft Store in Windows 11 enables the installation of Android apps.
- Windows 11 features such as Auto HDR from the Xbox console increase the visual and gaming experience.
- Windows 10 allows local accounts. You don't need a Microsoft-connected services account.
- There are live tiles in Windows 10.
- Get the version of Windows that fits your hardware requirements and has productivity apps and features you need.

## Touring the macOS
- macOS is the OS for Macs, and iPadOS is the OS for iPads.
- macOS has pinned and currently opened apps on the Dock.
- The trash is always pinned at the right of the dock.
- There is a permanent menu bar at the top, and its left side consists of the Apple menu, then the Application menu, and items according to the application.
- The right side of the menu bar is the Status area.
- The dot at the bottom of an icon in the dock represents a running application.
- Universal Control allows you to use a mouse, touch, or keyboard across different Apple devices.
- Mission Control gives a high-level overview of all windows, desktop spaces, and running apps.
- Finder is the equivalent of File Explorer in Windows.

## Touring Linux
- Linux is just the kernel. Along with the kernel, there are desktop interfaces, device drivers, controllers, and many other programs under the GNU (GNU's Not Unix) license.
- The GNU General Public License (GPL) is a free and widely used license that gives users the freedom to use, study, share, and modify software. The GPL is a copyleft license, which means it's protective of the original work and all works derived from it.
- Linux is freeware under the GNU license.
- Linux is commonly packaged in distributions (distros). It is a combination of programs under the GNU license.
- Fedora, Mint, and Ubuntu are three popular distros.
- Fedora has a KDE desktop environment.
- Ubuntu has a GNOME desktop environment.
- Mint has a Cinnamon desktop environment that looks like Windows.