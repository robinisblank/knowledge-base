# RAM

## RAM Technology
- Synchronous Dynamic Random Access Memory (SDRAM) has a 168 pins stick, and it is the only RAM with two notches. It runs synchronously with the motherboard clock speed.
- Double Data Rate (DDR) SDRAM does two data transfers per clock cycle. It has a 184 pins stick. If the clock speed is 100 MHz, then the DDR speed rating will be DDR-200, and the PC speed rating will be PC-1600.
- DDR2 has a 240 pins stick. If the clock speed is 100 MHz, then the DDR2 speed rating will be DDR2-400, and the PC2 speed rating will be PC2-3200.
- DDR3 also has a 240 pins stick. If the clock speed is 100 MHz, then the DDR3 speed rating will be DDR3-800, and the PC3 speed rating will be PC3-6400.
- DDR4 has a 288 pins stick. We use the term "bandwidth" when we talk about DDR4, and it is measured in Mega Transfers per second (MT/s).
- DDR4 uses the same formula as DDR3 but the base clocks start much higher. If the clock speed is 200 MHz, then the bandwidth will be 1600 MT/s, the DDR4 speed rating will be DDR4-1600, and the PC4 speed rating will be PC4-12800.
- We can identify generation of a RAM (e.g., DDR, DDR2, etc.) by looking at their speed ratings.
- Different generations of RAM have different pin layouts and notch placements to prevent incorrect installation.
- Different motherboards support a specific RAM technology.
- We measure RAM speeds using DDR or PC ratings.
- We multiple DDR speed rating by 8 to get PC rating because each clock cycle moves 8 bytes of data.
- The metal cover on a RAM stick is known as heat spreader.

## RAM Capacity
- The RAM's internal organization is based on a square. This is why the next RAM capacity will be multiplied by four as each side is doubled. If a RAM is of 1 GB, then the next will be of 4 GB.
- You will encounter RAM capacities like 512 MB or 2 GB. These are double-sided RAMs.
- RAMs these days are almost sold in pairs because motherboards nowadays uses the concept known as "channels".
- If a motherboard has a dual-channel memory, then you have to put two RAMs at minimum into specific slots.
- RAMs should be identical in the same channel.
- Refer to the motherboard's manual to get the information about the type of RAM to use and how to put it.

## RAM Features
- We measure RAM in bytes, and 1 byte has 8 bits. There are 8 chips on a RAM stick, and each chip handles 1 bit. In rare cases you might find more chips.
- Parity and Error Correcting Code (ECC) RAM contains extra chips to check for errors.
- ECC RAM is only for motherboards that support it. We usually see them in servers.
- Small Outline Dual Inline Memory Module (SO-DIMM) is for smaller spaces like in the laptops. Everything about these is same as other RAMs except its size.
- DDR4 SO-DIMM has a 260 pins stick. DDR3 SO-DIMM has a 204 pins stick. We can't be sure about SO-DIMMs before DDR3.
- Almost all RAMs has a Serial Presence Detect (SPD) chip that stores information about the RAM stick.
- Programs like CPU-Z can read SPD information.
- You can select a specific slot to view information about RAM in it under SPD. If the slot is empty, then it will display no information. This way you can check for empty RAM slots without having to look in the PC.

## Virtual Memory
- To avoid out-of-memory errors, the OS can use a portion of mass storage to simulate additional RAM, known as virtual memory.
- Every OS has the feature of virtual memory and options to modify its size and usage.
- We don't want to use the virtual memory. We need to have enough RAM in our system, and virtual memory will keep us running till then.
- The paging file is a designated area on the hard drive that acts as virtual memory.
- In Windows, the `pagefile.sys` in `C:\` is the paging file. Run `dir /ah` to view this file.
- In Windows, the `swapfile.sys` in `C:\` is used to manage memory for Windows Store apps (modern apps) and some system processes, complementing the paging file. Run `dir /ah` to view this file.
- Linux uses swap partitions or swap files as virtual memory when needed.
- It's obvious when virtual memory is in use, our computer gets very slow because now it is not writing into the RAM but into the mass storage which is much slower.

## Installing and Troubleshooting RAM
- Review your hardware and software technical requirements before choosing RAM.
- RAM sticks have generation-specific notches that line up with the appropriate slot on a motherboard.
- Poorly seated RAM is often the main cause of a non-functional RAM.