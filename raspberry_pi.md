
# Raspberry Pi Guide

## Contents

  - Initial Setup
    - Format SD card
    - First boot
  - Setup WiFi
    - Static / Dynamic
    - Remote Access
    - SSH
    - SCP
  - RetroPie setup
    - Installation
    - Controller config
    - ROM copy
  - LCD setup
 
## Initial Setup

First step is to get the Raspbian image files.

Go to [https://www.raspberrypi.org/downloads/raspbian/] and download the image.

I used Raspbian Wheezy (2015-05-05: Kernel version: 3.18).

 > There was a newer Raspbian Jessie available (v4.1) but I couldn't unzip it on
 > my Mac and after an hour of searching it had something to do with limits on
 > Mac unzip utilities, still not sure...  but Wheezy works fine.)

Next step is to prepare the SD card.

### Format SD Card

These steps assume a Mac setting this up.  First is find what name disk your Mac sees the SD card you will be using.  

Insert your SD card into your Mac.  The card should be >= 8GB.  Size enough for the OS and all ROMs you eventually want to load onto it.  After inserting the card, open the Mac Disk Utility program.  Find the card and Format it to FAT32.  Pick any name you want.  Do not pick a Mac Journaled File system or the Raspberry Pi won't be able to read it.  After format and clearing the card, run the following command at the Terminal:

```
$ diskutil list
```

Identify the disk number of your SD card.  Something like `disk2`.
Next is to unmount the SD card to prepare it for imaging.

```
$ diskutil unmountDisk /dev/disk<disk number>   // diskutil unmountDisk /dev/disk2
```

Now run the following command to image the card.  This will take ~10-15 min

```
$ sudo dd bs=1m if=image.img of=/dev/rdisk<disk number>
```

> Note: in the above command the path is `/dev/rdisk2` with an _r_ 
> You can also press `Ctrl+T` during the operation to check on its progress.  This will take a few minutes, depending on the image file size. You can check the progress by sending a SIGINFO signal pressing Ctrl+T.



### First boot



## Links

  - https://www.raspberrypi.org/documentation/installation/installing-images/mac.md
  - http://www.circuitbasics.com/raspberry-pi-wifi-installing-wifi-dongle/
  - http://weworkweplay.com/play/automatically-connect-a-raspberry-pi-to-a-wifi-network/
  - http://www.instructables.com/id/Installing-RetroPieEmulationStation-onto-Raspberry/?ALLSTEPS

