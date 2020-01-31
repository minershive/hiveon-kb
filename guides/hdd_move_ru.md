---
title: Перенос HiveOS с Флешки на SDD/HDD Средствами Самой HiveOS
category: Гайды
---

## Перенос HiveOS с Флешки на SDD/HDD Средствами Самой HiveOS
Один из способов перенести HiveOS на SDD/HDD - скопировать её с работающей флешки.
Для этого проделываем в консоли следующее:
[list=1]
[*] Определяем наши диски (флешку и SDD/HDD), для этого вводим команду fdisk -l и смотрим ее вывод.
Например:


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

   Disk /dev/sda: 111.8 GiB - судя по размеру это SSD/HDD, а Disk /dev/sdb: 14.4 GiB - это флешка. Собственно, в большинстве случаев,
/dev/sda - будет SSD/HDD, а /dev/sdb - флешка.

[] Переносим образ флешки с помощью команды dd:
dd if=/dev/sdb of=/dev/sda bs=10M count=800 status=progress
здесь
if - это устройство с которого будем переносить (наша флешка),
of - устройство куда переносить (SDD/HDD)
bs - Размер блока, который переносится за 1 раз (10M это 10Мегабайт, обязательно M большая, иначе выдаст ошибку!)
count - количество блоков, которые нужно перенести, 800 будет достаточно (10800 = 8000Мб), можно не указывать, но тогда будет
копироваться вся флешка (в нашем случае 16Gb), несмотря на то, что под файловой системой всего около 8Гб. Кроме того,
если флешка будет большего объема, чем SSD/HDD, то процесс закончится ошибкой. Впрочем, она не повлияет на работу.

[*] По завершению процесса, можно загружать HiveOS с SSD/HDD:
`shutdown -r now`

Не забудьте вынуть флешку при перезагрузке или изменить загрузочное устройство в BIOS.
[/list]

Если хотите хранить прон на риге и вам нужен весь размер диска, то можете прочитать как расширить размер раздела с HiveOS на весь диск:
https://gist.github.com/dobrMAN/8307c1f6a2515186ba74a554ee1b56a0
