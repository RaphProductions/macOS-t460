# MacOS Kit from OS11 to 13 💻
## A kit to install macOS on the ThinkPad T460 (Powered by OpenCore)

### Before you continue, let's change to these BIOS Settings for better compatibility
* BIOS KEY: F1
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

## So How do you install it?
### Requirements
* An USB flash drive of 8gb minimum. (this is because we will download the 600MB recovery environment and not the full 16gb macOS image)
* Lenovo ThinkPad T460 (Skylake i5)

### Note
### _I'm not responsible for any damage made to your computer by installing macOS on it so try installing it on a secondary cheap SSD first instead of your actual windows disk._

### 1 : Format the USB
Open Rufus (cause balenaetcher doesn't work some times for no particular reason) and select these options :
* Boot selection : Not bootable
* Filesystem : Large FAT32
* Partition: GPT

### 2: Download the macOS recovery environment
I do recommend following [this guide by Dortania](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/).
* Note: it's simply a .py script that downloads the com.apple.recovery base img (this is the actual mac boot image)
* When downloaded, extract it into your USB flash drive.

### 2.5 Place the EFI in your USB
So next we just place the the EFI folder you downloaded from this repo's Releases folder in the MacOS USB

* Note: If this EFI doesnt work for you, or causes some incompatibility you are free to try [this bigsur one](https://github.com/AsherCarneiro/T460-MacOS-BigSur) or any other one's from github just make sure to download updated kexts (you 
  can update kexts using dortania's guide and don't forget to use OC clean Snapshot in Propertree on config file)

### Note: Delete all files that rufus makes like `autorun.inf` or other files like those, you usb should only have `com.apple.recovery` and `EFI` folders present.

### 3 : Restart your laptop
While on the BIOS screen (a Lenovo logo with the "To interrupt normal startup, press Enter" text), spam the F12 key.
This will get you into the boot menu.

Now, select the USB flash drive. (should appear as "USB HDD: <your usb flash drive's model name>")

This should spawn the OpenCore boot menu. (a Mac-like boot nenu)

IMP: Select the orange drive (it should be named with the name of your FAT32 partition).

Then, the Apple logo should show.

Note: Yo, also dont freak out if nothing happens for a long time, let it do it's own thing

### 4 : Next Format your internal hard drive to APFS
* You can also follow [this tutorial](https://youtu.be/Gaosub7FRf4?feature=shared) after 1:00:20 Timestamp
* When on the "macOS Recovery" screen, select Disk Utility.

On the new window, select your biggest partition of your internal drive (the one where Linux or Windows is installed) & format it to APFS (Apple File System) 

Then, close the Disk Utility

### 5 : Connect your laptop to the WI-FI or Ethernet
This is required for downloading macOS as this is simply a recovery img.

### 5.5 : Install macOS
Select "Reinstall macOS". It should spawn a new window with the OS's name & icon (example: "macOS BigSur*).

Select Next and accept the license.

Finally, select your internal hard drive and click on Install.
    
### 6 : Setup your "Thinkbook"
Set it up like any other Mac on Earth.

### 7 : Install the bootloader
Now, we installed macOS, but we still need our USB stick to boot it...

I recommend following [this guide by Dortania](https://dortania.github.io/OpenCore-Post-Install/universal/oc2hdd.html#grabbing-opencore-off-the-usb).

### Conclusion
Yay! You now have macOS on your Thinkpad! well you have a "Thinkbook" now.

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
