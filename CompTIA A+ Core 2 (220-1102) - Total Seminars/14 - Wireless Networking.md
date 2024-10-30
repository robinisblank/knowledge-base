# Wireless Networking

## Basic WAP Setup
- A site survey using a Wi-Fi analyzer (e.g., WiFiman by Ubiquiti) shows available channels in an ISM band.
- It's okay if SSIDs overlap on a channel. They will run even if they are overlapped, but they run better if they are not.
- The best practice is to have the WAP pick a channel for an SSID automatically. These devices are smart; they can find and use the least congested channel.
- On the 2.4 GHz band, we might sometimes set the channel manually after picking the least congested one. But on the 5 GHz band, it's best to set the channels automatically.
- You'll find wireless settings on the SOHO router's web interface.
- Service Set Identifier (SSID) is the name of your wireless network.
- You can hide/disable SSID broadcast.
- To speed things up, you can select a mode that contains only the Wi-Fi standards that devices on that network use.
- You can change the channel width.
- You can adjust the transmit/radio power.
- Make sure the wireless radio is enabled after you're done changing its settings.

## Wireless Encryption
- A wired network can only be intercepted with a physical connection, but everything on an unencrypted (open) wireless network can easily be intercepted by anyone with the right capture tools.
- The obsolete Wired Equivalent Privacy (WEP) encryption can be easily cracked today and is never used. It used an ancient encryption known as RC-4, which was predictable and people were able to hack it mechanically.
- Wi-Fi Protected Access (WPA) introduced Temporal Key Integrity Protocol (TKIP) encryption, Personal/Pre-Shared Key (PSK), and Remote Authentication Dial-In User Service (RADIUS) authentication.
- WPA2 added Advanced Encryption Standard (AES) encryption.
- WPA uses TKIP; WPA2 uses AES.
- Today, most probably you are going to use WPA2 and PSK in a SOHO environment.
- Wi-Fi Protected Setup (WPS) automates setting up encryption but can be easily cracked. Just press the WPS button on the router, then on the WPS-capable device, and they will automatically configure themselves.

## Connecting to a Wi-Fi Network
- Disabling your wireless NIC is different from airplane mode. Airplane mode disables all wireless communications on a device.
- In Windows, you can enable/disable your wireless NIC in Control Panel > Network and Internet > Network Connections.
- All wireless clients can scan the 802.11 spectrum, finding available SSIDs.
- You must know the SSID and password to connect.
- Clients create a network profile that stores the SSID and their password.
- In Windows, you can manage network profiles in Network & internet > Wi-Fi > Manage known networks.
- **Issues Connecting to an SSID**:
	- The NIC is set up as a DHCP client. If you get an APIPA address (`169.254.x.x`), it's a clue that you have a bad password.
	- Passwords can change. Delete (forget) the network profile and try to make a new connection.
	- You can set wireless NIC to a static IP address to avoid these issues.

## Enterprise Wireless
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/14 - Wireless Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/14%20-%20Wireless%20Networking.md)
- The major difference between an enterprise environment and a SOHO environment is that in an enterprise network, we use dedicated WAPs.
- Most WAPs don't have AC adapters. They use Power over Ethernet (PoE). They get electricity from their ethernet cable itself.
- PoE (1st generation) and PoE+ are versions of PoE. PoE+ provides a lot more electricity.
- A PoE switch can communicate and provide electricity.
- To take advantage of power over ethernet, you need to have devices that are PoE capable, you should be careful about the versions of PoE, and you need to have a PoE switch.
- If you don't have a PoE switch, you can use a PoE injector.
- There are enterprise tools to analyze where to put your WAPs and types of antennas to use. They can also show you a heat map to see the wireless coverage and find dead spots.
- Enterprise networks use RADIUS or TACACS+ protocols to implement the Authentication, Authorization, and Accounting (AAA) framework.
- Change default usernames and passwords that are used to configure WAPs.
- It's good to provide static IP addresses to WAPs instead of a DHCP server.
- An Extended SSID (ESSID) is when every single WAP on a LAN has the same SSID. Your device will automatically get picked up by the nearest WAP as you walk into campus or the office.
- If you enable isolation, the connected device can only talk to WAP. It cannot communicate with other devices, share resources, etc. This way, people will only get on the Internet, but won't be able to pass files and folders.
- Separate SSIDs with same/different settings can be enabled/disabled easily for guest access.
- You can set up WAPs to know each other's MAC address, so if any other device tries to act as a WAP, it will be ignored or blocked because its MAC address is not on the list. This is rogue AP detection.
- Know your network ID. You should be aware of what kind of IP addresses your DHCP server allocates (e.g., `10.11.12.x` or `192.168.0.x`) so if one day something weird happens like getting an IP address of `44.33.22.x` kind, you will be able to detect it quickly.
- Rate limit allows throttling of upstream and downstream speeds on specific SSIDs.
- A captive portal is a web page displayed to newly connected users before they are granted broader access to network resources.
- Special enterprise Wireless LAN (WLAN) switches allow us to configure things like ESSIDs and captive portals only a single time which then will be propagated to all WAPs.

## Troubleshooting Wireless Connections
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/14 - Wireless Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/14%20-%20Wireless%20Networking.md)
- Wi-Fi analyzers (e.g., WiFiman by Ubiquiti) help diagnose wireless problems.
- If multiple devices can't see a network, the issue may lie with the SSID or wireless network, not the devices.
- Low RF signal can lead to no, low, slow, or intermittent connectivity. Try getting closer to the SSID. Make sure there are no walls or other interferences in between.
- **No Connectivity**:
	- SSID or password might be changed.
	- If you have a problem with an existing network, it's probably a bad network profile. Delete (forget) the network profile and try to make a new connection.
	- Check antennas and make sure they are standing straight. Some WAPs can have different antennas for different bands. If a 2.4 GHz antenna is bent, you might get connectivity issues with that particular SSID.
	- SSID broadcast might be disabled. In this case, you need to manually configure the profile that requires the exact SSID, security protocol, and password.
- **Limited Connectivity**:
	- Many situations that happen with no connectivity also occur with limited connectivity.
	- External interference (like a wall, baby monitor, microwave, etc.) can interfere with wireless signals.
	- Change the physical placement of the WAP or move interfering objects.
- **Intermittent Connectivity**:
	- Advanced versions of 802.11ac are incredibly good with getting around problems like external interference. But if they can't, they will stop and restart again.
	- Too many people might be on the wireless network.
	- If you are in charge of the network, get more WAPs.
	- Implement Quality of Service (QoS) for devices/ports that always need good bandwidth.