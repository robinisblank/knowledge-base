# Working with Operating Systems

## The Task Manager
- Task Manager is a utility program that comes with the Windows OS that helps users monitor and manage the applications and processes running on their computer.
- Services are tasks handled by Windows and needed for the OS to function.
- Processes are programs or applications that a user initiates or runs.
- Users are the individual accounts with access to a specific file, folder, logon, or application.
- The Processes tab lists all running processes and applications, along with their resource usage. You can also end or prioritize processes.
- The Performance tab provides real-time information about your computer's CPU, memory, disk, and network usage. This tab also shows if your system is short on memory or the processor is spiking.
- The App History tab displays resource usage information for specific Windows Store apps.
- The Startup tab lists the applications and processes that are configured to launch when your computer starts.
- The Users tab shows the active user sessions on your computer. You can send messages to users, disconnect users, or log users off from this tab.
- The Details tab provides more detailed information about each process, including its full name, PID (Process Identifier), and the username under which the process is running.
- The Services tab displays information about system services that are currently running on your computer. You can also start and stop services from this tab.

## The Control Panel
- The Windows Control Panel enables access to common configurations and tools in a centralized area.
- Applets are the sections accessed via shortcuts within the Control Panel.
- Administrative Tools in Windows 10 is called Windows Tools in Windows 11.
- Many applets within the Windows Control Panel have corresponding run files with the `.cpl` extension that you can use to access the tools directly.
- God Mode gives you access to a centralized control panel with all the system's settings in one place by listing them in one comprehensive list, making it easy to manage everything from administrative tools to accessibility settings.
- Enable God Mode by creating a folder on your Windows desktop with `God Mode.{ED7BA470-8E54-465E-825C-99712043E01C}` as its filename.

| CPL Filename   | Purpose                                                  |
| -------------- | -------------------------------------------------------- |
| `Access.cpl`   | Accessibility properties                                 |
| `Appwiz.cpl`   | Add/Remove Programs properties                           |
| `Desk.cpl`     | Display properties                                       |
| `FindFast.cpl` | FindFast (included with Microsoft Office for Windows 95) |
| `Inetcpl.cpl`  | Internet properties                                      |
| `Intl.cpl`     | Regional Settings properties                             |
| `Joy.cpl`      | Joystick properties                                      |
| `Main.cpl`     | Mouse, Fonts, Keyboard, and Printers properties          |
| `Mlcfg32.cpl`  | Microsoft Exchange or Windows Messaging properties       |
| `Mmsys.cpl`    | Multimedia properties                                    |
| `Modem.cpl`    | Modem properties                                         |
| `Netcpl.cpl`   | Network properties                                       |
| `Odbccp32.cpl` | Data Sources (32-bit ODBC, included w/ Microsoft Office) |
| `Password.cpl` | Password properties                                      |
| `Sticpl.cpl`   | Scanners and Cameras properties                          |
| `Sysadm.cpl`   | System properties and Add New Hardware wizard            |
| `Themes.cpl`   | Desktop Themes                                           |
| `TimeDate.cpl` | Date/Time properties                                     |
| `Wgpocpl.cpl`  | Microsoft Mail Post Office                               |

## Windows Settings
- Windows Settings includes many options for configuring your OS.
- Windows Settings in Windows 10 vs. 11 are similar, and only a few names and interfaces have changed.
- Privacy in Windows 10 has changed to Privacy & security in Windows 11, and Update & Security in Windows 10 has changed to Windows Update in Windows 11.

## MMC and Additional Tools
- Windows key + R opens the Run dialog box to quickly execute commands or launch programs.
- The Microsoft Management Console (MMC) offers a framework in which multiple administrative tools can be added to a single management interface. It enables you to create custom toolsets for administering your machine efficiently.
- Access MMC by searching for "mmc".
- Snap-ins are tool shortcuts added within the MMC.
- Customized MMC setups can be saved for quick access.
- The "Safe boot" option ("minimal" by default) in the Boot tab in System Configuration makes the system load only the things necessary for Windows to function when it boots, making it easier to troubleshoot any additional hardware/software that we have installed that is causing problems.

| Command/File   | Tool Name              |
| -------------- | ---------------------- |
| `msinfo32.exe` | System Information     |
| `resmon.exe`   | Resource Monitor       |
| `msconfig.exe` | System Configuration   |
| `diskmgmt.msc` | Disk Management        |
| `devmgmt.msc`  | Device Manager         |
| `certmgr.msc`  | Certificate Manager    |
| `lusrmgr.msc`  | Local Users and Groups |
| `perfmon.msc`  | Performance Monitor    |
| `gpedit.msc`   | Group Policy Editor    |
| `taskschd.msc` | Task Scheduler         |
| `regedit.exe`  | Registry Editor        |

## What is the Registry?
- The Registry is a database that stores Windows settings. Whenever you are making changes in the Control Panel, Settings, or other system configuration tools, you are basically editing the registry.
- `C:\Windows\System32\config` is where the registry files reside.
- The Registry Editor (`regedit.exe`) is a tool to manually edit the Registry.
- The Registry has five root keys into which all data is organized.
- HKEY_CLASSES_ROOT (HKCR) contains information about file associations and OLE (Object Linking and Embedding) objects. It helps Windows know which application to use when opening a specific file type.
- HKEY_CURRENT_USER (HKCU) stores configuration settings for the currently logged-in user. This includes user-specific settings like desktop preferences, keyboard layout, and application preferences.
- HKEY_LOCAL_MACHINE (HKLM) contains configuration settings that apply to the entire computer, regardless of which user is logged in. It holds system-wide hardware and software settings.
- HKEY_USERS (HKU) stores settings for all users on the computer. Each user has a subkey under HKU, and HKCU is actually a link to the currently active user’s settings in HKU.
- HKEY_CURRENT_CONFIG (HKCC) holds information about the current hardware profile used at system startup. It stores settings related to the current hardware configuration, such as display and printer settings.
- The Export feature creates a backup of registry keys as a `.reg` file, and the Merge feature imports settings from a `.reg` file into the registry. This is useful for saving a snapshot of the current configuration before making changes or for transferring settings between computers.

## macOS Core Tools
- Most of the main system settings can be found under System Preferences. You'll find it in the Apple menu.
- Every item in System Preferences is called Settings Pane.
- Security & Privacy includes many tools to secure your macOS device.
- Apple ID enables syncing with things such as Photos, iCloud Mail, Calendar, Contacts, etc.
- Apple Business Manager (ABM) is a web-based portal that works with a third-party Mobile Device Management (MDM) solution to help IT administrators manage Apple devices and content.
- Command + Space opens Spotlight. You can search for anything and can even use this as a calculator.
- Keychain Access allows users to view and manage certificates, keys, and other information stored in a keychain. It also works with iCloud Keychain to share keychains with other Apple devices.
- FileVault is a built-in security feature on Mac computers that encrypts data to protect it from unauthorized access or copying.
- You'll find utilities under the Go menu.
- The Console is a utility that collects and displays log messages from your computer and connected devices.
- Activity Monitor is a utility that provides information about your Mac's processes, including how much CPU time and memory they are using.