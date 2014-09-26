ps_initrd.sh, initrd manipulation tool and more
============

About
====

ps_initrd.sh allows you to manage contents of your initrd and
different filesystem images like cramfs, squashfs easily.

Usual ps_initrd.sh workflow consists of the following steps:
  * backup original initrd as initrd.orig (you can use it by manually modifying grub options if you break the working version)
  * unpack initrd with `ps_initrd.sh IMAGE_NAME open` command
  * add/modify files in created initrd-* and modules-* directories
  * pack new initrd with `ps_initrd.sh IMAGE_NAME close` command (if depmod is available -- it refreshes modules.*map files)

You can use `ps_initrd.sh IMAGE_NAME cancel` to delete unpacked
initrd-* and modules-* directories without (honestly!) updating original image.

Prerequisites
====
Functioning Linux system with sh, gzip, tar, cpio and loopback device.

For certain filesystems you will need addiotional packages and kernel support:
  * For cramfs: http://sourceforge.net/projects/cramfs
  * For squashfs: http://sourceforge.net/projects/squashfs

Tested with the following Linux distributions:
  * RHEL/Centos 3
  * RHEL/Centos 4
  * RHEL/Centos 5
  * Debian 3.1 (sarge)
  * Debian 4.0 (etch)
  * Debian 5.0 (lenny)

petya@kohts.ru, 2009
