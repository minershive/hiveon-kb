---
title: Transferring Hive OS from a flash-drive to SDD/HDD using Hive OS itself
category: Guides
meta_description: By following this instruction, you will transfer Hive OS to SDD/HDD quickly and easily.
---

One of the ways to transfer Hive OS to SDD/HDD is to copy it from the flash-drive.

To do this, follow these steps:

1. Detect the drives (flash-drive and SDD/HDD). Use the command `fdisk -l` and check the results.
For example:


<pre><code>
Disk /dev/sda: 111.8 GiB, 120034123776 bytes, 234441648 sectors
	 Units: sectors of 1 * 512 = 512 bytes
   Sector size (logical/physical): 512 bytes / 512 bytes
   I/O size (minimum/optimal): 512 bytes / 512 bytes
   Disklabel type: dos
   Disk identifier: 0x244b7fbe

   Device     Boot     Start       End   Sectors  Size Id Type
   /dev/sda1            2048     43007     40960   20M  e W95 FAT16 (LBA)
   /dev/sda2           43008 188786687 188743680   90G 83 Linux
   /dev/sda3       188786688 234441647  45654960 21.8G 82 Linux swap / Solaris


   Disk /dev/sdb: 14.4 GiB, 15489564672 bytes, 30253056 sectors
   Units: sectors of 1 * 512 = 512 bytes
   Sector size (logical/physical): 512 bytes / 512 bytes
   I/O size (minimum/optimal): 512 bytes / 512 bytes
   Disklabel type: dos
   Disk identifier: 0x244b7fbe

   Device     Boot Start      End  Sectors Size Id Type
   /dev/sdb1        2048    43007    40960  20M  e W95 FAT16 (LBA)
   /dev/sdb2  *    43008 14690303 14647296   7G 83 Linux
	 </code></pre>

   **Disk /dev/sda: 111.8 GiB** - judging by the size, it's SSD/HDD, and **Disk /dev/sdb: 14.4 GiB** is a flash-drive. Actually, in most cases
**/dev/sda** is SSD/HDD, and **/dev/sdb** is a flash-drive.

2. Transfer the image of the flash-drive using the command `dd:
dd if=/dev/sdb of=/dev/sda bs=10M count=800 status=progress`

- if - this is the device from which we will transfer (our flash-drive)

- of - this is a device where to transfer
 (SDD/HDD)

- bs - this is a size of the block that is transferred at a time (10M is 10 Megabytes, "M" has to be capital, otherwise an error will occur!)

- count - the number of blocks that have to be transferred, 800 will be enough (10800 = 8000Mb). You don't have to specify this, but in this case the entire flash-drive will be copied (in our example, that's 16Gb), despite the fact that under the file system there are only about 8GB. Besides,
if the flash-drive has larger memory capacity than SSD/HDD, the process will end with an error. However, it will not affect the work.

3. After the process is over, you can boot Hive OS from SSD/HDD:
`shutdown -r now`

Don't forget to remove the flash-drive when rebooting, or simply change the boot device in BIOS.
