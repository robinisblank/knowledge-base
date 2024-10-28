# Implementing Mass Storage

## RAID
- Data redundancy refers to storing the same data on multiple locations to prevent it from getting lost.
- RAID stands for Redundant Array of Independent Disks.
- RAID combines multiple physical disks into a single logical unit for the purpose of getting data redundancy and speed.
- There are many ways of setting up a RAID, known as levels.
- RAID 0 (Striping) splits data across multiple disks. It provides speed. If one disk fails, all data is lost.
- RAID 1 (Mirroring) duplicates the same data on multiple disks. It provides data redundancy. If one disk fails, data is still available on other disk(s). Only 50% of total storage capacity is used.
- RAID 5 (Parity) uses block-level striping with distributed parity. Parity information (used to reconstruct data in case of a disk failure) is spread across all disks in the array. It provides speed and redundancy but can only lose one drive. It requires a minimum of three drives.
- RAID 6 uses dual parity, meaning it writes two separate parity blocks for each stripe of data. It also provides speed and redundancy but can only lose two drives. It requires a minimum of four drives.
- RAID 10 (RAID 1+0) creates a striped set of mirrored drives. It can lose one drive on each pair but not one complete mirrored pair. It requires a minimum of four drives or technically two pairs.
- RAID 0+1 is the inverse of RAID 10. It creates a mirrored set of striped disks. It can lose a complete striped pair but not one drive on each pair. It also requires a minimum of four drives or technically two pairs.
- Proprietary RAIDs can work in different ways that aren't revealed by their vendors. These can provide really good efficiency and features.

## Hardware RAID
- Hardware RAID requires a controller to configure the RAID arrays. Many motherboards have built-in RAID controller.
- A dedicated RAID controller comes in the form of an expansion card.
- It has its own BIOS that comes with a special system setup to configure the RAID array.
- We need to switch from AHCI mode to RAID mode in the system setup.
- The completed array looks like a single drive to the OS.
- A hot spare drive is a standby drive that automatically replaces a failed drive. It sits idle until a failure occurs. Data automatically rebuilds onto the spare drive. Downtime is required to manually replace the failed drive with a good one.
- A hot swappable drive can be replaced or added while the system is running.

## Software RAID in Storage Spaces
- Software RAID uses the OS to configure the RAID array.
- Windows comes with a powerful tool called Storage Spaces to configure advanced software RAID arrays.
- Just a Bunch of Disks (JBOD) is a collection of disks that acts as a single drive that doesn't act as RAID.
- Simple refers to JBOD.
- Three-way mirror is Microsoft's proprietary RAID. Traditionally, using drives with different capacities caused wastage, but this doesn't happen with three-way mirrors.
- Software RAID is free but doesn't have a dedicated controller; it is controlled by the OS and the CPU. It's not a problem with high-end CPUs, but slows your system with lower ones.
- Hardware RAID is costly but it has high efficiency and many features.

## Encrypting Mass Storage
- Encryption is used to protect data from unauthorized access.
- File-based encryption encrypts files and folders.
- Disk-based encryption encrypts entire drives.
- Windows uses Encrypted File System (EFS) to encrypt folders and files on New Technology File System (NTFS) formatted drives.
- Windows uses BitLocker to encrypt entire drives.
- BitLocker requires a system with a Trusted Platform Module (TPM) chip.
- BitLocker To Go is an extension of BitLocker that provides encryption for removable storage devices.

## Mass Storage Troubleshooting
- Before attempting any fixes, back up important data. This could involve copying files to a thumb drive or external storage.
- If a device isn't working, go through the process of reinstalling it mentally to identify any steps you might have missed.
- Always double-check, and even triple-check connections and configurations as human error is a common cause of issues.
- **RAID Not Found**:
	- Check if the RAID controller is active and properly configured.
	- Ensure you have the correct drivers installed.
	- Verify hardware connections and power to the drives.
- **RAID Stops Working**:
	- Similar to single-drive issues; check power and connections.
	- Consider the possibility of deleted or corrupted RAID configurations.
- **Read/Write Failures / Extended Read/Write Times**:
    - Often indicate a drive nearing the end of its lifespan.
    - Use Self-Monitoring, Analysis, and Reporting Technology (S.M.A.R.T.) tools to check the drive's health.
    - Replace the drive if it shows signs of failure.
- **Slow/Sluggish Performance**:
	- Likely not a drive issue; could be due to low RAM causing disk thrashing (excessive paging to virtual memory).
	- Red read/write LED status indicator for your hard disk going nuts is a clue.
	- Adding more RAM might solve the issue.
- **Loud Clicking/Grinding Noise (Click of Death)**:
	- Indicates a physical drive failure.
	- Backup immediately if possible and replace the drive.
- **Failure to Boot**:
	- Check the boot order to ensure it is correct.
	- Use Windows Recovery Environment (WinRE) tools for recovery.
	- A common cause is a connected device (like a USB drive) altering the boot sequence.
- **Drive Not Recognized / Bootable Device Not Found / Missing Drives**:
	- Often due to a formatting problem; try reformatting the drive if data isn’t needed.
	- When moving drives between systems, remember to initialize the disk.
- **OS Not Found**:
	- Usually due to incorrect boot order settings.
	- Check for external devices affecting the boot sequence.
- **Attempts to Boot to Incorrect Device**:
	- Directly related to boot order issues; ensure the correct device is prioritized.
- **Continuous Reboots**:
	- Not typically a mass storage issue; could be OS corruption.
	- Might require more in-depth troubleshooting, like checking for a corrupted OS installation or faulty controller settings.