# Local Area Networking

## Introduction to TCP/IP
- TCP/IP was adopted as a protocol for the Advanced Research Projects Agency Network (ARPANET) and what was to become the Internet.
- IPv4 addresses have four octets ranging 0-255 separated by three dots.
- An IP address does two things:
	1. It identifies which LAN you are part of.
	2. It gives you a unique host ID.
- Class A address: `A.x.x.x`
- Class B address: `A.A.x.x`
- Class C address: `A.A.A.x`
- `A` means assigned, and `x` means you can do anything with that octet. This isn't standard networking terminology and is only used for note purposes.
- Now, each ethernet frame consists of a destination MAC address, a source MAC address, a destination IP address, a source IP address, a data payload, and an FCS.
- IP addresses with a 0 at the end represent a network ID. It identifies an entire LAN.
- Subnet masks are used to differentiate IP addresses on LANs vs. outside traffic, and are only used for IPv4 addresses.
- `255.255.255.0` is a common subnet mask. Every octet masked with `255` is part of the network address.
- Two IP addresses follow the subnet mask when octets masked with `255` are the same and octets masked with `0` are different.
- If two IP addresses follow the subnet mask, they are from the same LAN. If not, then from different LANs.
- The router typically has an IP address ending in `.1` (e.g., `192.168.4.1`) and acts as the "default gateway" for devices in the LAN.
- You need to give three things to a computer if you want it to be on the Internet:
	1. IP address
	2. Subnet mask
	3. Default gateway

## Dynamic IP Addressing
- Dynamic Host Configuration Protocol (DHCP) automatically and dynamically assigns IP information to hosts.
- Gateway routers commonly are DHCP servers for their internal LANs. But a DHCP server can also be a separate computer.
- Whenever a computer boots/reboots in a network, it asks for IP information from the DHCP server. The DHCP server will hand them an IP address, a subnet mask, a default gateway, etc.
- Typically, you will have a different IP address each time you connect to the same or different network. However, in some cases, you may keep the same IP address on a network if the DHCP lease hasn't expired or the server is configured to reserve a specific IP address for your device.
- In Windows, Control Panel > Network and Internet > Network and Sharing Center > Change adapter settings > Select the adapter and open its properties > Double-click "Internet Protocol Version 4 (TCP/IPv4)" or open its Properties.
- Under the General tab in the "Internet Protocol Version 4 (TCP/IPv4)" properties, you can either enter static IP information (IP address, subnet mask, and default gateway) after checking the "Use the following IP address" option or check the "Obtain an IP address automatically" option, which simply means you want to use DHCP.
- You can see the IP address of your DHCP server by running the command `ipconfig /all` in Windows.
- DHCP servers are just computers that can go down sometimes. Almost every OS has Automatic Private IP Addressing (APIPA). It is a fallback in case you (a DHCP client) cannot find a DHCP server.
- Under the Alternate Configuration tab in the "Internet Protocol Version 4 (TCP/IPv4)" properties, you will find APIPA.
- By default, APIPA will always give a `169.254.x.x` address. You pretty much can do anything with this IP address, but you cannot connect to the Internet because your router doesn't use APIPA, it has a fixed IP address.
- Whenever you get into a situation where you have limited connectivity. You are able to talk to other nodes in the network but are not able to run Google. Check if you have an APIPA address (in Windows, run the `ipconfig` command). If yes, then you have a DHCP server problem.
- The `/release` switch with the `ipconfig` command releases the IPv4 address for the specified adapter.
- The `/renew` switch with the `ipconfig` command renews the IPv4 address for the specified adapter.
- Built-in troubleshooter will disable and enable the network card, release and renew, and it will make some queries to the Internet to make sure you have Internet connectivity.
- Under the Alternate Configuration tab in the "Internet Protocol Version 4 (TCP/IPv4)" properties, you can also put static IP information that you want instead of APIPA when you can't find a DHCP server after checking the "User configured" option. You should be careful and know why you are doing this.

