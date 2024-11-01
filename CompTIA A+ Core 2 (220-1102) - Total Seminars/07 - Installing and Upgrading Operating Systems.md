# Installing and Upgrading Operating Systems

## Windows 10 Editions and Features
- Run the `winver` command to see the Windows edition and version you are running.
- Domain is a network of computers managed by a central server (Domain Controller) for centralized administration and security.
- Remote Desktop Protocol (RDP) is a proprietary Windows protocol that enables remote access to and control of a computer over a network. It uses port 3389.
- Group Policy (gpedit.msc) is a Windows feature that allows administrators to configure and manage user and computer settings across a domain.
- BitLocker is an encryption tool that protects data on Windows devices by encrypting entire disk volumes.
- Long-Term Servicing Branch (LTSB) is a Windows version designed for stability and long-term support with minimal feature updates, which is ideal for critical systems.
- Visit Microsoft's official website for more information about different editions and features of Windows.

| Edition                         | Min RAM                      | Domain | RDP | Group Policy | BitLocker | LTSB |
| ------------------------------- | ---------------------------- | ------ | --- | ------------ | --------- | ---- |
| Windows 10 Home                 | 1 GB (32-bit); 2 GB (64-bit) | N      | N   | N            | N         | N    |
| Windows 10 Pro                  | 1 GB (32-bit); 2 GB (64-bit) | Y      | Y   | Y            | Y         | N    |
| Windows 10 Pro for Workstations | 1 GB (32-bit); 2 GB (64-bit) | Y      | Y   | Y            | Y         | N    |
| Windows 10 Enterprise           | 1 GB (32-bit); 2 GB (64-bit) | Y      | Y   | Y            | Y         | Y    |

## Windows 11 Editions and Features
- Windows 11 features a much more security-centric build.
- If your Windows 10 PC meets the minimum specifications, you can easily upgrade to Windows 11.
- Windows 11 requires UEFI, Secure Boot, and TPM 2.0.
- Windows 11 OS is based on the Zero Trust security model that assumes that no entity should be trusted by default. It's based on the philosophy of "never trust, always verify".
- You must have an Internet connection to set up Windows 11, and local accounts can't initially be used. You have to sign in with a Microsoft-connected services account.
- Long-Term Servicing Branch (LTSB) is now called Long-Term Servicing Channel (LTSC).

| Edition                         | Min RAM | Min CPU        | Domain | RDP | Group Policy | OneDrive for Business | BitLocker | LTSC |
| ------------------------------- | ------- | -------------- | ------ | --- | ------------ | --------------------- | --------- | ---- |
| Windows 11 Home                 | 4 GB    | 1 GHz; 2 cores | N      | N   | N            | N                     | N         | N    | 
| Windows 11 Pro                  | 4 GB    | 1 GHz; 2 cores | Y      | Y   | Y            | Y                     | Y         | N    |
| Windows 11 Pro for Workstations | 4 GB    | 1 GHz; 2 cores | Y      | Y   | Y            | Y                     | Y         | N    |
| Windows 11 Enterprise           | 4 GB    | 1 GHz; 2 cores | Y      | Y   | Y            | Y                     | Y         | Y    |

## Boot from Everything
- An ISO image is an exact copy of an optical media saved as a single file.
- The OS must be in the partition table of the mass storage device.
- To make a bootable media, you need to download an ISO file of the OS and burn it on optical media, thumb drive, SD card, etc.
- We always call it "burn" with every mass storage device, though it only makes sense with optical media.
- Mounting an ISO file makes its contents accessible.
- The "Burn disc image" option will write the contents of an ISO file onto a physical disc. The resulting disc is a clone of the original and can be booted.
- Rufus is a utility that helps format and create bootable USB flash drives, such as USB keys/pen drives, memory sticks, etc.
- You can also boot from a network server using Pre-Boot Execution Environment (PXE) or Apple NetBoot.
- Windows Recovery Environment (WinRE) is used to create recovery drives that can repair common causes of unbootable OSes.

## Installing and Upgrading Windows 10
- Keeping your Windows OS updated ensures your system is protected against known threats.
- The End-of-Life (EOL) for OSes occurs at the end of the product lifecycle.
- Performing an upgrade using the built-in Windows OS installer is called an in-place upgrade.
- Use Windows Update or PC Health Check to see system requirements and hardware compatibility.
- Image deployment allows us to install/update Windows on multiple systems across a network simultaneously.

## Post-Installation Tasks
- Check for errors in Device Manager.
- Install any third-party drivers after installing or upgrading an OS.
- You can install the latest drivers from the manufacturer's website, as the one with the hardware can be an older version.
- Update drivers as needed.
- In installations, where a screen comes up that lists many drivers, don't install extra web browsers and garbage that they put together.
- Run Windows Update to install any needed updates.
- A recovery drive is a copy of Windows that's used to reset or troubleshoot your PC even if it can't start. If you back up system files to this drive, you'll also be able to reinstall Windows.
- You'll need a USB drive that's at least 16 GB to create a recovery drive.
- A restore point is a snapshot of your system as it currently is. You'll find this under the System Protection tab in System Properties. Click Configure and check "Turn on system protection".
- Windows comes with pre-installed anti-malware, antivirus, and firewall software.
- Use Windows File History to automatically back up your files.
- Windows installs a basic video driver during installation.

## Installing and Updating Linux
- You can install many Linux distributions (distros) from an optical media or USB drive using an ISO file.
- Some editions of Linux can be run as a "Live CD", requiring no actual software installation or changes to a system's configuration.
- Live CDs/DVDs are getting replaced by Live USBs.
- Linux can be updated from the software manager or the command-line interface.

## Upgrading macOS
- macOS upgrade options can be found under System Preferences > Software Update.
- Be sure to check before you upgrade any OS, as it can introduce incompatibilities or issues with your workflow.