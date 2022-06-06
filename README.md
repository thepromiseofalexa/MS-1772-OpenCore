# [OpenCore](https://github.com/acidanthera/OpenCorePkg) EFI Build

A manually assembled build for installing Hackintosh on my laptop. Saved for future experiments.

I would like to express my gratitude to [Dortania's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) for such a detailed guide, which includes the correct installation, problems and their solution.

**OpenCore Version:** 0.8.0

# Completed to working

- QE/CI of Intel HD 4600
- Audio
- Power Management
- Ethernet
- All USB Ports
- HDMI Video
- Touchpad
- Battery Indicator
- Brightness

# Not working

- Wifi and Bluetooth (i'm don't need their work)
- Airdrop
- Brightness keys

# Computer specifications

Component | Model
--- | ---
Laptop | MSI GS70 2PE Stealth Pro (MS-1772)
CPU | Intel Core i7-4710HQ
iGPU | Intel HD Graphics 4600
Audio Chipset | ALC-892
Ethernet | Killer E2200 Gigabit Ethernet Controller

# Successfully checked versions MacOS

- [x] MacOS Big Sur (1.1.6.6, not checked other versions)
- [x] MacOS Monterey (Successful OTA update without breaking any's kexts & drivers from Big Sur).

# Installed Drivers 

Drivers | Short description
--- | ---
[HfsPlus](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi) | Needed for seeing HFS volumes
[OpenRuntime](https://github.com/acidanthera/OpenCorePkg/releases) | Extension for OpenCore to help with patching boot.efi for NVRAM fixes and better memory management

# Installed Kexts

Kexts | Short description
--- | ---
[VirtualSMC](https://github.com/acidanthera/VirtualSMC/releases) | Emulates the SMC chip found on real macs, without this macOS will not boot
[Lilu](https://github.com/acidanthera/Lilu/releases) | A kext to patch many processes, required for AppleALC, WhateverGreen, VirtualSMC and many other kexts. Without Lilu, they will not work.
[WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases) | Used for graphics patching, DRM fixes, board ID checks, framebuffer fixes, etc; all GPUs benefit from this kext.
[AppleALC](https://github.com/acidanthera/AppleALC/releases) | Used for AppleHDA patching, allowing support for the majority of on-board sound controllers
[AtherosE2200Ethernet](https://github.com/Mieze/AtherosE2200Ethernet/releases) | Used for work ethernet card
[VoodooPS2](https://github.com/acidanthera/VoodooPS2/releases) | Works with various PS2 keyboards, mice, and trackpads
[USBInjectAll](https://bitbucket.org/RehabMan/os-x-usb-inject-all/downloads/) | Used for injecting Intel USB controllers on systems without defined USB ports in ACPI
