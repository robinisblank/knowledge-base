# Printers and Multifunction Devices

## Laser Printers
- The photosensitive drum is the most critical component of a laser printer.
- Laser printing process (B&W):
	- **Processing**: Print jobs are stored in memory on the laser printer.
	- **Charging**: Primary corona puts a strong negative charge uniformly on the spot on the drum.
	- **Exposing**: Laser writes onto the drum and reduces the negative charge wherever it hits.
	- **Developing**: Toner comes out of the hopper and sticks on the exposed areas on the drum. This is the first time you can see text/pictures on the drum.
	- **Transferring**: Pick-up rollers grab the paper, and separation pads push on it so that only one piece is grabbed at a time. Transfer corona charges the paper with a strong positive charge. As the paper moves through the drum, the toner hits hard on it.
	- **Fusing**: With heat and pressure, toner seals on the paper.
	- **Cleaning**: A rubber scrapper removes residual toner from the drum.
	- All these steps happen simultaneously and continuously until the print job is done.
- Never stick your hand in a functioning laser printer.
- Color laser printers have the same printing process, but instead of a black toner, there are four different toner hoppers, CMYK (Cyan, Magenta, Yellow, Black). It doesn't have a transfer roller, but a transfer belt. Each toner hopper comes close to the belt and transfers its toner.
- Laser printer maintenance means replacing toner cartridges, regular cleaning, and applying maintenance kits.
- The toner cartridge contains a photosensitive drum, toner, and other components.
- Every laser printer has a specific cleaning process that you'll find in their documentation.
- All laser printers have maintenance kits that might contain extra pick-up rollers, separation pads, or transfer rollers.
- The maintenance mode instructs the printer to print its vital statistics.
- Color laser printers have built-in calibration features.

## Inkjet Printers
- Inkjet printers use heat or mechanical processes to push ink through the print heads to the media.
- A feeder is a mechanism that brings in the paper and pushes it out after finishing the print job.
- Inkjet printers use ink cartridges.
- Multifunction Devices (MFDs) include printers, scanners, copiers, and fax machines.
- Inkjet printers also have maintenance modes.
- Whenever an ink jet is not in use, it sits in a maintenance area where stoppers come up to shut the nozzle so the ink doesn't drip and clog.
- Inkjet maintenance means running cleaning routines for the nozzles, replacing ink cartridges, and some form of calibration for color printers.
- Every printer requires you to clear paper jams from time to time.

## Impact Printers
- Dot-matrix is an impact printer that commonly uses tractor feed paper.
- Impact printers use a print head to strike an ink ribbon against a platen to write on the paper.
- Impact printers use a special type of carbon paper.
- These are handy for printing multipart forms.
- Maintenance for an impact printer includes replacing the ribbon, replacing the print head, adjusting platens, and occasional cleaning.

## Thermal Printers
- Thermal printers heat special thermal paper to create a printout.
- It has only two parts: a feed mechanism and a heating element.
- Thermal paper is sensitive to heat. Even a press of your thumb can change its color.
- These can also print to multipart (thermal) forms.
- Maintenance with thermal printers includes frequent paper replacement, cleaning the printhead, and occasionally blowing out debris.

## Installing a Local Printer
- Only you can use the printer in a local printer setup.
- Installing a local printer means connecting to a workstation via USB (commonly used) or serial (niche industry cases).
- Most OSes automatically install the correct printer drivers, or you can find them on the printer's website.
- Firmware updates are common for printers.
- You can download utilities for printers that indicate low ink, paper jams, and other problems.
- For every OS, you have two different functions: printer and spooler.
- Spooler is an associated software that stores and queues the print jobs.
- In Windows, you will find your printer (under "Printers") and spooler (under "Print queues") in Device Manager.
- In the printer properties, under "Events", events are listed for that device. It's a good place to have a look when facing any problem.
- Control Panel > All Control Panel Items > Devices and Printers. Here, you will find all printers, including virtual printers. You can reach here by clicking the "Devices and Printers Folder" option under the Settings tab in printer properties.
- You can adjust printing preferences and printer properties in Devices and Printers.
- Most printers have options for print quality, size, color mode, tray settings, orientation, etc.
- You will find maintenance options in printing preferences.
- Advanced printers have collation and duplex functions.
- Collation allows copies of a document to be printed in the correct order.
- Duplex allows printing on both sides of the paper.
- You can do collation and duplex even though your printer doesn't have those functions. Software like Word allows collation and manual duplex.
- In Windows Settings, under "Printers & scanners", you can open the queue (spooler) of a printer. You can pause printing, cancel all documents, or pause/cancel/restart individual documents.
- The Print Spooler shows up in the System Tray for all actively printing jobs.
- Changes to the spooler require admin permissions. Basic users can control their print jobs, but superusers can control any print job.
- Virtual printers aren't actual printers. They convert the file into a different format or send it to a different location. For example, print to PDF, print to XPS, and print to OneNote.
- You can set a printer to the default printer. Setting this yourself is much better than allowing Windows to handle it.

