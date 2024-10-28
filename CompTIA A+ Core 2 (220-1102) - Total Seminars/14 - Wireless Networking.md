# Wireless Networking

## Basic WAP Setup

## Wireless Encryption

## Connecting to a Wi-Fi Network

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
- Wi-Fi analyzers help diagnose wireless problems.
- If multiple devices can't see a network, the issue may lie with the SSID or wireless network, not the devices.
- Low RF signal can lead to no, low, slow, or intermittent connectivity. Try getting closer to the SSID. Make sure there are no walls or other interferences in between.
- **No Connectivity**:
	- SSID or password might be changed.
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