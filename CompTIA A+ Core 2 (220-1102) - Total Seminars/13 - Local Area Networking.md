# Local Area Networking

## Introduction to TCP/IP
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/13 - Local Area Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md)
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

## Network IDs and Subnet Masks
- Use the Network and Sharing Center to set up network information.
- In Windows, Control Panel > Network and Internet > Network and Sharing Center > Change adapter settings > Select the adapter and open its properties > Double-click "Internet Protocol Version 4 (TCP/IPv4)" or open its Properties.
- Under the General tab in the "Internet Protocol Version 4 (TCP/IPv4)" properties, you can enter static IP information (IP address, subnet mask, and default gateway) after checking the "Use the following IP address" option.
- When you manually set the IP address, it's called a static IP address.

## Special IP Addresses
- Class A address range: `1.x.x.x` - `126.x.x.x`
- Class B address range: `128.A.x.x` - `191.A.x.x`
- Class C address range: `192.A.A.x` - `223.A.A.x`
- Class D (multicast) address range: `224.A.A.A` - `239.A.A.A`
- Class E (reserved) address: `240.A.A.A` - `255.A.A.A` (excluding `255.255.255.255`)
- A private IP address is an IP address used within a private network (such as a home, office, or internal network) that is not routable on the public Internet. These addresses are reserved for internal use and allow devices within the private network to communicate with each other.
- There are three sets of private IP addresses:
	1. Class A (`10.x.x.x`)
	2. Class B (`172.16.x.x` - `172.31.x.x`)
	3. Class C (`192.168.A.x`)
- `A` means assigned, and `x` means you can do anything with that octet. This isn't standard networking terminology and is only used for note purposes.
- Devices using private IP addresses access the Internet through a router with NAT, which translates private addresses to a public IP address.
- A computer uses a loopback IP address (`127.0.0.1`) to refer to itself. Packets sent to this address never reach the network but are looped through the NIC only.
- The loopback address allows for a reliable method of testing the functionality of an Ethernet card and its drivers and software without a physical network.
- In Windows, when we run the `ping` command, it pings four times, but with the `-t` option, it keeps pinging the specified host until stopped.
- The `ping` command keeps pinging by default in Linux and macOS.

## Network Address Translation (NAT)
- A gateway connects networks, while a router delivers data within a network.
- Historically, gateways and routers have been separate devices. However, it's becoming more common for their functions to be combined and simply called a router.
- Without NAT, all computers within a LAN will have easy-to-find public IP addresses. If somebody bypasses the firewall, any computer will be publicly visible. Another issue is that you're eating a lot of public IP addresses.
- With NAT, a router will still have a public IP address, but the computers within a LAN will use private IP addresses.
- NAT saves public IP addresses as devices on different local networks can have the same private IP address.
- If a computer within an internal network wants to communicate with a computer in an external network, the packet will go through the router, and NAT will replace the computer's private IP with its public IP before sending the packet, and vice versa when receiving a packet.
- Networks using NAT are invisible to the Internet because NAT hides the private IP addresses of devices within a local network. From the perspective of external systems, the traffic appears to originate from the public IP of the router, not from the internal devices. This provides privacy and security, as external systems cannot directly access or identify individual devices within the private network.
- All gateway routers are NAT-enabled by default.
- Normally, NAT-enabled routers have a public IP address on their WAN interface and a private IP address on their LAN interface.

## Dynamic IP Addressing
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/13 - Local Area Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md)
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
- Under the Alternate Configuration tab in the "Internet Protocol Version 4 (TCP/IPv4)" properties, you can also put static IP information that you want instead of APIPA when you can't find a DHCP server after checking the "User configured" option. You should be careful and know why you're doing this.

## Working with Connections
- In Windows, the `netstat` command displays protocol statistics and current TCP/IP network connections.
- The `-n` switch with the `netstat` command displays addresses and port numbers in numerical form.
- The `-a` switch with the `netstat` command displays all connections and listening ports.
- Windows uses port 445 for file and print sharing over a network.
- Use TCPView from [Sysinternals](https://learn.microsoft.com/en-in/sysinternals/) by Mark Russinovich to monitor active network connections in real time.

## Understanding DNS
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/13 - Local Area Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md)
- The Domain Name System (DNS) is the Internet's phonebook. It resolves Fully Qualified Domain Names (FQDNs) (e.g., www.youtube.com) to IP addresses (e.g., `142.250.194.206`).
- DNS replaced the hosts file. A hosts file is a plain text file that maps hostnames to IP addresses.
- When you enter a domain name into a browser, it sends a request to a DNS resolver, which first checks its cache. If the IP address isn't cached, the resolver queries a root server, then the appropriate Top-Level Domain (TLD) server, and finally the authoritative server for that domain. The authoritative server responds with the correct IP address, which is returned to your browser to connect to the website's server.
- FQDNs have a 255-character limit with dots included.
- Domain-based Message Authentication, Reporting, and Conformance (DMARC) enter records of domains to avoid spoofing.
- DomainKeys Identified Mail (DKIM) enables the sender to sign their message and verify their identity.
- Sender Policy Framework (SPF) allows mail servers to verify that the sender of an email is authorized to send mail from the domain listed.

