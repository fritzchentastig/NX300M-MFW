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

## Modifications to the original firmware

After *someone* published the autoexec.sh trick that we used to pull off those mods, Samsung removed the four main parts that were needed for that trick.

The first thing that was known: limbisc.so. This is a library in the OS and it was the one that called the autoexec.sh in the first place. Samsung decided to get rid of that part. So I replaced the limbic.so in the 1.15 with the one from the 1.10.

The second thing I noticed was that telnet was not working. So, thanks to [ge0rg](https://github.com/ge0rg), I found out that it was part of busybox. Samsung decided to get rid of that part. So I replaced it: Aaaaand nothing. It turns out that telnetd and ftpd are part of busybox and are called via symlinks in /usr/sbin. And Samsung removed those too. I decided to recreate them, but that was not possible for some reason. So I copied the 1.10 busybox there three times, and renamed them to telnetd, ftpd and chroot respectively.

#### TL:DR

- libmisc.so and busybox were replaced with the versions from the 1.10 firmware
- the missing telnetd, ftpd, and chroot symlinks were replaced with equally renamed busybox binaries.

## A word about compatibility 

This software aims to make the NX300M as compatible as possible with existing NX300 hacks. This is not that difficult, except for one thing: WiFi. The method used in the remote controller mod no longer works in this camera. So, thanks to [this](https://languagetool.org/de) article, I found a solution. This solution will be published soon™. Until then, refer to this article to enable always-on WiFi.

## A word about the future

The main goal of this project has been fulfilled. 
However, another branch of this project will be used to hopefully create new mods for the NX300 family, such as a button interface to start the local AP or the remote mod. Please refer to the project’s page regarding that.

## A word about help

I welcome and appreciate any ideas or suggestions that can improve our project. If you have an idea, please share it with us by using one of the following methods:

- Commit your idea to a branch in your fork of the repository.
- Write an issue with the feature request tag, describing your idea and why it is useful or needed. Include any relevant screenshots, mockups, or examples.
- Write a pull request, linking it to the issue you created. Explain what your code does and how it works.
- Comment on other issues or pull requests that are related to your idea. Provide constructive feedback, ask questions, or offer support.

By following these steps, you can help us review and evaluate your idea faster and easier. Thank you for your interest and contribution to our project. 😊

## Disclaimer

This firmware is provided as-is, without any warranty or guarantee. Use it at your own risk. I am not responsible for any damage or loss that may occur as a result of using this firmware.

## Credits

- [Samsung Support](https://www.samsung.com/de/support/model/EV-NX300MBSTDE/): Here you can find the official user manual, firmware updates, and warranty information for the NX300M camera.
- [nx300-hacks](https://github.com/HausnerR/nx300-hacks): This GitHub project contains some useful scripts to enhance the functionality of the NX300M camera, such as enabling telnet access. This uses different methods for FTP and telnet than the other project. This helped me find possible mistakes I made.
- [Auto Backup from NX300 via FTP](https://lemmster.de/auto-backup-from-nx300-via-ftp.html): This blog post explains how to set up an automatic backup of your photos and videos from the NX300M camera to your computer via FTP. It was useful to figure out how the camera works. This also describes how to enable always-on wifi.
- [Rooting the NX300](https://op-co.de/blog/posts/rooting_the_nx300/): This blog post describes how to root the NX300M camera and gain full access to its Linux system, allowing you to install additional software and modify the system settings. Also, check out this website.
- [ge0rg](https://github.com/ge0rg) The person who brought me into this community and taught me most of the things I know about these cameras, his groundwork and continuing support made this project possible.
- [nxfiles](https://nxfiles.nx.tc): This website made the project possible by hosting every firmware version and OSS release Samsung no longer continues to host.
