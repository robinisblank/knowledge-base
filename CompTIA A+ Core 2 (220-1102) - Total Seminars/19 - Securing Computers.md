# Securing Computers

## Threats
- The term "security" encompasses host-based, network-based, and physical security.
- In a Man-In-The-Middle (MITM)/On-Path attack, an attacker secretly intercepts and potentially alters the communication between two parties, making them believe they are directly connected.
- To defend against MITM attacks, we encrypt communications.
- Spoofing is faking the identity of another user, device, or network (e.g., IP or email spoofing) to trick the target into trusting the attacker’s message or connection.
- To defend against Spoofing, we use various authentication methods and certificates to verify the identity of the entity you are connecting to.
- A Denial of Service (DoS) attack overwhelms a server or network with excessive requests, making it unavailable to legitimate users.
- A Distributed DoS (DDoS) attack is similar to a DoS attack but uses multiple compromised systems (often a botnet) to flood the target, making it harder to mitigate.
- A zombie is a computer that has been infected with malware and is used by an attacker to perform a malicious task, such as a DDoS attack.
- Zero-Day refers to a vulnerability in software or hardware that is typically unknown to the vendor and has no patch or fix available. The term "zero-day" comes from the fact that the vendor has zero days to fix the flaw.
- Symptoms of such attacks include renamed system files, modified permissions, missing files, and more.

## Dealing with Threats
- Host-based security includes patching, anti-malware, antivirus, and host firewalls.
- Network-based security includes an Intrusion Detection System (IDS), Intrusion Prevention System (IPS), and network firewalls.
- IDS is a security tool/application that monitors network traffic and detects suspicious or malicious activities. When it identifies a threat, it sends alerts to IT or security teams but does not take direct action to block or stop it.
- IPS functions similarly to IDS by monitoring and detecting threats, but it also actively blocks or prevents malicious traffic from entering the network, providing an additional layer of defense.
- Endpoint management is the process of centrally monitoring, securing, and managing devices that connect to an organization’s network. It involves device configuration, software updates, security enforcement, access control, etc.
- Unified Threat Management (UTM) is a network security approach that combines multiple security functions such as IDS/IPS, firewall, anti-malware, VPN, and content filtering into a single device or software installation.
- UTM simplifies security management, especially in small to medium-sized organizations. It is commonly available as both on-premises devices and cloud-based solutions.
- A LAN tap, or network tap, is a device that allows you to monitor and access data that is transmitted over a network. [Throwing Star LAN Tap Pro](https://greatscottgadgets.com/throwingstar/)

## Physical Security

## Passwords and Authentication

## Multi-Factor Authentication (MFA)

## Malware

## Anti-Malware

## Social Engineering

## Licensing

## Incident Response

## Environmental Controls

## Malware in Action