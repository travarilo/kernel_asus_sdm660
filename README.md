exFAT-nofuse v1.2.24-dragon
============

Linux non-fuse read/write kernel driver for the exFAT, FAT12, FAT16 and vfat (FAT32) file systems.<br />


**Full adaptation to kernel 4.19.y**


To load the driver manually, run this as root:
==============================================

    modprobe exfat_core
    modprobe exfat_fs


Enable exFAT module and install exfat-utils:
============================================

Add to /etc/initramfs-tools/modules:

    exfat_core
    exfat_fs

For filesystem creation and manipulation beyond that of the mount command it is necessary to install the exfat-utils package:
=============================================================================================================================

    $ sudo apt install exfat-utils
    $ sudo apt purge exfat-fuse


To create an exFAT file system, use mkfs.exfat (or the mkexfatfs command, which is synonymous):
===============================================================================================

    root #mkfs.exfat
    mkexfatfs 1.2.8
    Usage: mkfs.exfat [-i volume-id] [-n label] [-p partition-first-sector] [-s sectors-per-cluster] [-V] <device>
    For instance, to create it on a removable device present at /dev/sde1 while assigning "Flash" as the file system label:

    root #mkfs.exfat -n Flash /dev/sde1

