---
title: Booting problems
meta_description: You plugged your drive in the rig, but nothing happened. That is an unpleasant issue, but we know how to solve it.
---

In general you just plug your drive in the rig and it goes. But sometimes it just doesn’t work.
Firstly you should ensure you are not trying to boot from UEFI partition. Some BIOSes give you this option to choose, and you should not do it.

<img src="https://lbd.hiveos.farm/kbase/images/forum/5rpntezwp5sf.jpg">

Your USB settings should have Legacy mode On. Like for mouse and keyboard to work at boot time, otherwise USB drive will not be detected. IOMMU might be an issue on some motherboards. Sometimes it’s called CSM (compatibility support module).

<img src="https://lbd.hiveos.farm/kbase/images/forum/nkq21zwkxe4t.jpg">

Ok, drive is detected, it starts, but fails after like this:

<img src="https://lbd.hiveos.farm/kbase/images/forum/ebj16b6y9jub.jpg">

This tells you that’s there is some problem with the image written. Usually it’s solved with trying to write the image with alternative software:
- [Etcher](https://www.balena.io/etcher/)
- [Rufus](https://rufus.akeo.ie/)
- [Chrysocome](http://www.chrysocome.net/dd)
- [SourceForge](https://sourceforge.net/projects/win32diskimager/)
- [HDDGURU](http://hddguru.com/software/HDD-Raw-Copy-Tool/)
