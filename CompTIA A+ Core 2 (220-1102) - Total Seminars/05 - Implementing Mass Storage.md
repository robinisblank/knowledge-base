# Implementing Mass Storage

## Understanding Partitioning
- A mass storage device is like a house, and partitions are like different rooms. Inside a human house, are rooms like a kitchen, bedroom, garage, bathroom, etc. Similarly, in a mass storage device, partitions can be for OSes, recovery, swap partitions in Linux, and others of your choice.
- A swap partition in Linux is a disk partition used for virtual memory.
- Partitions are created using some utility provided by the OS. They must be mounted to make them accessible to the user.
- In Windows, partitions manifest as drive letters with a colon; in Linux/macOS, partitions manifest as folders.

## MBR Partitioning
- There has to be a way to tell your computer after turning it on where to find the OS on the mass storage so that the OS can take control.
- Master Boot Record (MBR) is the oldest type of partition still in use today. It not only defines partitions but also tells the computer where to find the OS.
- LBA 0 is a block at the start of a hard disk that the computer starts reading when turned on. This block contains a small program known as MBR.
- MBR consists of a boot loader and a partition table.
- LBA 0 was divided into five partitions. One for the boot loader and four were originally used to run different OSes.
- Boot loader is the first code read off a mass storage. It pointed to the start of the partition with the OS that needed to be run. Whichever partition was booted off was assigned as the "active partition".
- MBR had a limit of 2 TB per partition.
- MBR is limited to only 4 partitions.
- Modern versions of Windows don't do MBR well anymore.
- If more than four partitions are needed on a single drive, an extended partition with additional logical drives can be created. Instead of four primary partitions, there will be three primary partitions and one extended partition. Each partition within that extended partition is known as a logical drive.
- Over time two major problems were faced with MBR:
	1. The capacity of hard disks got bigger and the 2 TB limit became a problem.
	2. People wanted more partitions.

## GPT Partitioning
- GUID Partition Table (GPT) is the new standard that improves MBR partitions. It works closely with UEFI and offers many features.
- A Globally Unique Identifier (GUID) is a 128-bit value assigned to a partition.
- With GPT, you can have 128 partitions on a single drive.
- With GPT, there is no concept of primary partition, extended partition, or logical drives. There are just simple partitions commonly referred to as volumes.
- Each partition can be of 18.8 million TB.
- GPT is backward compatible with MBR. It consists of a Protective MBR in LBA 0.
- Protective MBR is there in case the drive is yanked out of a GPT-capable system and put into an old MBR system. They will get a warning that says "cannot read LBA partitions" to stop them from erasing it.
- A portion of the Protective MBR says, "I am a GPT". If a GPT-capable system reads it, it will ignore this part and move to actual partitions.
- LBA 1 is the Primary GPT Header that stores information about partitions.
- A Secondary GPT Header is somewhere in the storage (usually next to the primary). It's a copy of the Primary GPT Header. It can rebuild partitions if anything happens to the Primary GPT Header.
- If you have an MBR drive, you can convert it to GPT. All OSes have this ability.
- Modern OSes only offer GPT. You will see MBR only with older systems.

## Understanding File Systems
- If a drive is like a house, a partition is like a room, then formatting is like creating shelves to store files and folders in an organized manner.
- A partition must be formatted before it's usable.
- A file system is applied to a partition by formatting.
- All file systems have a data structure known as a File Allocation Table (FAT) that maps LBA blocks to files and folders.
- FAT16 and FAT32 are file systems in the FAT family.
- On the left side of the FAT, there are LBA values for every block on that drive.
- On the right side of the FAT, there is content for each LBA block.
- Empty blocks are marked with zeroes.
- In the formatting process, each LBA block is queried to check if it isn't a bad block and if it can be read/written properly. Bad blocks are marked with a unique value and are skipped when writing content.
- When we store a file, it will look for an available/empty block. If it needs more blocks, then the value of the next block is written to the previous block before writing any content. In the end, we put `FFFF` to mark the end of the file.
- Fragmentation occurs when files get stored in non-contiguous blocks. This is less of an issue with SSDs. However, in HDDs, it can cause slower read/write speeds.
- Formatting tests blocks, creates a file index and a blank root folder/directory.

