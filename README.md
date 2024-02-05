# Modified Samsung NX300M Firmware

This project is a modified firmware for the Samsung NX300M camera that makes it fully compatible with the [Samsung NX Hacks project](https://github.com/ge0rg/samsung-nx-hacks). 

## Installation

To install this firmware, you need to:

- Download the firmware file (NX300M.bin) from this repository and copy it to the root directory of the SD card.
- Insert the SD card into the camera, power on the device, go to Menu > Setting > Device Information > Firmware Update > Body Firmware Update, and agree with the next message that will initiate the upgrade.
- Wait for the camera to reboot and verify that the firmware version is 1.15.

## Usage

To use the modified firmware, you need to:

- Make sure your memory card is formatted as ExFAT, as the FAT32 filesystem does not support files over 4GB in size.
- The main feature of this MFW is that it restores autoexec.sh functionality.

## Disclaimer

This firmware is provided as-is, without any warranty or guarantee. Use it at your own risk. I am not responsible for any damage or loss that may occur as a result of using this firmware.

## Credits

- [Samsung Support](https://www.samsung.com/de/support/model/EV-NX300MBSTDE/): Here you can find the official user manual, firmware updates, and warranty information for the NX300M camera.
- [nx300-hacks](https://github.com/HausnerR/nx300-hacks): This GitHub project contains some useful scripts to enhance the functionality of the NX300M camera, such as enabling telnet access. This uses different methods for FTP and telnet than the other project. This helped me find possible mistakes I made.
- [Auto Backup from NX300 via FTP](https://lemmster.de/auto-backup-from-nx300-via-ftp.html): This blog post explains how to set up an automatic backup of your photos and videos from the NX300M camera to your computer via FTP. It was useful to figure out how the camera works. This also describes how to enable always-on wifi.
- [Rooting the NX300](https://op-co.de/blog/posts/rooting_the_nx300/): This blog post describes how to root the NX300M camera and gain full access to its Linux system, allowing you to install additional software and modify the system settings. Also, check out this website.
- [ge0rg](https://github.com/ge0rg) The person who brought me into this community and taught me most of the things I know about these cameras, his groundwork and continuing support made this project possible.
- [nxfiles](https://nxfiles.nx.tc): This website made the project possible by hosting every firmware version and OSS release Samsung no longer continues to host.