## Working with DNS
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/13 - Local Area Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md)
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

## Windows Naming
- Windows Naming refers to the way Windows organizes and identifies computers on a network. Each computer is assigned a unique name for identification and communication within a network, whether in a workgroup or a domain.
- Windows Naming, specifically through systems like NetBIOS/NetBT or DNS, is primarily designed for LANs. It allows devices within the same LAN to identify and communicate with each other using human-readable names (like computer names) rather than relying on IP addresses.
- When you install Windows, you will need to give the computer a name.
- Every Windows system is a member of a Workgroup or Domain.
- A workgroup is a decentralized network model used in small local networks where each computer manages its own resources. There is no central authority or server.
- A domain is a centralized network model where resources, such as user accounts, permissions, and security policies, are managed from a centralized server.
- Domains are typically managed by Windows Server with Active Directory (AD).
- Active Directory is a directory service developed by Microsoft, used for managing domain networks by storing user information, security settings, and resources in a structured database.
- In System Properties, you can change the computer name, workgroup, or domain.

## Working with Workgroups
- NetBIOS/NetBEUI was the network protocol originally used by Microsoft to share stuff.
- Network Basic Input/Output System (NetBIOS) is a network protocol that allows applications on different computers to communicate within a LAN. It provides services like name resolution (mapping computer names to IP addresses) and session management.
- NetBIOS Extended User Interface (NetBEUI) is an enhanced version of NetBIOS, optimized for small networks. It’s a fast, simple, and non-routable protocol, meaning it’s only suitable for small, local networks without the need for routing between networks.
- NetBIOS over TCP/IP (NetBT) allows NetBIOS services to run over the more scalable and Internet-compatible TCP/IP protocol. It enables NetBIOS to function in larger networks and WANs, such as the Internet.
- NetBT is commonly used in Windows networks to maintain backward compatibility with legacy applications that rely on NetBIOS.
- Common Internet File System (CIFS) is an older version of the Server Message Block (SMB) protocol, used primarily for sharing files, printers, and communication between computers on a network.
- CIFS was used in early versions of Windows to allow devices to access shared resources across a network, regardless of the OS.
- SMB is a network file sharing protocol that allows applications or users to read and write to files on a remote server, as well as perform other networked operations like printer sharing.
- SMB is more advanced than CIFS and is still widely used today, especially in modern Windows networks, Linux (via Samba), and macOS.
- All Windows computers on a single LAN will automatically see each other if they are in the same workgroup.
- In Windows, `whoami` is a utility that can be used to get user name and group information along with the respective security identifiers (SID), claims, privileges, logon identifier (logon ID) for the current user on the local system. I.e. who is the current logged on user? If no switch is specified, tool displays the user name in NTLM format (domain\username).
- Microsoft best practices recommend sharing resources with everyone with read/write permission level, not using share permissions, and instead use NTFS permissions.
- With workgroups, users often create identical accounts with the same passwords across different computers to simplify access, which is insecure. This practice is generally acceptable for home networks but weak in enterprise environments, where central management with Active Directory in a domain environment provides a more secure and manageable solution.

## Working with Active Directory
- An Active Directory Domain requires a Domain Controller (dedicated server) with Windows Server software installed.
- We have domain accounts instead of local user accounts.
- We use domain names instead of computer names.
- `<name>.local` is a common domain name for internal domain networks.
- Active Directory User and Computers is the program used to add computers, create users and groups, Organizations Units (OUs), add users to groups, etc.
- Domain Admin has the power to add any computer to the domain.
- We use OUs and Forests to organize members of a domain.
- Domain supports many security policies, login scripts, and home folder redirection.
- Windows Domains support single sign-on.
- In a domain, you can share resources based on domain accounts.

## Windows Sharing with macOS and Linux
- LAN Manager (LM) is a discontinued network OS from Microsoft that allows users to connect PCs on a network.
- Samba is a file and print-sharing service that uses the SMB protocol. It allows file and printer sharing across different OSes.
- Samba comes with Linux and macOS to connect to Windows networks.
- You need to know the workgroup or domain name and give the system a computer name.

## The `net` Command
- The `net` command in Windows is used to manage network resources.
- The `net` command by itself displays all the net commands.
- The `net view` command displays a list of resources being shared on a computer. When used without options, it displays a list of computers in the current domain or network.
- The `net share` command makes a server's resources available to network users. When used without options, it lists information about all resources being shared on the computer. For each resource, Windows reports the device name(s) or pathname(s) and a descriptive comment associated with it.
- The `net use` command connects/disconnects a computer to a shared resource. When used without options, it lists the computer's connections.
- The `net user` command creates and modifies user accounts on computers. When used without switches, it lists the user accounts for the computer. The user account information is stored in the user accounts database.
- The `net help` command displays information about a net command.
- Different versions of Windows often require tweaks to get this command working.