## IPv6
- `172.16.254.1` is an example of an IPv4 (Internet Protocol version 4) address. We can have about 4.3 billion addresses with IPv4. We thought it would be sufficient. But we were wrong and we ran out of them.
- `2001:0db8:85a3:0000:0000:8a2e:0370:7334` is an example of an IPv6 (Internet Protocol version 6) address. With IPv6, we can have 340 undecillion addresses. It has 8 groups separated by 7 colons.
- IPv6 uses 128-bit addresses, which is much larger than the 32-bit addresses used by IPv4.
- We can get rid of leading zeroes in an IPv6 address. For example, `fe80:0000:0000:0123:0000:0000:0000:1234` can be written as `fe80:0:0:123:0:0:0:1234`.
- We can replace one or more consecutive zeroes with a double colon. This can only be done once in an address to avoid ambiguity. For example, `fe80:0:0:123:0:0:0:1234` can be written as `fe80:0:0:123::1234`.
- With IPv4, you only had one IP address. However, with IPv6, you will have a minimum of two separate IP addresses: Link-local address, and Global unicast address (Internet address).
- Link-local address always starts with `fe80` followed by `0000:0000:0000`. The last half of the address is automatically generated by your system.
- Global unicast address is brought down by the router. The router gives the first half and the second half is automatically generated by your system.
- Run the `ipconfig` command in Windows to see your Link-local address (labeled as "Link-local IPv6 Address") and Global unicast address (labeled as "IPv6 Address" and "Temporary IPv6 Address").
- Depending on OS, your system will have one main IPv6 address and some temporary IPv6 addresses that will rotate. This is a security feature with IPv6.
- IPv6 addresses have prefixes instead of subnet masks.
- The `/release6` switch with the `ipconfig` command releases the IPv6 address for the specified adapter.
- The `/renew6` switch with the `ipconfig` command renews the IPv6 address for the specified adapter.

## Port Numbers
- Data transmission happens between a client and a server on the Internet.
- Your system can run multiple applications, and only the IP address is not enough to keep track of them.
- An IP address gets you to the correct computer, but a port number gets you to the correct application.
- Port numbers go from 0-65535.
- The packet contains the destination port number and the source port number.
- Destination IP address swaps with source IP address, and destination port number swaps with source port number when the packet reaches the destination.
- Source port numbers are spun up automatically by the OS.
- In Windows, Resource Monitor shows connections on a system. TCP Connections under the Network tab.
- There are three types of port numbers:
	1. Well-known ports: 0-1023
	2. Registered ports: 1024-49151
	3. Dynamic/ephemeral ports: 49152-65535
- Servers listen for well-known port numbers.
- The source port number is an ephemeral port number.
- FTP uses TCP by default, with ports 20 and 21.

| Port    | Protocol                                                                |
| ------- | ----------------------------------------------------------------------- |
| 20/21   | File Transfer Protocol (FTP)                                            |
| 22      | Secure Shell (SSH)                                                      |
| 23      | Telnet                                                                  |
| 25      | Simple Mail Transfer Protocol (SMTP)                                    |
| 53      | Domain Name System (DNS)                                                |
| 67/68   | Dynamic Host Configuration Protocol (DHCP)                              |
| 80      | Hypertext Transfer Protocol (HTTP)                                      |
| 110     | Post Office Protocol v3 (POP3)                                          |
| 137/139 | Network Basic Input/Output System (NetBIOS)/NetBIOS over TCP/IP (NetBT) |
| 143     | Internet Mail Access Protocol (IMAP)                                    |
| 161/162 | Simple Network Management Protocol (SNMP)                               |
| 389     | Lightweight Directory Access Protocol (LDAP)                            |
| 427     | Service Location Protocol (SLP)                                         |
| 443     | Hypertext Transfer Protocol Secure (HTTPS)                              |
| 445     | Server Message Block (SMB)/Common Internet File System (CIFS)           |
| 3389    | Remote Desktop Protocol (RDP)                                           |

