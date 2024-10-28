# Essential Peripherals

## USB Standards
- USB stands for Universal Serial Bus.
- With devices like keyboard or mouse, you will never be able to go faster than 12 Mbps.
- USB 3.0 had many compatibility issues that were fixed in USB 3.1 Gen 1.
- There are many types of USB connectors: Type-A, Type-B, mini-B, micro-B, 3.0 micro-B, and Type-C.
- USB is backward compatible. A USB device will work with a USB port with an older standard, but it will only run up to the speed of that port.
- Different USB standards might use unique coloring, but don't take it as a law. These colors are common in Type-A but you will also see them with other types.

| Standard      | Maximum Speed |
| ------------- | ------------- |
| USB 1.0       | 1.5 Mbps      |
| USB 1.1       | 12 Mbps       |
| USB 2.0       | 480 Mbps      |
| USB 3.0       | 5 Gbps        |
| USB 3.1 Gen 1 | 5 Gbps        |
| USB 3.1 Gen 2 | 10 Gbps       |

| Color             | Standard             |
| ----------------- | -------------------- |
| White             | USB 1.1              |
| Black             | USB 2.0              |
| Blue              | USB 3.0 or 3.1 Gen 1 |
| Teal              | USB 3.1              |
| Red/Orange/Yellow | Charging Ports       |

## Understanding USB
- All USB devices connect to built-in USB controllers, which are in charge of all connected USB devices.
- USB Type-A is generally a downstream connection; USB Type-B is generally an upstream connection.
- The motherboard sends commands downstream, and the device takes commands from upstream.
- In most cases, B connector is soldered into the device.
- B connectors are plugged into the devices. You never plug them in a computer.
- USB Type-C automatically configures the upstream and downstream connections. You can plug it either way.
- Typically, multiple controllers (like 2.0 or 3.1) are connected to separate root hubs. The connectors coming off of the root hub are colored according to the controller connected to it.
- USB allows you to plug in up to 127 devices.
- A USB hub lets you connect multiple devices using a single connector on the motherboard.
- A single connector cannot supply enough power if many devices are connected to the USB hub. There are powered hubs that have AC connectors to plug into the AC power.
- In Windows, you can see USB controllers in Device Manager.

## Configuring USB
- USB devices need device drivers to function.
- OSes come with thousands of built-in device drivers.
- In some cases, you may need to install the device driver by yourself.
- Human Interface Device (HID) are base drivers that ensure that the core features of devices like mice and keyboards always work. The base features of a fancy mouse or keyboard will work fine, but you need to install drivers that support their extra features.
- You can disable USB ports selectively or all of them through the system setup to prevent people from putting malicious USB devices into your computer.
- USB lock is a security software that prevents, reports, and whitelists USB devices.

## Thunder and Lightning
- Thunderbolt and Lightning are connection technologies.
- The Thunderbolt standard combines PCI Express (for data) and DisplayPort (for video) into a single connection. It can charge, transfer data, drive monitors, and so much more.
- Thunderbolt 1 runs at 10 Gbps (x2 channels = 20 Gbps total)
- Thunderbolt 2 runs at 20 Gbps
- Thunderbolt 3 runs at 40 Gbps
- Thunderbolt 1 and 2 uses the same connector as Mini DisplayPort.
- Thunderbolt 3 uses USB Type-C connector.
- The lightning bolt near the port or on the connector tells that it is a Thunderbolt.
- The Lightning standard is exclusive to Apple products. It uses a proprietary lightning connector.
- macOS generally uses Thunderbolt, and iOS generally uses Lightning.
- Thunderbolt is showing up as USB Type-C in recent apple products.

## Optical Media
- Compact Disc (CD) was originally designed to play music. It came in capacities of 74 mins and 80 mins.
- Compact Disc Read-Only Memory (CD-ROM) allowed us to store data. The file system was based on ISO-9660 standard which we called CD File System (CDFS).
- CD-R (Recordable) allowed us to burn data, but you couldn't erase data.
- CD-RW (ReWriteable) allowed us to burn and erase data.
- CDs store 650-700 MB of data.
- Digital Video Disc (DVD) was originally designed to play movies.
- DVD today stands for Digital Versatile Disc.
- DVD Read-Only Memory (DVD-ROM) allowed us to store data. Even today, this is the most common type of optical media.
- DVD with Dual-Layer (DL) has two layers that are hit by different lasers.
- DVD with Double-Sided (DS) is silver on both sides.
- SS stands for Single-Sided, and SL stands for Single-Layer.
- DVDs came in many formats like, -R, +R, -RW, and +RW.
- Today, any optical drive can read/write any optical media with any format.
- Blu-ray Disc (BD) was originally designed to play high definition movies. These are best in terms of capacity. This also came in various formats like -R and -RE.
- The hole in an optical drive is the emergency eject hole. It allows you to manually eject the disc tray using a paperclip or a similar object if the drive is not functioning properly or there is no power.
- Configuring optical media is simple. They are SATA devices that are based on the ATA standard. You just need to plug them in, make sure they show up in the system setup, and the OS will automatically recognize them.

| DVD Version           | Capacity                                      |
| --------------------- | --------------------------------------------- |
| DVD-5 (12 cm, SS/SL)  | 4.37 GB, more than two hours of video         |
| DVD-9 (12 cm, SS/DL)  | 7.95 GB, about four hours of video            |
| DVD-10 (12 cm, DS/SL) | 8.74 GB, about four and a half hours of video |
| DVD-18 (12 cm, DS/DL) | 15.90 GB, more than eight hours of video      |

| BD Type          | Size  | Capacity (single layer) | Capacity (dual layer) |
| ------------- | ----- | ----------------------- | --------------------- |
| Standard disc | 12 cm | 25 GB                   | 50 GB                 |
| Mini disc     | 8 cm  | 7.8 GB                  | 15.6 GB               |

## Readers and Scanners
- Smart card readers and Magnetic readers are used to read cards.
- Hard token is a smart card used to authenticate into a system.
- Flash memory readers read many types of flash memory.
- SD Cards are very popular flash memory.
- SD cards, Mini SD card, and Micro SD card have different physical sizes.
- Scanners read paper documents.
- Automatic Document Feeder (ADF) enables multiple pages to scan.
- Barcode and QR code scanners read printed coded labels.

## Common Peripherals
- The term peripherals includes both input and output devices.
- The most common modern peripherals are mice, keyboards, webcams, and external storage.
- A Ten Keyless (TKL) keyboard doesn't have a num pad.
- Wireless mice and keyboards work with USB Unifying Receiver which operates on Radio Frequency (RF) technology.
- "USB controller resource warning" means that too many devices are connected to high-speed ports. Rearrange devices to lower speed ports or reboot your system.
- You can personalize your sound settings in Windows.

## Webcams and Videoconferencing
- Webcams enable us to meet remotely using videoconferencing software.
- Two common videoconferencing software are Zoom and Microsoft Teams.

## Installing and Troubleshooting Expansion Cards
- Peripheral Component Interconnect (PCI) cards were the first internal plug and play (PnP) components.
- PCI Express (PCIe) is an updated standard for PCI that enables devices to keep up with higher bandwidth hardware like the CPU and RAM.
- PCIe lanes (x1, x4, x8, and x16) refer to the number of data lanes that a PCIe slot or device uses to transfer data. The number of lanes determines the slot's bandwidth.
- PCIe slots can be used for GPUs/video cards, sound cards, network interface cards (NICs), and RAID cards.
- You may need to disable on-board/integrated graphics in the BIOS when installing a GPU/video card.