## Sharing Printers
- Sharing a local printer over a network requires enabling sharing and giving it a shared printer name.
- In Windows, Control Panel > All Control Panel Items > Devices and Printers. Here, open the printer properties of the printer you want to share. Then, under the Sharing tab, check the "Share this printer" option.
- Use appropriate drivers for a given OS while selecting additional drivers.
- In printer properties, under the Security tab, "Manage this printer" means managing all documents in the spooler, and "Manage documents" means managing individual documents in the spooler.
- It's better to allow everyone to print to the printer, but only users with administrator permissions can manage the spooler.
- Printers shared on a domain have to be set up with the domain users.
- Implement user authentication for the print spooler.
- To connect to a shared printer, add a printer, but select the shared printer rather than a local one.
- Be careful of data privacy risks when sharing a printer. Set it up accordingly.

## Installing Wireless and Cloud Printers
- A wired network printer has an Ethernet card and plugs in directly to the network.
- A wireless network printer has a wireless NIC and requires configuration to get on an 802.11 network.
- As soon as a printer is connected to a network, it gets an IP address via DHCP, and it broadcasts itself on the network using protocols like SLP (Mac), LLDP (Windows), and many more. 
- After the printer is connected to the network, you just need to install it on that OS just like you do with a local printer.
- Use the front screen to configure settings or connect to an SSID. It's simple to get an IP address for a printer.
- Use utilities from the printer's website to troubleshoot any connectivity problems.
- When getting a printer, make sure it supports the 802.11 standard you are using.
- You can connect printers to both infrastructure mode and ad hoc mode.
- Bluetooth-capable printers have the same pairing process as other Bluetooth devices.
- Zeroconf (Zero configuration) for Windows, Bonjour for Mac, and AirPrint for wireless on Mac enable devices on the same network to discover and use the printer without manual setup.
- Cloud printing via Google Cloud Print allows wireless printers with Google Print Services support to connect to a wireless network. You can print from anywhere if you are on the Internet and that printer is still on that wireless network.

## Troubleshooting Printers
- **Unable to install a Printer**:
	- You might not have permission to install that printer.
	- Can reflect an unshared or missing printer.
	- Make sure the printer exists and is turned on.
- **No Connectivity**:
	- Most of the time, this is a network issue.
	- Whenever you face a printer problem, go through a mental re-install.
	- Check physical cables, print server, device drivers, and configurations.
	- Rollback device drivers if required.
- **Access Denied**:
	- You don't have permission.
- **No Image on Printer Display**:
	- Is it turned on? Is it in sleep mode? Did you press some keystroke that locked you out of that printer?
	- Might have a bad display and can be replaced.
- **Paper Trouble! Paper not Feeding, Paper/Staple Jam, Issues with Hole Punches, Multipage Misfeed, etc.**:
	- You have a problem with pick-up rollers or separation pads.
	- Apply the maintenance kit to replace faulty parts.
	- Humidity is a great killer of paper.
- **Low Memory Errors**:
	- Laser printers use RAM for memory. They still use older types of RAMs.
	- Try decreasing the resolution.
	- Get more RAM.
	- No need to buy special RAMs that companies sell you. Use the regular ones. Every manufacturer mentions what type of RAM that printer needs.
- **Error Code**:
	- Error codes help us find problems.
	- Research and find what the error code means.
- **Garbled Character on Paper**:
	- Bad or corrupted drivers.
	- Try dumping the print jobs in the spooler and resetting the printer.
	- Rollback device drivers if required.
- **Vertical Lines on Page**:
	- This is a laser printer issue.
	- There is foreign matter on the photosensitive drum. It's impossible to clean it without damaging it.
	- Replace the toner cartridge.
- **Color Prints in the Wrong Print Color or Incorrect Color Settings**:
	- Issues with drivers.
	- If dead ink, then replace that one.
- **Printing Blank Pages**:
	- A thermal printer with a faulty heating element.
	- A laser printer with dead primary corona.
- **Streaks/Speckling on Printed Pages**:
	- This is an inkjet printer issue.
	- Go into the maintenance mode to clean the nozzles.
- **Faded Prints**:
	- If it's a laser printer, you are low on toner. Put a new toner cartridge.
	- If it's an impact printer, your ink ribbon is running out and needs to be replaced.
- **Ghost Images or Double/Echo Images on the Print**:
	- This is a laser printer issue.
	- Those ghost images are from the previous cycle because of the leftover toner on the drum.
	- The rubber scrapper that removes residual toner from the drum is broken.
	- Replace the toner cartridge.
- **Toner Not Fused to Paper**:
	- Replace the fuser assembly.
- **Creased Paper**:
	- One of the pick-up rollers isn't working properly, and the paper gets pulled at an angle, causing creases.
	- Apply maintenance kit to replace pick-up rollers.

## 3D Printing
- 3D printers melt and extrude thermal plastic (such as filament or resin) in a pattern to create a 3D shape on the print bed.
- A 3D printer consists of a movable heating element with an extruder attached to a feed tube that brings in the filament.
- Software like Blender is used to create a 3D image.
- A slice file created by the software after the slicing process is given to the 3D printer.