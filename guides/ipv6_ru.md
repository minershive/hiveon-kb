---
title: IPv6
parent_category: Гайды
path: /guides-ipv6_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## IPv6
Некоторые пользователи могут захотеть отключить IPv6 в системе (если он не отключен в выпуске образа). Маршрутизатор является лучшим способом сделать это. Тем не менее, вот как это сделать для одного хоста.

Это добавляет `ipv6.disable=1` к опциям GRUB, обновляет их и перезагружает:

`sed -i 's/^GRUB_CMDLINE_LINUX_DEFAULT=.*/GRUB_CMDLINE_LINUX_DEFAULT="text consoleblank=0 intel_pstate=disable net.ifnames=0 ipv6.disable=1 pci=noaer iommu=soft amdgpu.vm_fragment_size=9 radeon.si_support=0 radeon.cik_support=0 amdgpu.si_support=1 amdgpu.cik_support=1"/g' /etc/default/grub && update-grub && reboot`

Запустите это из терминала или из веба Linux Shell.