## Popular File Systems
- FAT32 is an ancient file system. It introduced many features like having long file names.
- New Technology File System (NTFS) is the primary file system for Windows. It supports compression, encryption, file/folder security, and many features.
- NTFS doesn't use FAT; it uses Master File Table (MFT).
- Extensible File Allocation Table (exFAT) is a middle ground between FAT32 and NTFS. It is designed to handle larger file and volume sizes without the overhead of NTFS features like compression and encryption.
- FAT32 and exFAT are handy for thumb drives.
- Compact Disc File System (CDFS) was designed to organize a file system that the OS can read on an optical media, which was originally designed to play movies and music. It is a standard for all optical media.
- Linux uses Third Extended Filesystem (ext3) and Fourth Extended Filesystem (ext4).
- Mac OS uses Hierarchical File System Plus (HFS+).

| **File System** | **Maximum File Size** | **Maximum Volume Size**          |
| --------------- | --------------------- | -------------------------------- |
| FAT32           | 4 GB                  | 2 TB (up to 16 TB in some cases) |
| NTFS            | 16 TB (default)       | 256 TB (default)                 |
| exFAT           | 16 EB                 | 128 PB                           |
| CDFS (ISO 9660) | 4 GB                  | 8 TB                             |
| ext3            | 2 TB                  | 16 TB                            |
| ext4            | 16 TB                 | 1 EB                             |
| HFS+            | 8 EB                  | 8 EB                             |

## Formatting in Action
- Windows uses Disk Management to partition and format disks.
- New drives must first be initialized in Windows.
- Quick format option skips checking blocks while formatting.
- Allocation unit size refers to the size of blocks. It's rare not to use default.
- FAT (Default) or FAT refers to FAT16.
- Linux has many tools for partitioning and formatting. Use the one you like.

## Dynamic Disks
- Dynamic disks are unique to Windows.
- A drive must be converted from basic to dynamic to get those extra features.
- Dynamic disks enable shrinking, extending, and spanning volumes without losing data. RAID 0, 1, and 5 are also possible.
- You will see these options even with basic disks. Windows will convert them to dynamic when you select such an option.
- Any data in the volume you are extending remains in perfect order.
- Windows will not let you shrink a volume beyond the occupied size.
- Spanned volume allows you to make two or more disks act as one.
- Creating a spanned volume is not recommended because now you will have two or more points of failure. If either one of the drives dies, you will lose your data.
- Spanned volume feature should be used in an emergency. If your drive gets full, you can put another drive and span the volume till you can get a bigger drive.
- Best practices that Microsoft recommends:
	1. Keep the boot drive basic (not dynamic).
	2. Set the boot drive to GPT.
	3. Converting dynamic disks back to basic erases all data.

## New Installation - First Drive
- The first drive on a system relies on the OS install program to provide partition and format tools.
- The partitioning and formatting tools in installation programs provide a smaller subset of tools compared to their main tools.
- Installation tools may provide features not normally seen (such as swap file creation).

## Software RAID in Storage Spaces
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/09 - Implementing Mass Storage](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/09%20-%20Implementing%20Mass%20Storage.md)
- Software RAID uses the OS to configure the RAID array.
- Windows comes with a powerful tool called Storage Spaces to configure advanced software RAID arrays.
- Just a Bunch of Disks (JBOD) is a collection of disks that acts as a single drive that doesn't act as RAID.
- Simple refers to JBOD.
- Three-way mirror is Microsoft's proprietary RAID. Traditionally, using drives with different capacities caused wastage, but this doesn't happen with three-way mirrors.
- Software RAID is free but doesn't have a dedicated controller; it is controlled by the OS and the CPU. It's not a problem with high-end CPUs, but slows your system with lower ones.
- Hardware RAID is costly but it has high efficiency and many features.

## Encrypting Mass Storage
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/09 - Implementing Mass Storage](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/09%20-%20Implementing%20Mass%20Storage.md)
- Encryption is used to protect data from unauthorized access.
- File-based encryption encrypts files and folders.
- Disk-based encryption encrypts entire drives.
- Windows uses Encrypted File System (EFS) to encrypt folders and files on New Technology File System (NTFS) formatted drives.
- Windows uses BitLocker to encrypt entire drives.
- BitLocker requires a system with a Trusted Platform Module (TPM) chip.
- BitLocker To Go is an extension of BitLocker that provides encryption for removable storage devices.

## Maintaining Storage Disks
- Error checking and optimization help maintain the health and performance of storage devices. You will find both these options under the Tools tab in the disk's properties.
- Error checking runs the `chkdsk` command on a disk to check for file system errors and bad sectors/blocks.
- Optimizing (defragmentation) reorganizes fragmented data to improve disk performance.
- Trimming allows data to be written in individual pages termed "available for use".
- Optimizing trims blocks in disks to allow new data to be written in partially full blocks.