## TCP, UDP, and ICMP
- A protocol is a set of rules that allows different devices to communicate with each other despite their differences.
- Transmission Control Protocol/Internet Protocol (TCP/IP) is a communication protocol suite where IP handles the addressing and routing of data across networks, and TCP ensures reliable, ordered delivery of that data. Together, they form the foundation of how devices communicate over the Internet.
- Transmission Control Protocol (TCP) is connection-based. It establishes a connection between two devices before data is sent.
- User Datagram Protocol (UDP) is connectionless. It allows datagrams to be sent without establishing a connection between devices.
- Internet Control Message Protocol (ICMP) is a single packet only (e.g., the `ping` command), and not like TCP and UDP which send multiple packets.
- Protocol Data Unit (PDU) refers to the data chunk at different layers of the networking model. Ethernet frame > IP packet > TCP segment/UDP datagram.

## Understanding DNS
- The Domain Name System (DNS) is the Internet's phonebook. It resolves Fully Qualified Domain Names (FQDNs) (e.g., www.youtube.com) to IP addresses (e.g., `142.250.194.206`).
- DNS replaced the hosts file. A hosts file is a plain text file that maps hostnames to IP addresses.
- When you enter a domain name into a browser, it sends a request to a DNS resolver, which first checks its cache. If the IP address isn't cached, the resolver queries a root server, then the appropriate Top-Level Domain (TLD) server, and finally the authoritative server for that domain. The authoritative server responds with the correct IP address, which is returned to your browser to connect to the website's server.
- FQDNs have a 255-character limit with dots included.
- Domain-based Message Authentication, Reporting, and Conformance (DMARC) enter records of domains to avoid spoofing.
- DomainKeys Identified Mail (DKIM) enables the sender to sign their message and verify their identity.
- Sender Policy Framework (SPF) allows mail servers to verify that the sender of an email is authorized to send mail from the domain listed.

## Working with DNS
- It's very common for the DHCP to provide both IP addresses and DNS.
- Use the `ipconfig /all` command to see a system's DNS servers.
- In Windows, Control Panel > Network and Internet > Network and Sharing Center > Change adapter settings > Select the adapter and open its properties > Double-click "Internet Protocol Version 4 (TCP/IPv4)" or open its Properties.
- Under the General tab in the "Internet Protocol Version 4 (TCP/IPv4)" properties, you can configure DNS manually after checking the "Use the following DNS server addresses" option.
- You can statically configure DNS and still use DHCP for IP addressing.
- `8.8.8.8` and `8.8.4.4` are Google's public DNS servers.
- `nslookup` is a network administration command-line tool for querying the DNS.
- When you face a DNS problem, manually configure DNS, use alternate public DNS servers, or call your administrator to fix the issue.
- DNS stores many kinds of records:
	- A records track IPv4 address system names.
	- AAAA records track IPv6.
	- MX records are used by mail servers.
	- Canonical Name (CNAME) records track multiple names of the same IP address.

## Routers
- Routers filter and forward traffic based on IP addresses.
- A routing table determines where to filter or forward IP packets.
- Every routing table has a default gateway/route that sends all data unless otherwise specified.
- Some routers, especially enterprise-grade ones, are configured via a console port. This involves connecting a serial cable (often a DB-9 connector or an RJ-45 modified for serial use) to a laptop using a terminal program. The cable is called yost/rollover cable.
- Small Office/Home Office (SOHO) routers are common for personal use, often combining several devices into one box (router, switch, and WAP).
- Configuration is done through a web interface for most SOHO routers.
- When a device connects to a SOHO router, it passes out a DHCP range (scope) via DHCP (often `192.168.0.x` or `192.168.1.x`). Your device is automatically assigned an IP address within this range.
- If you don't receive a DHCP address and instead get an APIPA address like `169.254.x.x`, it means the router isn't providing DHCP, and you'll need to manually configure your IP address to match the router's DHCP range.
- In Windows, run the `ipconfig` command, if you see an address like `192.168.0.x` or `192.168.1.x`, it confirms that the router is properly assigning IP addresses.
- You access the router by typing the default gateway address (often `192.168.0.1` or `192.168.1.1`) in a browser and make configurations.

