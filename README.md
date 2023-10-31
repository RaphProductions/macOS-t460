# macOS-t460
A kit to install macOS on the ThinkPad T460 (Powered by OpenCore)

## How to install it?
### Requirements
* An USB flash drive of 1gb minimum. (this is because we will download the 600MB recovery environment and not the full 16gb macOS image)
* Lenovo ThinkPad T460 (since this kit is made for that laptop)

### Note
I'm not responsable of any damage made to your computer by installing macOS on it.

### 1 : Format the USB
Open Rufus and select these options :
* Boot selection : Not bootable
* Filesystem : Large FAT32

### 2 : Download the macOS Kit 
When downloaded, extract it into your USB flash drive.

### 2.5 : Download the macOS recovery environment
I recommend following [this guide by Dortania](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/).

### 3 : Restart your laptop
While on the BIOS screen (a Lenovo logo with the "To interrupt normal startup, press Enter" text) and spam the F12 key.
This will get you into the boot menu.

Now, select the USB flash drive. (should appear as "USB HDD: <your usb flash drive's model>")

This should spawn the OpenCore boot menu. (a Mac-like boot nenu)

Select the orange drive (it should be named with the name of your FAT32 partition).

Then, the Apple logo should show.

### 4 : Format your internal hard drive to APFS
When on the "macOS Recovery" screen, select Disk Utility.

On the new window, select your biggest partition of your internal drive (the one where Linux or Windows is installed) & format it to APFS (Apple File System) 

Then, close the Disk Utility

### 5 : Connect your laptop to the WI-FI
This is required for downloading macOS.

### 5.5 : Install macOS
Select "Reinstall macOS". It should spawn a new window with the OS's name & icon (example: "macOS Ventura*).

Select Next and accept the license.

Finally, select your internal hard drive and click on Install.
    
### 6 : Setup your "MacBook Pro"
Set it up like any other Mac on Earth.

### 7 : Install the bootloader
Now, we installed macOS, but we still need our USB stick to boot it...

I recommend following [this guide by Dortania](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html#grabbing-opencore-off-the-usb).

### Conclusion
Voila! You have now macOS on your laptop!

## What's working?
* Intel HD 520 Graphics (including graphics acceleration)
* CPU Power Management
* Battery
* All USB ports
* HDMI port (including HDMI Audio)
* Intel I219V Ethernet port
* Realtek ALC239 Audio (including headphones jack)
* Wi-Fi & Bluetooth (including Apple services)
* Internal camera (including Facetime)
* Trackpad, Trackpoint and physical buttons (including gestures)
* Sleep / Wake / Shutdown / Reboot (lid sleep and lid wake)
* Keyboard (incuding all fn Keys using ThinkpadAssistant)
* Apple Services (iMessages, iCloud...) (just app store is broken on macOS Big Sur)
* DRM support (iTunes Movies, Apple TV+, Amazon Prime and Netflix, and others)
* SD Card Reader (v2.2 works but still a bit unstable)

## What's **not** working
* Fingerprint Reader (will never work since no drivers available)
* Sidecar Wireless (doesn't work without apple native WIFI card)
 
# BIOS Settings
* Security Chip Disabled
* Memory Protection -> Execution Prevention Enabled
* Virtualization -> Intel Virtualization Technology Enabled
* Virtualization -> Intel VT-d Feature Enabled
* Anti-Theft -> Computrace -> Current Setting Disabled
* Secure Boot -> Secure Boot Disabled
* Intel SGX -> Intel SGX Control Disabled
* Device Guard Disabled
* UEFI/Legacy Boot UEFI Only
* CSM Support No
