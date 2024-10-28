# Wireless Networking

## Wireless Network Hardware
- Wireless networking works on the IEEE 802.11 standard.
- A Wireless Access Point (WAP) serves as a bridge between an ethernet network and a wireless 802.11 network.
- A true WAP only has an ethernet connection, and is only a WAP. However, a home router has multiple ethernet ports to give Internet access to various devices. It is a router, switch, and WAP all in one.
- 802.11 works in one of two modes: Infrastructure mode or Ad hoc mode.
- Infrastructure mode requires WAPs and wireless network cards.
- Ad hoc mode doesn't require a WAP. One of the clients sets up the wireless network, and other computers see it as a WAP.
- Wireless network cards come in many forms: dedicated NICs, motherboards with built-in NICs, USBs, laptops with built-in NICs, and smartphones.
- Laptops' wireless antennas usually run around the monitor.
- Smartphone's wireless antennas are usually the whole case.
- The Service Set Identifier (SSID) is more commonly called the "network name." It's the name associated with a particular Extended Service Set (ESS).
- ESS is a wireless network, created by multiple access points, which appears to users as a single, seamless network, such as a network covering a home or office that is too large for reliable coverage by a single access point.
- An ESS is a group of Basic Service Sets (BSS) that share the same SSID.
- BSS is the area covered by an Access Point (AP).
- BSSID is the unique identified for a specific AP within a wireless network.
- The omnidirectional antenna's radiation pattern looks like a big fuzzy ball.
- Dipole antennas combine two omnidirectional antennas that point opposite to each other. Its radiation pattern looks like a disc and doesn't propagate signals up and down.
- The patch antenna's radiation pattern looks like a semi-sphere. It is useful when kept against the wall and propagating signals only in one direction, which excludes the back of the antenna.
- The highly-directional antenna's radiation pattern looks like a stretched rugby. It is excellent for long distances. You have highly-directional antennas on both ends to send and receive long-thrown signals.
- Wi-Fi Protected Access (WPA) is a form of encryption that uses Temporal Key Integrity Protocol (TKIP) as its wrapper.
- Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA) is the methodology used in wireless to send and receive data packets.

## Wi-Fi Standards
- The 802.11 has extensions with improving capabilities.
- 802.11 is based on Industrial, scientific, and medical (ISM) radio bands. It uses either or both bands of 2.4 GHz and 5 GHz.
- A band is a range of radio frequencies. If we had only one frequency, then every device would stomp over each other. Different devices use different frequencies from the range.
- 2.4 GHz band range: 2.412-2.4884 GHz
- 5 GHz band range: 5.150-5.875 GHz
- 802.11 uses premade channels. Each channel takes a piece of the band.
- 2.4 GHz usually has 14 channels, and 5 GHz has 24 non-overlapping channels.
- A WAP has a radio inside it, either or both 2.4 GHz and 5 GHz. If you have a WAP that runs on 802.11g, it is backward compatible with 802.11b as it runs on a 2.4 GHz band. But, it is not backward compatible with 802.11a because that WAP doesn't have a 5 GHz radio.
- A WAP with 802.11n is backward compatible with any wireless network card.
- 802.11n (Wi-Fi 4) introduced MIMO (multiple in/multiple out), which allows the WAP to change its antennas' radiation signal to zero into a device.
- 802.11ac (Wi-Fi 5) is incredibly fast, splits the channels, improves the MIMO, and introduces Multiuser MIMO (MU-MIMO), which can zoom signals into multiple devices.
- Make sure that your NIC matches your WAP's 802.11 extension.
- Many WAPs with 802.11ac have 2.4 GHz radio just for backward compatibility.
- 802.11ax (Wi-Fi 6) uses the 6-GHz band.

| Extension | Speed    | Band              |
| --------- | -------- | ----------------- |
| 802.11a   | 54 Mbps  | 5 GHz             |
| 802.11b   | 11 Mbps  | 2.4 GHz           |
| 802.11g   | 54 Mbps  | 2.4 GHz           |
| 802.11n   | 150 Mbps | 2.4 GHz and 5 GHz |

## It's a Huge Mesh
- Wireless Mesh Network (WMN) is a great wireless solution for SOHO environments than infrastructure networks.
- Mesh networks have a base station and beacon devices that connect to the base station.
- Mesh networks use third-party encryption that is much more robust than common encryptions.
- Mesh networks are easy to configure. You only need to change your SSID (network name) and password.

## Enterprise Wireless
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

## Beyond Wi-Fi
- Radio Frequency Identification (RFID) manifests as a sticker/tag that is a radio containing information.
- An RFID reader uses radio frequency energy to activate RFID tags so that they transmit back information.
- RFIDs are mainly used in the industrial world, such as distribution.
- Near Field Communication (NFC) is a type of RFID technology.
- Today, almost every smartphone has an RFID reader. 
- NFC requires extremely close proximity to function. That's why it says "tap-to-print" or "tap-to-pay".
- Bluetooth is designed to connect only two devices at any moment. It creates a Personal Area Network (PAN).
- In older Bluetooth devices, we needed to set one device in discoverable mode, and then the other device seeks out this device. Once they see each other, they will require a 4-digit PIN code for pairing. But modern Bluetooth devices are much easier to pair.

| Bluetooth Class | Power  | Range |
| --------------- | ------ | ----- |
| Class 1         | 100 mW | 100 m |
| Class 2         | 2.5 mW | 10 m  |
| Class 3         | 1 mW   | 1 m   |

## Troubleshooting Wireless Connections
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