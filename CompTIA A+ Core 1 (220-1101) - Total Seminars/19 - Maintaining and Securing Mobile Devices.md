# Maintaining and Securing Mobile Devices

## Maintaining Mobile Devices
- Code Division Multiple Access (CDMA) phones do not use SIM cards; Global System for Mobile (GSM) phones use SIM cards.
- In CDMA phones, there's no hard drive, and things like OS and drivers are stored on ROM, and that's firmware that sometimes needs to be updated.
- Many kinds of updates are done on a CDMA phone, such as baseband updates, broadband updates, radio firmware updates, etc.
- If you have an old CDMA phone and face issues like slow texting and phone calls taking forever to connect, you should consider updating the Preferred Roaming List (PRL).
- PRL is a part of Product Release Information (PRI). It's a big chunk of updates that hit all at once. You have to worry about this when facing connectivity issues, things getting slow, or you have no connection when you visit a new place.
- In GSM phones, you can either update manually or set it to update automatically.
- International Mobile Subscriber Identity (IMSI) defines critical SIM information.
- International Mobile Equipment Identity (IMEI) defines the phone itself.
- CDMA phones don't have IMSI because they don't have a SIM.
- For the IMSI number, you can find it in Settings, or use third-party SIM info/reader apps.
- The IMSI number is typically not displayed by default in the system's user interface because it's for internal carrier operations.
- For the IMEI number, dial `*#06#` on your phone, and your IMEI number will pop up on the screen. You can also find it in Settings, printed on the box, or in the SIM card tray.
- After getting a new phone, you go through an "activation" process. The carrier knows the IMSI, and they need to connect it to your phone's IMEI.
- To set up a VPN, name it, choose the protocol type, and give the server IP address.
- Better VPNs will not use your phone's built-in VPN client. They will install their client.
- All mobile OSes have built-in VPN and backup software.
- Android Package Kit (APK) is for Android files.
- Android phones can be configured with root access for more (possibly unsafe) options. Similarly, you can jailbreak iPhones.
- Trusted sources from the store are safer. Untrusted sources can introduce malicious applications or malware.
- Anti-malware is common for Android. But less so for iOS.

## Mobile Devices and E-mail
- E-mail setup on smartphones always means adding an e-mail account.
- IMAP and POP3 are for incoming, and SMTP is for outgoing.
- Things you need to know to set up a classic e-mail account:
	- FQDN of SMTP mail server
	- Probably a username and password for the SMTP server
	- Port number for SMTP (usually port 25)
	- FQDN for IMAP/POP3 mail server
	- Probably a username and password for the IMAP/POP3 server
	- Port number of IMAP/POP3 (usually port 143/110)
- STARTTLS is a protocol command used to upgrade an existing, non-encrypted connection to an encrypted one.
- SMTP encrypted port: 465 or 587
- IMAP encrypted port: 993
- POP3 encrypted port: 995
- Multipurpose Internet Mail Extensions (MIME) is a standard that extends the formats that e-mail can support (e.g., attachments and rich content). Before MIME, e-mail could only handle plain text with basic ASCII characters. MIME added a layer of encoding, making modern e-mail services possible.
- Secure/MIME (S/MIME) is an extension of MIME that adds security features like encryption and digital signatures.
- Mobile account setup (e.g., Google, Yahoo, iCloud, Microsoft 365, etc.) only requires you to type in your e-mail and password.

## Mobile Synchronization
- Synchronization is different from backup.
- Backups are only in sync at the instant of backup - after that, the original source may undergo changes until the next backup session.
- Synchronization is concerned with keeping current, identical copies of data across multiple devices.
- We synchronize our devices to a desktop, automobile, or cloud.
- Android devices sync with Google Drive; iOS devices sync with iCloud.
- iOS devices can sync using USB or W-Fi only.
- We can sync bookmarks, browser history, location data, eBooks, social media data, applications, and more.

