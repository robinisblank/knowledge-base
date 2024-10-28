# Firmware

## What is BIOS?
- BIOS stands for Basic Input/Output System.
- Motherboard is an assumption that you're going to use certain types of hardware. This is why it has all sorts of ports available.
- BIOS is a firmware embedded in a motherboard that talks to the computer's hardware.
- BIOS programming enables interaction with motherboard and its connected hardware before OS loads.
- BIOS is stored in non-volatile media, thus called firmware.
- Modern motherboards have two BIOS chips, one of which is a backup chip.
- POST and System Setup are built into a BIOS.
- Services are BIOS programs that make hardware functional.
- POST is a testing program in BIOS.
- CMOS is a type of memory chip.
- Device drivers make hardware function in an OS.

## POST
- POST stands for Power-ON Self-Test.
- The only thing that ON/OFF button does is providing electricity to the computer. Every CPU has a "power good" wire often referred to as PWR_OK wire. As soon as this wire gets enough voltage, CPU starts running, and the first thing that it does is talking to the BIOS and running one of its component known as POST.
- BIOS performs POST to check that all connected hardware are working properly before loading the OS.
- POST errors can manifest as specific beep sounds, text, or hex codes on POST cards.
- Beep codes are issued when error messages can't be displayed on the screen. For example, a bad video card.
- You can plug in a POST card and watch the two digit hexadecimal code.
- Some motherboards has a POST card built in. The motherboard's manual contains a list of meanings of the POST error codes.
- POST card enables testing of dead computers.
- You don't need to buy an expensive POST card that comes with a thick book.

## System Setup
- Also known as the "BIOS Setup" or "UEFI Setup Utility". It is a firmware interface that allows users to configure hardware settings on their computer. It enables changes to CPU frequencies, RAM timings, BIOS passwords, boot options, and more.
- Unified Extensible Firmware Interface (UEFI) replaces the 16-bit BIOS with a modern firmware interface that supports both 32-bit and 64-bit processors.
- A user password prevents the OS from booting until the password is entered.
- The administrator password prevents unauthorized access to the system setup.

## Troubleshooting Firmware
- Back in the days, we had two chips, EEPROM and a separate CMOS chip. But now we have a single flash ROM chip.
- Flash is a type of ROM which is still a Read-Only Memory, but we can reprogram it if we want to update the built-in BIOS.
- Real-Time Clock (RTC) is a hardware device on the motherboard that keeps track of date and time even when the computer is powered off.
- Complementary Metal-Oxide-Semiconductor (CMOS) is a small amount of memory on the motherboard that stores BIOS settings.
- Modern systems no longer have separate RTC chips. RTC is built into the chip that also handles the CMOS memory.
- CMOS battery (often a CR2032 lithium battery) provides power to both RTC and CMOS to maintain their functions when the computer is powered off.
- If the CMOS battery runs out, then the time is going to slow down and you'll see that your computer is behind the current time. Another thing that will happen is that all the settings that you have updated through the system setup will disappear.
- Flashing the ROM updates the firmware on the flash chip.
- Make sure you have an uninterrupted power supply while flashing takes place.
- You should have a complete copy of the updated BIOS that you can download from the motherboard's manufacturer.
- You should know why you are updating the BIOS. One of the common reasons is to flash it so that it accepts newer technologies.
- Modern motherboards have backup BIOS chips for recovery in case you screw one up.