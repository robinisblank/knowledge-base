# The Internet

## Telnet and SSH
- The Telnet and Secure Shell (SSH) protocols provide command-line access to remote systems.
- PuTTY is a free and open-source terminal emulator application that allows users to connect to remote systems. It supports several network protocols, including Telnet and SSH.
- Telnet runs on TCP port 23; SSH runs on TCP port 22.
- Telnet is unencrypted; SSH is encrypted.

## Remote Desktop Connections
- Remote Desktop Protocol (RDP) is a proprietary Windows protocol that enables remote access to and control of a computer over a network. It uses port 3389.
- Remote Assistance is designed for support scenarios. It allows someone (e.g., a tech support person) to view or control another user's computer with the user's permission. Both parties are actively involved in the session, making it ideal for troubleshooting and guidance. It’s available on all editions of Windows.
- Remote Desktop is for remote work access. It lets one user fully control another machine remotely, logging into it as if they were physically at that computer. It’s a solo session without the other user's input, suitable for remote work or accessing files/programs on a primary machine from another location. Only Pro editions and above can host Remote Desktop sessions.
- You'll find Remote Assistance and Remote Desktop settings under the Remote tab in System Properties.
- Remote Desktop Connections is the program in Windows that allows users to connect to a computer remotely and control it as if they were sitting in front of it.
- The Remote Desktop Protocol (RDP) client is available on all Windows editions, allowing any Windows device to initiate a remote session. However, only the Pro, Enterprise, and Education editions include the Remote Desktop host, which allows other devices to connect to them. This has been the case since at least Windows 7, where the Home editions could initiate connections but not accept incoming RDP connections.
- Virtual Network Computing (VNC) is a cross-platform screen-sharing system created to remotely control another computer.
- TightVNC is a free and open-source remote desktop software based on the VNC protocol.

## The World Wide Web

## Fire Transfer Protocol (FTP)

## Proxy Servers
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/15 - The Internet](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/15%20-%20The%20Internet.md)
- A proxy server acts as a go-between (a proxy) between a client and a server.
- Proxy servers are application-specific (e.g., a web proxy for HTTP and HTTPS).
- Applications must know the address of the proxy server.
- Proxy servers can filter like firewalls (based on web addresses, IP addresses, ports, etc.). They can provide firewalling, check for malware, and ban bad URLs. They can also filter based on restricted content.
- In Windows, you will find proxy settings in Internet Properties > Connections > LAN settings.
- Proxy servers can do caching. They can cache static stuff on a web page and quickly load dynamic stuff as you visit them.

## Virtual Private Networks (VPNs)
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/15 - The Internet](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/15%20-%20The%20Internet.md)
- VPNs use the Internet to create a private connection to a remote network.
- We need a VPN client program that connects to a VPN server/endpoint at the remote network.
- A VPN creates an encrypted tunnel between your device and the VPN server.
- The VPN client needs to know the IP address of the VPN server to make the connection.
- Point-to-Point Tunneling Protocol (PPTP), Layer 2 Tunneling Protocol (L2TP), and IP Security (IPSec) are some common VPN protocols.
- Windows's built-in VPN client is limited. You need third-party VPN clients to get advanced features.
- VPN split tunneling lets you route some of your application or device traffic through an encrypted VPN, while other applications or devices have direct access to the Internet.

## Internet of Things (IoT)
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/15 - The Internet](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/15%20-%20The%20Internet.md)
- IoT means giving Internet capability to devices not traditionally associated with the Internet (light bulbs, thermostats, refrigerators, water heaters, door locks, garage door openers, etc.).
- The most common IoT connections are 802.11, Zigbee, and Z-wave.
- IoT requires a hub to link to the IoT devices.
- Google Home, Amazon Alexa, and Apple Siri add voice capabilities to IoT.

## Troubleshooting Internet Connections
- Same lecture as in [/CompTIA A+ Core 1 (220-1101) - Total Seminars/15 - The Internet](/CompTIA%20A+%20Core%201%20(220-1101)%20-%20Total%20Seminars/15%20-%20The%20Internet.md)
- Check your physical system first (link lights, cabling, ports, etc.). Verify that you have actual connectivity before blaming anything else.
- Know your network! Know your network ID, router, and DNS server.
- Run the `ipconfig /all` command in Windows to get important network information.
- Know your Internet connectivity!
- Run `tracert` (Windows) or `traceroute` (Linux/Mac) to trace the path that packets take from your computer to a destination (like a website or another networked device).
- You need to run `tracert`/`traceroute` when everything is good. So that you know what it looks like, and when something bad happens, you can deal with it.
- Use the `ping` command to test the connection between two systems.
- You can use the `ping` command with an FQDN to test your DNS server. It doesn't matter if it gets timed out. If you get an IP address in return, that means the DNS server is working.

## Browser Security