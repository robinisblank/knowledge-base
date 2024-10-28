# Troubleshooting Operating Systems

## Windows Recovery Environment
- Windows Pre-installation Environment (WinPE) is a lightweight OS used for deploying, troubleshooting, and recovering Windows installations.
- Windows Recovery Environment (WinRE) is a set of recovery tools based on WinPE that is specifically designed for troubleshooting and repairing existing Windows installations.
- Click "Repair your computer" in WinPE to access the WinRE options.
- The "Troubleshoot" option in WinRE offers advanced options, such as System Restore, Uninstall Updates, System Image Recovery, Startup Repair, and Command Prompt, to fix boot issues or restore the system to a previous state.
- [WinRE Reference](https://learn.microsoft.com/en-us/windows-hardware/manufacture/desktop/windows-recovery-environment--windows-re--technical-reference)
- Microsoft recommends Windows 10 users to avoid relying on the built-in Windows System Image Backup feature, as it has been deprecated. Instead, they encourage users to explore third-party backup solutions like Macrium Reflect 8 Free Edition or EaseUS Todo Backup Free.
- Windows System Image Backup and Recovery Drive are different concepts. A System Image Backup is a complete copy of your system (the entire disk). However, a Recovery Drive is a tool to repair or reset your system, not a full backup of everything.

## Advanced Windows Startup Options
- To get to Safe Mode options in Windows 10/11, check the "Safe boot" option ("minimal" by default) in the Boot tab in System Configuration (`msconfig.exe`).
- [Configure Windows Startup Options](https://support.microsoft.com/en-us/windows/windows-startup-settings-1af6ec8c-4d4a-4b23-adb7-e76eef0b847f)

## Troubleshooting Boot Problems
- Windows OS problems can be grouped into three categories:
	1. Boot problems (computer has booted up but can't find Windows or the Windows is so messed up that it can't even start).
	2. Windows never loads to a desktop (you can't even log into the system).
	3. Bizarre things happen at the desktop level (you can log into the system, but bizarre things happen, like error screens popping up, computer freezing, or the Blue Screen of Death (BSoD)).
- If you face a black screen, first check if your computer is actually turned on.
- A black screen on a booted computer often indicates a video driver problem.
- Get to the Safe Mode and try Roll Back Driver or Update Driver in Device Manager. You'll find these options under the Driver tab in a driver's Properties.
- Be aware of your driver versions. Many websites cover such information. Just like OS patches can be bad, we have the same problem with device drivers. If you know such information, you can recognize a bad driver version in Safe Mode.
- Check the Events tab in a driver's Properties or click the "View All Events..." option to open the Event Viewer for more detailed information. Look for the last log after which things went wrong.
- Issues like Windows not booting up or OS not being found are usually due to incorrect boot order settings or external devices affecting the boot sequence.
- If you face a black screen or any major failure after installing new hardware, undo your actions and see if your system works properly. This will help you zero in on the hardware that is causing issues.
- Any problem you face has already happened to many people before you. You are just one search away from finding the solution.
- If your Windows becomes corrupted or encounters issues, you can use WinRE to fix them. You can either restore your system to a previous point when it was functioning properly or use Windows installation media to perform a repair installation.

## Troubleshooting at the GUI
- You can try rebooting to troubleshoot pretty much any issue.
- If Windows never loads to a desktop, the OS is fine, and the problem lies with the startup.
- When you encounter a startup problem, try rebooting at least three times. If it doesn't fix the problem, Windows will boot into WinRE, and from there you can access Advanced Windows Startup Options by selecting "See advanced repair options" > Troubleshoot > Advanced options > Startup Settings > Restart.
- Check Windows Logs > System in Event Viewer in Safe Mode.
- Sometimes, Windows is fine, but it's incredibly slow. You might have application issues or insufficient RAM.
- Use Autoruns from [Sysinternals](https://learn.microsoft.com/en-in/sysinternals/) by Mark Russinovich to see which programs are configured to run automatically during system boot or login.
- A corrupted profile is when you can access the login screen but not the desktop.
- Create a new user account and copy the old profile to try to recover from the corrupted profile.
- [NeoSmart](https://neosmart.net/) is a great website for fixes and repairs.

## Troubleshooting Applications
- If Windows has booted properly, you've logged in and are at the desktop, and bizarre things start happening. These issues can be broken down into three areas:
	1. System running slow or sluggish performance
	2. Applications blowing up
	3. Problems with services
- In most cases, a slow-running system is due to malware. If malware isn't an issue, open the Task Manager to find and kill processes hogging CPU or disk resources.
- Consider defragmentation and also try using `chkdsk`. Even a single `.dll` file in a bad spot on your mass storage can cause sluggish performance.
- Check Windows Logs > Application/System in Event Viewer.
- When applications crash, try repair or reinstallation.
- Some applications offer a "repair" option or a repair utility after clicking the "change" option in Programs and Features (`appwiz.cpl`). An application might also contain built-in repair features.
- If an application is in a bad spot on your mass storage, it can cause trouble. At this point, consider using `chkdsk` and even SFC.
- Application or OS updates can sometimes be bad and cause issues. Try rolling back updates or applying new updates.
- If a service fails to start, there's something else going on keeping it from starting. Try starting the service manually in the Windows Tools > Services, or check Event Viewer for details.

## Kernel Panic
- Kernel panic means the OS is crashing and can't recover.
- Kernel panics can manifest in different ways. In Windows, as a Blue Screen of Death (BSoD), in macOS, as a Spinning Pinwheel of Death (SPoD), and in Linux, there's so much variance.
- BSoD can happen at any point. It's a Windows thing, so it will not happen until the Windows starts loading.
- Most BSoDs are caused by hardware incompatibility. Try updating drivers.
- Check Event Viewer in Safe Mode for clues.