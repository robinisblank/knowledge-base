# The Internet

## Telnet and SSH

## Remote Desktop Connections

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