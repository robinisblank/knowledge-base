# Essentials of Networking

## Introduction to Networking
- Local Area Network (LAN) computers connect with Ethernet.
- Ethernet says that data can only be sent in discrete chunks of 1500 bytes known as frames. This solved the problem of one person hogging up the network.
- Every system in a LAN is uniquely identified by a Media Access Control (MAC) address, which is a 48-bit address represented as 12 hexadecimal characters. For example, `00-AF-22-01-23-E2`. This enabled data to be sent to the desired computer only.
- Every network card gets its MAC address. The first six characters are called OEM ID, issued by the issuing body of the Internet, and the other six characters can have many combinations.
- To see your MAC address (labeled as "Physical Address") in Windows, run the command `ipconfig /all`, and in Linux, run the command `ifconfig` (now simple `ip`).
- Each ethernet frame consists of a destination MAC address, a source MAC address, data payload, and a Frame Check Sequence (FCS).
- Source MAC is added if the destination computer wants to talk back.
- FCS is an error-detecting code added to a frame in a communication protocol.
- IP addresses don't do much in a small LAN. To appreciate their use, we need to make our network bigger.

## Hubs vs. Switches
- It doesn't matter which port or how computers are connected to a hub or a switch. As long as they are connected, you have a LAN.
- Hubs repeat all traffic on LAN to all nodes. This causes the sharing of bandwidth.
- Switches filter traffic based on MAC address. It sends data to the computer with destination MAC address only. This provides full bandwidth to all nodes because no computer is talking over the other conversations.
- Switches watch all inbound frames and learn MAC addresses from them.
- If you are going to make a LAN today, you will use a switch.

## Hexadecimal
- Hexadecimal (base 16) is shorthand to represent long strings of 1s and 0s.
- Each hex character represents four binary numbers (0000-1111).
- In hex, numbering goes 0-9, then a-f, for 0-15.

## WANs and Routers
- Ethernet standards restrict the maximum number of connected computers to 1,024 on a LAN (via single or daisy-chained switches). However, the network overloads even before reaching that limit. Hence, ethernet is not suitable for large-scale networks.
- Routers connect multiple LANs to form a Wide Area Network (WAN).
- Routers use logical addressing (IP addressing) to differentiate local and remote traffic.
- Every device has two addresses: a MAC address, which is a physical address burned into devices for local communication, and an IP address, which is a logical address that we can assign to devices for communication across different networks.
- Devices within a LAN use unique IP addresses (e.g., `192.168.4.x`).
- The router typically has an IP address ending in `.1` (e.g., `192.168.4.1`) and acts as the "default gateway" for devices in the LAN.
- A router acts as a traffic cop between LANs, directing data to the appropriate destination network.
- Each LAN can have its unique IP addressing system, and routers manage communication between them.
- We don't need to manually assign IP addresses to each device as the router uses a Dynamic Host Configuration Protocol (DHCP) server, which automatically does this.
- A typical home router may have a built-in switch and wireless capabilities, allowing for wired and wireless connections.

## Cables and Connectors
- Wired connections are the backbone of networking and the Internet.
- Ethernet is the predominant networking technology that defines frames, how network cards work, speed, and the type of cables and connectors we use.
- DOCSIS (used for cable modems) is an alternate technology that uses different cables and connectors.
- 10BaseT (10 Mbps baseband twister pair), 1000BaseT, and 10GBaseT are some ethernet standards.
- Coaxial cables have RG ratings (e.g., RG-58, RG-59, RG-6). 
- RG-59 and RG-6 use F-type connectors, and RG-58 use BNC connectors.
- Twister Pair cables come shielded or unshielded.
- Unshielded Twisted Pair (UTP) uses RJ-11 (for telephone cords) and RJ-45 (for Ethernet cables). It has a maximum distance of 100m. It has four pairs of wires.
- RJ-11 had 4 contacts (2 pairs of wires), and RJ-45 had 8 contacts (4 pair of wires).
- Shielded Twister Pair (STP) uses RJ-45. It has shielding for protection.
- Fiber optic cable doesn't use electricity, it uses light.
- Multimode (uses LED) and Singlemode (uses lasers) are different ways to propagate light signals.
- One wire in a fiber optic connection either sends or receives. This is why they are always used in pairs.
- CAT 5 (100 Mbps), CAT 5e (1 Gbps), CAT 6 (1 Gbps up to 100m and 10 Gbps up to 55m), and CAT 6a (10 Gbps at 100m segments) are different Cat (category) ratings of UTP cables, each with a different transfer rate and bandwidth.
- PVC (non-plenum) is the most burnable cable.
- Plenum-rated cables are designed for use in spaces with airflow (e.g., above drop ceilings, below raised floors). These are much more fire-resistant.
- Riser-rated cables are used for vertical runs between floors (e.g., in walls, shafts). These are less fire-resistant than plenum cables, but still better than standard PVC cables.
- Direct-burial cable (DBC) is designed to be buried under the ground. These cables are much more protected than other cables like extra insulation, waterproofing, and heat tolerance.

