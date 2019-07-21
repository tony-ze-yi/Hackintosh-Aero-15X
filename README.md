# Hackintosh-Aero-15X
Hackintosh for Gigabyte Aero 15X V8
Tested and working on macOS High Sierra and Mojave

Please see the following for more details:

https://www.tonymacx86.com/threads/guide-aero-15x-v8-high-sierra-nvidia-graphics.267883/

## Specs

```
- Processor: i7-8750H
- Memory: 32GB 2667 MHz DDR4 (Upgraded, original was 16GB)
- Panel: LCD FHD 144Hz 1920x1080 IPS
- Graphics: Intel UHD Graphics 630 + NVIDIA GeForce GTX 1070 GDDR5 8GB

I/O | Ports:

- 3x USB 3.1 Gen1 (Type-A)
- 1x Thunderbolt™ 3 (USB Type-C)
- 1x HDMI 2.0
- 1x mini DP 1.4
- 1x 3.5mm Headphone/Microphone Combo Jack
- 1x SD Card Reader
- 1x DC-in Jack
- 1x RJ-45

Misc:
- Internal Speaker
- HD Camera
```
### Notes:
- Intel WiFi/Bluetooth card need to be replaced with a compatible one. (Used here: **Broadcom BCM94352Z**)
- EFI based

## How to use this repository:
- Root folder has the version of Hackintosh (e.g. 10.13.6 - High Sierra)

Then, inside each folder:
- EFI/CLOVER: Clover EFI files (with kexts, configs, patches, etc.)
- Library/Extensions: Has the kext files that needs to be put in your Library/Extensions folder
- patches: Has the used SSDT/DSDT patches for this version

## Working

**USB Based Devices**
- [x] All USB ports (2.0 + 3.0)
- [x] Card Reader (3.0)
- [x] HD Camera (2.0)
- [x] Keyboard (2.0)
- [x] Bluetooth (Internal 2.0)

**Network**
- [x] Ethernet card
- [x] WiFi + Bluetooth

**Power**
- [x] CPU power management
- [x] Battery indicator
- [x] USB PM
- [x] Shutdown/Sleep/Restart

**Graphics**
- [x] Intel graphics card
- [x] **Nvidia graphics card** (over hdmi)
- [x] HDMI (with Nvidia GC)

**Misc**
- [x] Sound (internal speakers + mic jack on/off)
- [x] Touchpad

## Not working/Issues
- [ ] Thunderbolt hotplug (does work if plugged in on boot)

## Minor improvements needed
- [ ] Map ACPI Brigtness UP/DOWN keys

## Mojave support
- Tested this on Mojave through App Store update and it works right oob after the setup
- However, please note that I'll not update and test this often for Mojave compared to High Sierra since I'm waiting for Nvidia Graphics support on Mojave as well as APFS support on Clonezilla/partclone
   - https://github.com/zacmks/Hackintosh-Aero-15X/issues/4
- Moved Mojave support to 10.14.5 folder

## How I installed it
- Create a bootable USB via these instructions: https://www.tonymacx86.com/threads/guide-booting-the-os-x-installer-on-laptops-with-clover.148093/
- Delete the clover file installed there and replace it with the one in this repo
- Boot it and install to APFS/HFS+J volume
- After install, run clover install onto your laptop drive, ensuring you check "Install rc scripts on target volume" (the rest doesn't matter since we're going to replace the clover folder anyways, but install prefpane if you want).
- Mount EFI using clover configurator, delete the clover folder and replace it with the one in this repo.
- If all works well you should have a fully functioning mojave setup (no nvidia graphics sadly)
**Notes**
- If you happen to have a PM981 SSD (Samsung) due to an RMA, the Mojave install *will not work*! It will reboot randomly during install. Buy another SSD and put it into the second M.2 slot, then install Mojave onto there.
- Sometimes when you update Mojave to 10.14.5 from a lower build it may cause problems with sound. That happened to me. Make a backup and install fresh with the Mojave 10.14.5 installer.