## Basic Router Configuration
- SOHO routers work out of the box, which is bad because we need to deal with many default configurations that can risk the network's security.
- Avoid default settings for basic configurations (IP, SSID, password, etc.).
- The WAN side of the router refers to the connection between the router and the Internet Service Provider (ISP). Most routers are DHCP clients on the WAN side and automatically receive an IP address from the ISP.
- In your WAN settings, if Dynamic IP (DHCP) is enabled, the ISP assigns an IP address dynamically to the router. Static IP requires you to manually enter it, which is provided by your ISP.
- The LAN side refers to the internal network managed by the router. The router is the DHCP server for devices on the LAN.
- In your LAN settings, you can change your router's IP address, and it will automatically change the IP addresses of the devices on that LAN.
- In your DHCP server settings, you can configure the range of the IP address pool. The devices are assigned IP addresses from this pool. Keep the range short so that only a limited number of devices can connect.
- DHCP lease time determines how long a device can use an IP address before it needs to request a new one.
- DHCP reservation allows a specific device (identified by its MAC address) to always receive the same IP address from the DHCP server.
- Do not reserve IP addresses within the DHCP pool range, as it can cause unnecessary complexity. Instead, assign static IP addresses outside the DHCP pool for devices that need fixed IP addresses (e.g., servers and printers).
- Always change the default username and password to access the router’s settings.
- Local management allows you to control who can access the router's web interface from inside the network. Limit access to specific devices (based on their MAC addresses) for added security.
- Remote management allows users to configure the router from outside the local network. This is highly discouraged for security reasons.
- By default, the router will pass on the DNS settings provided by the ISP to the devices in the network. However, you can manually enter DNS servers (e.g., Google's public DNS `8.8.8.8`) if you prefer not to use the ISP's DNS.
- Keeping router firmware up to date is crucial for security and performance.

## Virtual LANs (VLANs)
- VLANs enable network segmentation without adding hardware. It electronically turns a single switch into two or more switches. Devices connected to ports of different VLANs will not even see each other.
- Configure VLAN-capable switches via IP address and web. Switches don't have IP addresses because they work with MAC addresses, but if connected to a router, it can be assigned an IP address by the DHCP.
- Managed switches have VLAN capabilities and many features that just don't come with unmanaged switches.
- If you plug in devices into a switch and they are not seeing each other, you might have some VLAN configurations.
- Port security enables features like disabling ports, reporting unauthorized devices, etc. if any device with a MAC address that the switch doesn't recognizes tries to connect.
- Software Defined Networking (SDN) reduces manual configuration and reconfiguration that was needed in traditional networks. The data plane is separated from the control plane. We still have programmable switches, but there is a separate controller machine that enables ease of access and central management. It allows the network to be more scalable and efficient.

## Network Troubleshooting
- **No Connectivity**:
	- Check physical connections. Make sure patch cables are properly plugged in and link lights are on.
	- For DHCP clients, check if the IP address is assigned correctly.
	- For static IP addresses, check for IP conflicts.
	- Use ping to test connectivity.
- **Limited Connectivity**:
	- If you have an APIPA address (`169.254.x.x`), there's a DHCP issue.
	- If the IP range changes unexpectedly, someone might have connected a rogue DHCP server.
	- A rogue DHCP server is the one that is not authorized to provide IP addresses to device on your network.
- **Intermittent Connectivity**:
	- Check for physical damage to the cable.
	- Nearby equipment could be interfering with the cable.
- **Unavailable Resources**:
	- Ping the resource to test if it's reachable.
	- Ensure you can access the system hosting the resource.
	- Confirm you have the correct permissions to access the resource.
	- Make sure the resource is properly shared and configured.
- **Slow Transfer/Network Speeds**:
	- Use Task Manager to monitor network card usage and identify bandwidth hogs.
	- Manage applications that consume excessive bandwidth.
	- Configure Quality of Service (QoS) on routers or switches to prioritize critical network traffic.