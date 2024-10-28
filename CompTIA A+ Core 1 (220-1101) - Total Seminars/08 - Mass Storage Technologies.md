# Mass Storage Technologies

## Introduction to Mass Storage
- There are many types of mass storage devices used today, including hard drives, solid-state drives (SSDs), and optical media.
- Logical Block Addressing (LBA) is an organization structure for mass storage devices.
- Regardless of the media your OS sees, mass storage is a string of LBA.
- LBA is inherent to every OS. We don't need to deal with device drivers. Just plug them in right and make sure your BIOS recognizes it.
- The capacity of mass storage devices can be calculated using two different systems: decimal (SI) values and binary (IEC) values.
- Users often see less available capacity on their devices than expected because OSes typically report storage in binary (IEC) values, while manufacturers advertise using decimal (SI) values.
- 5.25", 3.5", 2.5", 1.8", and M.2 are form factors.

| Decimal (SI) Values                               | Binary (IEC) Values                               |
| ------------------------------------------------- | ------------------------------------------------- |
| 10<sup>3</sup> = kilo = 1,000                     | 2<sup>10</sup> = kibi = 1,024                     |
| 10<sup>6</sup> = mega = 1,000,000                 | 2<sup>20</sup> = mebi = 1,048,576                 |
| 10<sup>9</sup> = giga = 1,000,000,000             | 2<sup>30</sup> = gibi = 1,073,741,824             |
| 10<sup>12</sup> = tera = 1,000,000,000,000        | 2<sup>40</sup> = tebi = 1,099,511,627,776         |
| 10<sup>15</sup> = peta = 1,000,000,000,000,000    | 2<sup>50</sup> = pebi = 1,125,899,906,842,624     |
| 10<sup>18</sup> = exa = 1,000,000,000,000,000,000 | 2<sup>60</sup> = exbi = 1,152,921,504,606,846,976 |

## Magnetic Disk Drive
- Magnetic disk drives use spinning platters to store data via magnetism.
- Data is accessed through read/write heads.
- The most popular Hard Disk Drive (HDD) form factors are 3.5" and 2.5".
- Advanced Technology Attachment (ATA) is a command and connection standard for mass storage devices.
- ATA, Parallel ATA (PATA), and Integrated Device Electronics (IDE) refer to older standards using parallel communication to connect internal drives, now largely obsolete. These terms are used interchangeably.
- Serial ATA (SATA) is the modern standard using serial communication for internal storage devices, offering higher speeds and more flexibility.
- SATA is a serial interface; all data moves in sequence (serial) over a single wire.
- SATA connector consists of a power connector and a data connector.
- External SATA (eSATA) is an external version of SATA, providing high-speed connections for external drives but has been mostly replaced by newer technologies like USB 3.x and Thunderbolt.
- eSATA expansion cards are available for motherboards that don't support eSATA.
- Hard drive speeds are measured in Rotations Per Minute (RPM). Speeds include 5,400 RPM, 7,200 RPM, 10,000 RPM, and 15,000 RPM.

## Solid-State Drives (SSDs)
- SSDs store data using chips; there are no moving parts.
- Data is stored in blocks and pages.
- The most popular SSD form factors are 2.5" and M.2.
- Some SSDs still use SATA connectors.
- Non-Volatile Memory Express (NVMe) is a modern, high-performance protocol designed specifically for SSDs and other non-volatile memory types.
- M.2 SSD with two notches typically supports SATA interface. These are not as fast as NVMe SSDs.
- M.2 SSD with a single notch usually supports the NVMe interface. These are commonly referred to as NVMe SSDs.
- In system setup, M1, M2, etc., typically refer to M.2 connectors, while P1, P2, etc., usually refer to ports.

## SCSI
- The Small Computer Systems Interface (SCSI) is an ancient standard that still has great support.
- The old parallel SCSI is standard, but the SCSI language lives on in serial SCSI versions.
- Two modern SCSI standards are Serial Attached SCSI (SAS) and Internet SCSI (iSCSI).
- SAS uses the SATA connector with the SCSI command language.
- iSCSI uses SCSI commands sent over Ethernet.