## Mobile Device Security
- Screen locks prevent others from accessing your phone. It includes options like facial recognition, PIN codes, fingerprints, patterns, or swipes.
- Multi-Factor Authentication (MFA) allows more than one type of authentication method, whereas Two-Factor Authentication (2FA) only allows one type of authentication factor on top of your password.
- MFA and 2FA can include requiring a voice call or code verification via SMS text.
- Failed login attempt restrictions can give you a timeout.
- Some failed login security settings will remotely erase/wipe your device.
- Authenticator apps add an extra layer of security. But be careful with these apps because losing your phone will get you in trouble.
- Geotracking provides location information to your mobile apps that make use of mapping functions.
- Locator apps like Find My Phone help locate lost devices, remotely lock them, and remotely erase/wipe them.
- Mobile Device Management (MDM) is a system that can help manage and secure mobile devices, apps, and data. It allows enforcing security policies, device tracking, app management, and remote wiping of data if the device is lost or compromised.
- Bring Your Own Device (BYOD) is a policy where employees are allowed to use their personal devices for work purposes.
- Corporate-Owned, Personally Enabled (COPE) is a policy where the company provides devices to employees, but they are allowed to use them for personal tasks as well.

## Mobile Security Troubleshooting
- You might face signal drops, weak signals, or connectivity issues while being attacked.
- The first thing the attacker does is to turn down your connectivity so that you cannot connect, update, or check anything.
- It's concerning when you should have a good signal but drops out of nowhere. Turn off that device and check it out later.
- When being hacked, you might face power drain, slower data speeds, high resource utilization, and data transmission over the limit.
- Watch out for unintended Wi-Fi/Bluetooth connections.
- Leaked personal files/data, unauthorized account access, unauthorized location tracking, and unauthorized camera/microphone activation are not symptoms but results of a hack.
- Run anti-malware tools.
- Change your passwords everywhere if you think you've been hacked.
- Do a factory reset on that device and reinstall from scratch.

## Mobile Device Troubleshooting
- **Inaccurate/Non-Responsive Touchscreen/Digitizer**:
	- In most cases, the touchscreen is fine and your system is overloaded.
	- Try rebooting the system.
	- You might have installed too many apps. Try removing some of them.
	- Try calibrating the touch sensors if your device has such capability.
- **Dim Display**:
	- Try adjusting the display's brightness or enabling automatic brightness.
	- If you still have a dim display, your device is at the end of its life. Smartphones are just like computers and have a limited lifespan.
	- Replace the bad display/backlight, if it's possible with that device.
	- Get a new device.
- **Cannot Display to External Monitor**:
	- Make sure you are on the same wireless network.
	- Make sure you are trying to talk to the right external monitor.
	- You cannot assume that every external monitor will work instantly with your device. So, be sure to check the manufacturer's information.
- **No Sound From Speakers**:
	- Make sure the volume is up.
	- Disconnect any Bluetooth devices.
- **Intermittent/No Wireless Connectivity**:
	- Same type of problems you will face with desktops, laptops, or anything.
	- Distance or interferences might be the cause.
	- SSID or password might be changed.
- **No Bluetooth Connectivity**:
	- Make sure the device you are trying to connect to is in discoverable mode.
	- Someone might be paired to that device already.
	- Make sure your Bluetooth is on.
- **Apps Fail to Launch/Update, Log Errors, Crashing**:
	- Try clearing the cache of that particular app.
	- Force-stop the app and try restarting it again.
	- Reboot your device and try running that app.
	- Uninstall and reinstall the app.
- **Slow Performance/Slow to Respond**:
	- You are running too many apps.
- **Extremely Short Battery Life**:
	- Anything running in real-time in the background (e.g., GPS and syncing) will burn CPU cycles and drop your battery considerably.
	- Use tools that list battery-consuming apps and remove them.
- **Overheating**:
	- Every smartphone has thermal material to prevent overheating.
	- Lack of ventilation, overcharging, and overusing apps can cause overheating.
	- Overheating can lead lithium batteries to swell and explode.
- **Frozen System**:
	- There might be an issue with the particular app.
	- Trace down the app and uninstall it until a patch is released.
- **System Lockout**:
	- Too many failed login attempts can lock you out of the system.
	- Often, a system lockout points to someone else trying to do something evil.
	- For example, you got a 1000$ smartphone for 200$, but it's got a system lockout. It was probably a stolen device.
	- Do a factory reset on that device and reinstall from scratch.