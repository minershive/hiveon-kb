---
title: IPv6
category: Guides
---

Some users might want to disable IPv6 on the system (if it’s not disabled in the image release). Router is the best way to disable it. Nevertheless, here is how to do it for one host.

This adds `ipv6.disable=1` to GRUB options, updates them and reboots:

`sed -i 's/^GRUB_CMDLINE_LINUX_DEFAULT=.*/GRUB_CMDLINE_LINUX_DEFAULT="text consoleblank=0 intel_pstate=disable net.ifnames=0 ipv6.disable=1 pci=noaer iommu=soft amdgpu.vm_fragment_size=9 radeon.si_support=0 radeon.cik_support=0 amdgpu.si_support=1 amdgpu.cik_support=1"/g' /etc/default/grub && update-grub && reboot`

Run this from terminal or from web Linux Shell.
