# macOS for ThinkPad X1 Carbon 6th Gen [20KG] (Updated: Oct 10, 2024)

![X1C6](https://psrefstuff.lenovo.com/syspool//Sys/Image/ThinkPad/ThinkPad_X1_Carbon_6th_Gen/ThinkPad_X1_Carbon_6th_Gen_CT1_09.png)

This project provides a complete and functional macOS Ventura `13.7` build for the ThinkPad X1 Carbon 6th Gen (model 20KG). It is based on the excellent guides from [tylernguyen](https://github.com/tylernguyen/x1c6-hackintosh) and [Rybo713](https://github.com/Rybo713/X1C6-macOS), with modified ACPI patches and updated kexts.

### Future Plans
I plan to modify the BIOS on the X1 Carbon Gen 6 once I receive my **CH341a SPI Programmer** and **SOIC8 Clip**. Updates on the BIOS modification process will be added as this progresses.

- Using SMBIOS: `MacBookPro15,2`
- Bootloader: OpenCore v1.0.1

## System Specifications

| Component   | Details                                     |
|-------------|---------------------------------------------|
| **Model**   | X1 Carbon 6th Gen [20KG]                    |
| **CPU**     | i5-8350U                                    |
| **GPU**     | Intel UHD620 1536MB (0x5916)                |
| **RAM**     | 2133MHz 16GB LPDDR3                         |
| **Display** | 14" IPS FHD Anti-Glare (1920x1080, 60Hz)    |
| **Storage** | 256GB Kioxia BG5 (2280)                     |
| **Wi-Fi**   | Intel Wireless AX210NGW                     |
| **Bluetooth**| Intel Wireless AX210NGW                    |

## Important Notes

Your X1 Carbon may not have the exact specifications listed above, and your results may vary. If you need assistance or run into issues, feel free to ask for help.

## Tested macOS Versions

- **macOS Ventura**: 13.7 (22H123)

## Functional Features

The following features are confirmed working:

- **Audio**
- **Keyboard**, including brightness control
- **Power Management** via CPUFriend
- **Battery Management**
- **USB-A Ports**
- **Trackpad** (with full gesture support)
- **Trackpoint**
- **Webcam**
- **Microphone**
- **Display Brightness Control**
- **Sleep / Wake**
- **Wi-Fi** (using [itlwm](https://github.com/OpenIntelWireless/itlwm))
- **Bluetooth** (using [IntelBluetoothFirmware](https://openintelwireless.github.io/IntelBluetoothFirmware/FAQ.html#what-additional-steps-should-i-do-to-make-bluetooth-work-on-macos-monterey-and-newer))
- **HDMI** (with patches from [tylernguyen](https://tylernguyen.github.io/x1c6-hackintosh/))
- **All FN Keys** ([patch tutorial](https://github.com/MSzturc/ThinkpadAssistant) and [Thinkpad Assistant app](https://github.com/MSzturc/ThinkpadAssistant/releases))

## Known Issues & Untested Features

- **Fingerprint Sensor / Touch ID**: Will never work (disabled in BIOS)
- **Thunderbolt 3**: Untested
- **microSD Card Reader**: Untested
- **USB-C Ports**: Untested

## Bugs & Fixes

- **Boot Loop After Installation (Recovery Issue)**:
  - If you encounter a boot loop after installation from recovery, follow [this guide](https://www.reddit.com/r/hackintosh/comments/17r9cy4/boot_loop_after_first_phase_of_install_after/) for a fix.
  - **Quick Fix (TL;DR):** Temporarily disable Apple Secure Boot in `config.plist`:  
    Navigate to `Misc -> Security -> SecureBootModel`, and set it to **Disabled** (case-sensitive).  
    Once the installation is complete, you can re-enable Secure Boot by setting it back to **Default**.

- **Apple Music Playback Issue**:
  - While Apple Music plays correctly through the internal audio, it's worth noting that the X1 Carbon's built-in speakers may not provide the best sound quality. A preferable option would be to use Bluetooth headphones. However, some users may experience issues with Apple Music not playing properly on Bluetooth devices, potentially due to DRM-related factors.

  **Workaround for Bluetooth Playback**
    To resolve skipping issues when using Apple Music over Bluetooth, follow these steps:

    1. Open **Apple Music** and go to **Preferences > Playback**.
    2. Uncheck the options for **Lossless Audio** and **Dolby Atmos**. These features can cause playback issues, likely due to DRM restrictions.
    3. Open **Audio MIDI Setup** (located in the Utilities folder).
    4. Click the (+) button and select **Create Multi-Output Device**.
    5. Name the new device as you prefer, then enable your Bluetooth device in the audio device list.

- **HDMI Monitor Connection Issue**:
  - When connecting the X1 Carbon to a 144Hz monitor via HDMI, you might encounter a problem where the monitor continuously connects and disconnects. This issue is typically caused by the system defaulting to a 60Hz refresh rate.

  **Solution**
  - To resolve this, manually set the refresh rate to **120Hz**:
    1. Go to **System Settings > Displays**.
    2. Select the external monitor and adjust the refresh rate to **120Hz**.
  
    After making this adjustment, the connection stabilize, and the monitor will work normally.
## Pre-Installation Instructions

1. Follow tylernguyen's detailed [installation guide](https://tylernguyen.github.io/x1c6-hackintosh/).
2. Generate an appropriate SMBIOS using `MacBookPro15,2`.

## Credits

Special thanks to the following contributors for their invaluable resources:

- [tylernguyen](https://github.com/tylernguyen/x1c6-hackintosh)
- [benbender](https://github.com/benbender/x1c6-hackintosh)
- [zhtengw](https://github.com/zhtengw/EFI-for-X1C6-hackintosh)
- [Rybo713](https://github.com/Rybo713/X1C6-macOS)

---
