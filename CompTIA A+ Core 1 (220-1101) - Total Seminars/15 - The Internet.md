# The Internet

## Beyond the LAN
- A Local Area Network (LAN) is a group of computers that are physically connected close to each other via a switch. These computers share the same network ID (e.g., `192.168.4.0`).
- A Wide Area Network (WAN) is two or more LANs interconnected by one or more routers. Each LAN has a unique network ID.
- A Metropolitan Area Network (MAN) is a WAN that spans a city.
- The Internet is the biggest WAN.
- A Personal Area Network (PAN) is a point-to-point connection used only in Bluetooth connections.

## Internet Tiers
- The Internet is composed of many organizations that connect to each other.
- A Network Operations Center (NOC) is a centralized location where an organization's IT team monitors and manages its networks.
- Tier 1 providers do not pay anyone and have peering agreements.
- Tier 2 providers pay some Tier 1s but also peer with Tier 1 and Tier 2s.
- Tier 3 providers pay Tier 1 or Tier 2 providers and have no peering agreements. They sell Internet services to people like us.

## Broadband Connections
- Broadband connections are high-speed and always on.
- Digital Subscriber Line (DSL) runs on top of a telephone service.
- We tend to call all these boxes "modems" (e.g., DSL modem and cable modem) even though that's not what they are. It's just that the term "modem" is stuck.
- Asymmetric DSL (ADSL) has a slower upload speed than download speed.
- Symmetric DSL (SDSL) has the same upload and download speeds.
- Many DSLs use Point-to-Point Protocol over Ethernet (PPPoE) which requires a username and password provided by your ISP.
- Cable uses the Data Over Cable Service Interface Specification (DOCSIS) protocol which is similar to the Ethernet. But you can watch TV and be on the Internet at the same time.
- Cable runs through a modem supplied by your Internet Service Provider (ISP), or bought by the customer (often combined with a switch, router, WAP, and firewall).
- With cables, you might need to set up MAC clone configurations.
- Satellites are handy for more remote locations. It has latency issues.
- You can use special 802.11 setups for your ISP for remote locations.
- A Wireless Internet Service Provider (WISP) is an ISP with a network based on wireless networking.
- An Optical Network Terminal (ONT) connects fiber optics cables to other wiring such as Ethernet and phone lines by converting the signal from optical to electrical and vice versa.

## Firewalls and Servers
- All Internet connections require a client and a server.
- Client and server networks use firewalls.
- One of the primary functions of firewalls is to block ports.
- Firewalls block ports on an incoming vs. outgoing concept.
- All web servers have firewalls.
- Public-facing servers do not block individual ports. They use stateful firewalls that monitor network activity.
- Home routers don't need to allow incoming port 80 (HTTP) or port 443 (HTTPS) traffic because we don't have any web server.
- Servers must not block incoming on the ports to which they listen.

## E-Mail
- E-mail uses Simple Mail Transfer Protocol (SMTP) to send e-mail from a client to an e-mail server.
- Use Post Office Protocol 3 (POP3) or Internet Message Access Protocol (IMAP) to pull e-mail down from an e-mail server.
- SMTP uses port 25, POP3 uses port 110, and IMAP uses port 143.
- POP3 and IMAP4 are the latest versions of POP and IMAP, so if you see any of the names, it means the same thing.
- The outgoing mail server will always be SMTP.
- You should know the port numbers of each protocol, but also be aware that in the real world, these protocols can have secure versions with completely different port numbers.

## Proxy Servers
- A proxy server acts as a go-between (a proxy) between a client and a server.
- Proxy servers are application-specific (e.g., a web proxy for HTTP and HTTPS).
- Applications must know the address of the proxy server.
- Proxy servers can filter like firewalls (based on web addresses, IP addresses, ports, etc.). They can provide firewalling, check for malware, and ban bad URLs. They can also filter based on restricted content.
- In Windows, you will find proxy settings in Internet Properties > Connections > LAN settings.
- Proxy servers can do caching. They can cache static stuff on a web page and quickly load dynamic stuff as you visit them.

## Virtual Private Networks (VPNs)
- VPNs use the Internet to create a private connection to a remote network.
- We need a VPN client program that connects to a VPN server/endpoint at the remote network.
- A VPN creates an encrypted tunnel between your device and the VPN server.
- The VPN client needs to know the IP address of the VPN server to make the connection.
- Point-to-Point Tunneling Protocol (PPTP), Layer 2 Tunneling Protocol (L2TP), and IP Security (IPSec) are some common VPN protocols.
- Windows's built-in VPN client is limited. You need third-party VPN clients to get advanced features.
- VPN split tunneling lets you route some of your application or device traffic through an encrypted VPN, while other applications or devices have direct access to the Internet.

## Internet of Things (IoT)
- IoT means giving Internet capability to devices not traditionally associated with the Internet (light bulbs, thermostats, refrigerators, water heaters, door locks, garage door openers, etc.).
- The most common IoT connections are 802.11, Zigbee, and Z-wave.
- IoT requires a hub to link to the IoT devices.
- Google Home, Amazon Alexa, and Apple Siri add voice capabilities to IoT.

## Troubleshooting Internet Connections, Part 1
- Check your physical system first (link lights, cabling, ports, etc.). Verify that you have actual connectivity before blaming anything else.
- Know your network! Know your network ID, router, and DNS server.
- Run the `ipconfig /all` command in Windows to get important network information.
- Know your Internet connectivity!
- Run `tracert` (Windows) or `traceroute` (Linux/Mac) to trace the path that packets take from your computer to a destination (like a website or another networked device).
- You need to run `tracert`/`traceroute` when everything is good. So that you know what it looks like, and when something bad happens, you can deal with it.
- Use the `ping` command to test the connection between two systems.
- You can use the `ping` command with an FQDN to test your DNS server. It doesn't matter if it gets timed out. If you get an IP address in return, that means the DNS server is working.