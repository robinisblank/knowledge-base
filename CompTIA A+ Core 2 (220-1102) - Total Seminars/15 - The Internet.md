# The Internet

## Telnet and SSH
- The Telnet and Secure Shell (SSH) protocols provide command-line access to remote systems.
- PuTTY is a free, open-source terminal emulator application that allows users to connect to remote systems. It supports several network protocols, including Telnet and SSH.
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
- TightVNC is a free, open-source remote desktop software based on the VNC protocol.

## The World Wide Web
- The World Wide Web (WWW or simply the Web) is a system of interconnected documents and resources linked by hyperlinks and accessed over the Internet. It uses the HTTP/HTTPS protocol to allow users to view and interact with web pages, which consist of text, images, videos, and other multimedia.
- Web browsers (e.g., Chrome, Firefox, and Safari) are software applications that act as gateways to the World Wide Web. They interpret the code of web pages (HTML, CSS, JavaScript) and display it in a user-friendly format, allowing users to navigate and interact with the web's vast content. In essence, browsers bring the World Wide Web to life on users' screens.
- HTTP uses port 80 and is not secure.
- HTTPS uses port 443 and certificates to make a secure connection.
- A website certificate (aka SSL/TLS certificate) is a digital file that verifies a website's identity and encrypts connections between the website and the user's browser.
- Secure Sockets Layer (SSL) and Transport Layer Security (TLS) are encryption protocols used to protect and encrypt data transmitted between a user’s browser and a website.
- Certificates let you know what websites are trusted (safe) and untrusted (unsafe).
- Make sure to recognize typical certificate errors.
- See what it looks like to connect to an insecure website: http://neverssl.com
- Check out an example of each type of certificate warning: https://badssl.com

## Fire Transfer Protocol (FTP)
- FTP is a standard protocol used to transfer files between computers on a network.
- You need an FTP client; almost all browsers are also FTP clients.
- FileZilla is a free, open source FTP software tool that allows users to set up FTP servers or connect to other FTP servers in order to exchange files.
- In active mode (traditional FTP mode), FTP uses TCP port 21 for the control channel and TCP port 20 for the data channel.
- In active mode, for the control channel, the client connects to the server's TCP port 21, and for the data channel, the client opens a listening port on its side, and the server connects back to the client’s specified port from its own TCP port 20.
- Since the client must accept incoming connections on its port, active mode FTP can be challenging with firewalls and NAT, as these often block incoming connections.
- In passive mode, FTP still uses TCP port 21 for the control channel, but the data channel is assigned a random high port chosen by the server (not port 21).
- In passive mode, for the control channel, the client connects to the server's TCP port 21, and for the data channel, the server opens a random high port (not port 21) and informs the client of this port through the control channel. The client then initiates the data connection to this port on the server.
- Passive mode solves firewall and NAT issues by having the client initiate all connections, so it doesn’t require incoming connections from the server.
- In active mode, the server tries to connect back to the client’s data port, which can cause issues if the client is behind a NAT or firewall. Port triggering helps by dynamically opening up specific inbound ports only when a particular outbound connection is detected. For FTP, port triggering temporarily opens the client’s port to allow the server’s incoming connection on the data channel, making the traditional active FTP mode work with firewalls and NAT setups.
- Trivial File Transfer Protocol (TFTP) uses port 69, uses UDP, and is a light version of FTP.

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
- Be sure to download browsers, as well as extensions and plugins, from a trusted source.
- Extensions such as password managers and ad/pop-up blockers can greatly enhance your web browsing experience.
- Good password managers won't save your password in cleartext, they will hash the password for more security.
- An easy troubleshooting step for browsers is to clear browsing data and cache under browser settings.
- Some browsers enable signing in to sync data and profile information.