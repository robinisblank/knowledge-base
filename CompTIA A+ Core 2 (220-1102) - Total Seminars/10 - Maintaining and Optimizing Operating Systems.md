# Maintaining and Optimizing Operating Systems

## Maintaining Windows
- Patch management is the process of applying firmware and software updates to improve functionality, close security vulnerabilities and optimize performance.
- Proactive patch management is a crucial aspect of maintaining a healthy system.
- An unpatched system can spell disaster to a network.
- You can manage your updates in Updates & Security in Windows 10, and in Windows Update in Windows 11.
- Delivery Optimization is a cloud-managed solution that reduces bandwidth consumption by allowing Windows devices to download updates from alternate sources like other devices on the network or a cache server, in addition to Internet-based servers.
- Sometimes an OS update might fail and you need to roll back updates.
- OSes that have reached their End-of-Life (EOL) are typically not eligible to receive feature and security updates.

## Maintaining macOS
- macOS upgrade options can be found under System Preferences > Software Update.
- Updating individual applications is done through the App Store > Updates.
- Installing applications is done via the App Store or downloading Apple Disk Image (`.dmg`), Package Installer (`.pkg`), or Application Bundle (`.app`) installation files.
- macOS no longer supports 32-bit.
- An alias is a pointer or reference to a file, folder, or application, allowing you to access it from another location without duplicating the original. It stays linked to the original item even if it's moved or renamed.
- System Preferences > Users & Groups > Login Items control what programs start when you log into a Mac. Check Hide if you don't want any application window to appear.
- Launchpad is a feature on Mac that allows users to view, open, move, and uninstall apps just like in iOS.
- You can force quit apps. Press the option key to change the quit option to force quit option. You can also force quit apps from the Apple menu > Force Quit...

## Maintaining Linux
- Linux can be updated via the GUI or CLI.
- Most distros of Linux utilize rolling repositories/repos that you can connect to and install the latest updates.
- Rolling repos are a series of different trusted sources that host updates.
- You might not be able to install an update until you update your repos.

## Working with Applications
- Alt + Tab in Windows switches between open applications in the Taskbar.
- Windows key + Tab opens the Task view and allows you to switch between open applications and desktops.
- You can also quickly switch desktops without going into the Task View pane by using the Windows Key + Ctrl + Left/Right Arrow.
- The Snap feature in Windows allows you to organize your open windows on your desktop by snapping them into different layouts.
- Press and hold the Windows Key + Arrow to Snap the app you are on.
- User Account Control (UAC) in Windows is a security feature that helps prevent unauthorized changes to your system by requiring administrator approval before certain actions.
- The "Run as administrator" option enables you to run a program as a higher-privileged user. A UAC pop-up displays to ensure you want to do this.
- Troubleshoot applications by uninstalling and reinstalling them. You can uninstall an application either from Control Panel > Programs > Programs and Features (`appwiz.cpl`) or Settings > Apps > Installed apps.
- Before installing any applications, it's important to consider hardware requirements (32-bit vs. 64-bit application, dedicated graphics card vs. integrated, system RAM and VRAM, CPU, Hard drive/storage, etc.) and their impact on your device, network (especially if you have metered connections and limitations), and operation/business.

## Backing Up your Data in Windows
- Backups are imperative to safeguarding your system and data.
- We can avoid having to do a full backup every day because all file systems have features that help us know when a file has been changed.
- The `stat` command in Linux provides information about files and directories. Here we can see the modified date and time.
- The archive attribute in Windows is a file attribute that indicates whether a file has changed since the last backup.
- A differential backup is a backup of all the changes since the last full backup.
- With differential backups, you only need a full backup and a differential backup to restore data. However, backup sets get bigger over time.
- An incremental backup only backs up changes made from the last backup.
- With incremental backups, you need full backup and all incremental backups to restore data. However, backup sets don't get bigger over time.
- First In, First Out (FIFO) is a backup scheme in which the newest files are saved to the oldest media, creating a cycle that overwrites old data with new data.
- Grandfather-Father-Son (GFS) is a backup scheme that uses three backup versions:
	- Grandfather is a full backup of the data that's performed once a year.
	- Father is a full backup of the data that's performed once a month.
	- Son is a full backup of the data that's performed once a week, plus increments daily.
- Testing your backup process frequently helps iron out any issues.
- The 3-2-1 backup rule states that you should have three copies of your backed up data, across two or more media types, and at least one copy of your backup should be hosted off-site, such as in the cloud. Following this rule helps ensure that you always have a complete backup available no matter the reason for the outage.
- SSDs will never have read/write head failure, optical media can survive moisture, and there are many examples to explain why you should keep backup copies in multiple forms of media.
- Consider where you'll host your backup. It could be on-site, off-site, or both.
- All Control Panel Items > Backup and Restore (Windows 7) is a legacy tool for restoring backups that were made using the tool in Windows 7. You can also use it to create backups in Windows 11, but newer alternatives like File History and OneDrive are recommended.
- Windows has moved towards their own hybrid backup method and we can no longer have control over choosing the backup method.

## Backing Up your Data in Linux and macOS
- There are many ways to backup your data in Linux via the GUI or CLI.
- System Preferences > Time Machine is a built-in feature on Mac that automatically backs up your files to an external storage device.
- Set backups to run automatically as a best practice.
- Remember to perform the necessary backups before making any system changes.