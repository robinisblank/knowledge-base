# Local Area Networking

## [Introduction to TCP/IP](CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md#Introduction%20to%20TCP/IP)

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

## [Dynamic IP Addressing](CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md#Dynamic%20IP%20Addressing)

## Working with Connections
- In Windows, the `netstat` command displays protocol statistics and current TCP/IP network connections.
- The `-n` switch with the `netstat` command displays addresses and port numbers in numerical form.
- The `-a` switch with the `netstat` command displays all connections and listening ports.
- Windows uses port 445 for file and print sharing over a network.
- Use TCPView from [Sysinternals](https://learn.microsoft.com/en-in/sysinternals/) by Mark Russinovich to monitor active network connections in real time.

## [Understanding DNS](CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md#Understanding%20DNS)

## [Working with DNS](CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md#Working%20with%20DNS)

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

## [Routers](CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md#Routers)

## [Basic Router Configuration](CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md#Basic%20Router%20Configuration)

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

## [Virtual LANs (VLANs)](CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/13%20-%20Local%20Area%20Networking.md#Virtual%20LANs%20(VLANs))