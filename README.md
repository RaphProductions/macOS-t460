# macOS-t460
A kit to install macOS on the ThinkPad T460 (Powered by OpenCore)

## How to install it?

1 : Format the USB with Rufus with this options :
Boot selection : Not bootable
Filesystem : Large FAT32

2 : When Rufus finished formatting your USB drive, download the macOS Kit on your PC and extract it into your USB.
    
    If you want, you can replace the BaseSystem.dmg file with any other version of macOS (e.g. macOS Catalina)
    
3 : Boot your computer from the USB drive you made and boot into your USB

    The Apple Logo will show.

4 : Go to Disk Utility and format your internal hard drive to APFS (Apple File System)

5 : Close Disk Utility and go to Reinstall macOS, follow the instructions, and select the drive you formatted.
    Click Install and wait...
    
    When your computer reboot, boot into the USB drive and select the macOS partition.
    
6 : When macOS is installed, setup your "Mac".

7 : When your "Mac" has been setup, download OpenCore Configurator and mount the EFI partition of your hard drive and copy the EFI files from your USB pen to the EFI partition of your hard drive.

8 : Try reboot your PC without the USB drive and see if it works.

Voila! MacOS on your computer!

# What's working?

### Intel HD 520 Graphics (including graphics acceleration)
### CPU Power Management
### Battery
### All USB ports
### HDMI port (including HDMI Audio)
### Intel I219V Ethernet port
### Realtek ALC239 Audio (including headphones jack)
### Wi-Fi & Bluetooth (including Apple services)
### Internal camera (including Facetime)
### Trackpad, Trackpoint and physical buttons (including gestures)
### Sleep / Wake / Shutdown / Reboot (lid sleep and lid wake)
### Keyboard (incuding all fn Keys using ThinkpadAssistant)
### Apple Services (iMessages, iCloud...) (just app store is broken)
### DRM support (iTunes Movies, Apple TV+, Amazon Prime and Netflix, and others)
### SD Card Reader (v2.2 works but still a bit unstable)
# What's not working
### Fingerprint Reader (will never work since no drivers available)
### Sidecar Wireless (doesn't work without apple native WIFI card)
 
# BIOS Settings

## Security Chip Disabled
## Memory Protection -> Execution Prevention Enabled
## Virtualization -> Intel Virtualization Technology Enabled
## Virtualization -> Intel VT-d Feature Enabled
## Anti-Theft -> Computrace -> Current Setting Disabled
## Secure Boot -> Secure Boot Disabled
## Intel SGX -> Intel SGX Control Disabled
## Device Guard Disabled
## UEFI/Legacy Boot UEFI Only
## CSM Support No