## Routers
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/13 - Local Area Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md)
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
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/13 - Local Area Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md)
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

## Firewall Configuration
- Firewall is a security device or software designed to monitor and control incoming and outgoing network traffic. It acts as a barrier between trusted internal networks and untrusted external networks, blocking unauthorized access and allowing permitted traffic based on security rules.
- The edge of a network, commonly the gateway router is an obvious place to put a firewall.
- Access Control List (ACL) is a set of rules that controls access to network resources by defining which users, IP addresses, or types of traffic are allowed or denied access.
- The Principle of Least Privilege (PoLP) is a policy that limits access to the minimum required amount of privileges and is a core component of access control.
- Content can be filtered with deny and allow lists (previously blacklist and whitelist).
- Blacklist denies access to prohibited entities, and whitelist allows access to only approved entities. These entities can be applications, services, etc.
- Stateless firewalls block using fixed criteria such as port number, time of day, URL, etc.
- Stateful firewalls block based on the activity at that moment (e.g., too many pings).
- Access Policy outlines the rules and guidelines for accessing network resources. It can include details on who can access specific systems, under what conditions, and with what permissions.
- Demilitarized Zone (DMZ) or Screened Subnet is a section of a network that acts as a buffer between the internal network and the public Internet. The DMZ typically hosts public-facing servers (e.g., web servers) that need to communicate with external users, while minimizing the risk of unauthorized access to the internal network. Firewalls isolate the DMZ from both the internal network and the Internet, allowing controlled access.
- A DMZ on a home router is not the same as a real DMZ because the router alone does not separate the host from the internal network. A real DMZ is separated from the internal network by a firewall, while a DMZ host on a home router is not.

## Windows Firewall
- Network/edge firewall is usually on the router. However, a host firewall is used on individual systems.
- Windows Defender Firewall is a host-based software firewall that comes with Windows.
- Host firewalls protect systems using host features such as file names or process IDs.
- Windows Defender Firewall has settings for Domain networks, Private networks, and Guest or public networks.
- Network discovery is a process that helps devices and computers on a network find each other and communicate. It's a great thing to have on your home network, but a terrible thing on a guest or public network.
- Advanced settings is where you can do monitoring, and where all the rules are.
- An Exception is when you allow something that was being blocked to pass through.
- You can create exceptions manually if needed by creating inbound/outbound rules.
- You won't need to create exceptions manually if you are careful when Windows Defender Firewall pops up and shows what is being blocked and if you want to allow it.

## Port Forwarding
- With NAT, only the router has the public IP address, and devices within the internal network have private IP addresses. Because of this, these devices are not accessible from the Internet directly.
- Port forwarding is a feature on NAT-enabled routers that directs incoming traffic on a specific port to a designated device on the internal network. For example, accessing a security camera from outside the home.
- We often use nonstandard port numbers for security reasons.
- Dynamic DNS (DDNS) allows you to map a dynamic IP address to a consistent hostname, allowing your router to be more easily accessed from different locations on the Internet.
- We can use DDNS to give DNS names to port forwarded devices.
- The only time you're going to use DDNS is when you have a NAT-enabled router, which is very common these days, and when you're doing port forwarding that motivates you to know your WAN IP address.

## Advanced Router Configuration
- Quality of Service (QoS) is a network feature that manages and prioritizes bandwidth allocation based on specific criteria, such as IP address, MAC address, port number, or application type to improve the network performance.
- Link Layer Discovery Protocol (LLDP) is a protocol used by devices (like switches, routers, and computers) on the same local network to advertise information about themselves.
- Microsoft uses LLDP for network discovery.
- Universal Plug and Play (UPnP) enables devices on a network to automatically discover each other and establish connections.
- Simple Network Management Protocol (SNMP) is a protocol for monitoring and managing devices on IP networks.

## Virtual LANs (VLANs)
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/13 - Local Area Networking](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md)
- VLANs enable network segmentation without adding hardware. It electronically turns a single switch into two or more switches. Devices connected to ports of different VLANs will not even see each other.
- Configure VLAN-capable switches via IP address and web. Switches don't have IP addresses because they work with MAC addresses, but if connected to a router, it can be assigned an IP address by the DHCP.
- Managed switches have VLAN capabilities and many features that just don't come with unmanaged switches.
- If you plug in devices into a switch and they are not seeing each other, you might have some VLAN configurations.
- Port security enables features like disabling ports, reporting unauthorized devices, etc. if any device with a MAC address that the switch doesn't recognizes tries to connect.
- Software Defined Networking (SDN) reduces manual configuration and reconfiguration that was needed in traditional networks. The data plane is separated from the control plane. We still have programmable switches, but there is a separate controller machine that enables ease of access and central management. It allows the network to be more scalable and efficient.