## Crimping Cables
- Use a crimping tool to attach a UTP cable to crimp (like RJ-45).
- Crimps also have CAT ratings so if you are for example cutting and crimping a CAT 5e cable, then you need to buy CAT 5e crimps.
- Advanced cables like CAT 6a are very challenging to crimp.
- TIA 568A and TIA 568B are standards to place cables on set pins.
- When the tab of the crimp is facing down, pins count from right to left.
- A cable tester is used to check connections for continuity and wire map.
- Straight-through cable has the same standard on each end.
- Crossover cable has different standards on each end.
- If you connect two computers directly with a crossover cable, they will be able to communicate with each other depending on the network card.

![T568A and T568B diagram](t568a-and-t568b-diagram.png)

## Structured Cabling
- Network cabling should be organized and kept in walls for safety and efficiency.
- Structured cabling involves organized runs from network equipment to wall outlets.
- Typically, structured cabling starts in a closet/room called the Main Distribution Frame (MDF) or Intermediate Distribution Frame (IDF).
- A 19-inch equipment rack is standard for housing network devices.
- The height of rack equipment is measured in U units. A switch is often 1U high.
- Horizontal runs refer to the cables that go from the equipment rack to various wall outlets in the building.
- These horizontal runs connect to a patch panel in the equipment rack, and then from the patch panel to devices like switches using patch cables.
- Patch cables connect the patch panel to the switch and extend to individual systems via horizontal runs.
- The TIA standard allows a maximum horizontal run length of 90 meters with up to 10 meters reserved for patch cables, aligning with Ethernet's 100 meters limit.
- Patch Panels follow the T568A and T568B wiring standards.
- The process of connecting wires into a patch panel is done using a 110 punch-down tool. The wire is punched down into the punchdown block.
- A cable tester is used to check connections for continuity and wire map. The tester can be used with a remote to test long horizontal runs.
- Fox (tone generator) and hound (tone probe) tools help locate cables in a patch panel.
- Time Domain Reflectometer (TDR) measures the length of a cable using the speed of light and detects cable breaks.
- Solid core cables are used for in-wall runs (better for carrying signals).
- Stranded core cables are used for patch cables (more flexible and durable).
- A loopback plug is used to test if ports or connections are physically working by looping the output signal back to the input.
- Commercial loopback devices are available for both RJ-45 and fiber optic connections.

## Network Card Troubleshooting
- A Network Interface Card (NIC), also known as an Ethernet Card or Network Adapter, is an essential component of any computer that connects it to the network.
- Today, motherboards come with built-in NIC.
- Use Device Manager > NIC Properties for information/configuration.
- You can disable NIC in Device Manager or System Setup.
- Speed & Duplex under advanced settings gives multiple speed options for Full-duplex and Half-duplex.
- Full-duplex allows data to be transmitted in both directions simultaneously, while half-duplex only allows one device to transmit and receive data at a time.
- Wake-on-LAN under power management settings wakes a computer if turned off when a piece of information comes in. This information is called a magic packet.
- Link lights show connectivity, speed, and activity.
- The link light for connection is steady and on all the time.
- Speed light changes color according to the speed.
- Activity light is always flickering. 
- Link and speed light can be the same and only change color.
- To ensure network connectivity, check link lights on both ends, the back of the system, and the switch it is plugged into.
- If the link lights are lit in any way without anything plugged in, that would indicate a defective port.