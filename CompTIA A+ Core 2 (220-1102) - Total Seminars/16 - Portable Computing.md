# Portable Computing

## Power Management
- It is recommended to purchase the AC adapter from the manufacturer itself.
- AC adapters use proprietary power cables and connectors.
- Every AC adapter has a particular voltage, ampere, and polarity. You need to match these to get the right one.
- Check for damaged jack/port if your AC adapter is good but your laptop isn't getting power.
- If you encounter issues the moment you unplug your laptop, either your battery is dead or the charging circuit is defective.
- Most modern laptops use lithium-ion (Li-ion) or lithium-polymer (LiPo) batteries, which degrade over time. When a laptop battery reaches the end of its useful life (typically after 2-5 years of regular use), it needs to be replaced.
- Advanced Configuration and Power Interface (ACPI) is an open standard that allows OSes to manage power, configure hardware, and monitor system status.
- To work with ACPI, you do it within the OS or the System Setup.
- The power button doesn't turn off the power or cut off the electricity. It talks to the motherboard and other components and only does what it is programmed for.
- What happens when closing the lid or pressing the power button can be programmed. You can find settings accordingly in the OS or the System Setup.
- ACPI level 0 means the power is on, but nothing is being used.
- ACPI level 3 is sleep mode; RAM is powered on but the CPU is powered off.
- ACPI level 4 is hibernation mode; RAM data is copied to mass storage and RAM and CPU are powered off.
- Hibernation mode consumes much less power than the sleep mode, but it takes longer to come back from.
- In Windows, the `hiberfil.sys` in `C:\` is where the RAM is copied to when you are in hibernation mode. Run `dir /ah` to view this file.
- In Windows, Control Panel > All Control Panel Items > Power Options. Here, you'll find power settings like power plan, what closing the lid and power button does, etc.
- Advanced settings give extremely detailed control over power.
- All OSes provide power management utilities.