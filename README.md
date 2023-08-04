
# Dell G3500 Hackintosh EFI 
**Mac OS Ventura 13.3 - OPENCORE**
**OpenCore Version: 0.9.3**

**[EOL] - No longer maintained**

This repository contains the necessary EFI files and configurations to run macOS Ventura 13.3 on a Dell G3500 laptop as a Hackintosh. Please note that Hackintoshing involves modifying and running macOS on non-Apple hardware, which may not be officially supported and can lead to various compatibility and stability issues.
![macos-ventura-roundup-header](https://github.com/alopez-2018459/EFI_G3500/assets/108323739/baffa579-a0ba-4f2d-ad0b-1a0036f116d4)


## What's Working?
| Desc                              | Status |
 | :----------------------------------- | ------ |
 | Gestures | ✅
 | 120hz Refresh Rate| ✅
 | Full Graphics Accleration | ✅
  | iGPU Power Management |✅
  | Brightness Controls | ✅
  |Sleep/ Hibernation Mode 3 |❌
 |Audio Recording | ✅
 | Speakers | ✅
 |Automatic Headphone Output Switching |✅
 | WIFI | ✅
 |Ethernet| ✅
 |USB 2.0, USB 3.0|✅
 |Bluetooth| ⚠️ **unstable**
|Headphone Jack | ⚠️ **needs patching**
|Built-in Keyboard|✅
|Multimedia Keys | ✅
| iCloud, iMessage, FaceTime | ⚠️ **valid SMBIOS**
| AirDrop | ⚠️ **unstable**
|Battery Percentage Indication | ✅


## Disclaimer

-   This project is for educational and experimental purposes only. Installing macOS on non-Apple hardware may violate Apple's End User License Agreement (EULA).
-   The creator and maintainer of this repository are not responsible for any data loss, hardware damage, or other issues that may arise from using the provided EFI files.

## Prerequisites

-   A Dell G3500 laptop with compatible hardware components (check the "Hardware Compatibility" section for details).
- Knowledge of OpenCore
-   Knowledge of macOS and Hackintoshing.
-   A USB flash drive with sufficient capacity for creating a macOS installer.

## Hardware Compatibility

Before proceeding, ensure that your Dell G3500 laptop has the following compatible hardware components:

-   **CPU**: Intel Core i5-10300H 2.5 GHz Quad Core
-  **RAM**: 8 GB DDR4 2933 MHz (2 x 4GB)
-   **iGPU**: Intel UHD 630
-    **dGPU**: Nvidia GTX 1650 4 GB (Disabled)
-    **SSD**: 256 GB NVMe
-    **HDD**: 1TB SATA
-   **Display**: 15.6" 1920 x 1080 120 Hz
-   **Wi-Fi/Bluetooth**: Intel
-   **Ethernet**: RTL8111/8168/8411
-   **Audio**: Realtek ALC295

## EFI Contents

This EFI repository includes the following files and directories:

-   **BOOT**: Contains bootloaders and bootloader configurations.
-   **OC**: Contains OpenCore configurations and necessary kexts.
-   **ACPI**: Contains patched ACPI files for better hardware compatibility.
-   **Drivers**: Contains EFI drivers required for booting.


## Installation Guide

1.  Download the latest version of the EFI repository from the "Releases" section.
2.  Create a macOS installer USB using a tool like [createinstallmedia](https://support.apple.com/en-us/HT201372) or [macOS Recovery](https://support.apple.com/en-us/HT201314) also you can simply download an image from [Oralila](https://www.olarila.com/topic/20908-easy-fast-and-perfect-vanilla-hackintosh/) and flash the USB with [Etcher](https://etcher.balena.io).
3.  Mount the EFI partition of the USB and replace its contents with the downloaded EFI repository contents.
4. Add your own SMBIOS ( Use MacBookPro16,4 )
5.  Ensure your BIOS/UEFI settings are properly configured for Hackintoshing. Refer to the "BIOS/UEFI Configuration" section for recommended settings.
6.  Boot from the macOS installer USB and follow the on-screen instructions to install macOS.
7.  After macOS installation is complete, boot from the USB again, but this time select the internal drive where macOS was installed.


## Post Install

You may encounter audio distortion issues when using headphones with the 3.5mm jack. To resolve this problem, follow these steps:

### Option 1: ALCPlugFix

1.  Go to [ALCPlugFix-Swift GitHub repository](https://github.com/black-dragon74/ALCPlugFix-Swift).
2.  Follow the installation instructions provided in the repository's README.md.
3.  Once installed, ALCPlugFix will automatically fix the audio distortion issue when you plug in headphones into the 3.5mm jack.

### Option 2: USB Headphones/Sound Card

If you prefer a simpler solution, you can use USB headphones or a USB sound card. By connecting your headphones through a USB port, you can bypass the audio distortion issue altogether, as these devices typically have their own audio processing capabilities.

Choose the option that best suits your preferences and hardware setup to enjoy distortion-free audio on your Dell G3500 Hackintosh.

Please note that these solutions are specific to resolving audio distortion issues. If you encounter any other post-installation issues or have further questions, refer to the troubleshooting section or seek help from the Hackintosh community.


**NOTE**: If you have bluetooth headphones those should work too!


## BIOS/UEFI Configuration

The following BIOS/UEFI settings are recommended for running macOS on the Dell G3500:

-   **SATA Operation**: AHCI
-   **VT-d**: Disabled
-   **Secure Boot**: Disabled
- **TPM**: Disabled
-   **Intel Virtualization Technology (VT-x)**: Enabled
-   **UEFI Boot**: Enabled
-   **Legacy Option ROMs**: Disabled
-   **SATA Mode**: AHCI

Note: The above settings are general recommendations. Your specific configuration might require some adjustments.

## Contributing

Contributions to this EFI repository are welcome. If you find improvements or fixes, feel free to open a pull request or raise an issue.


## License

This project is licensed under the MIT License - see the [LICENSE] file for details.
