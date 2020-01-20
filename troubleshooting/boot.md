---
title: Booting problems
---

## Booting problems
In general you just plug your drive in the rig and it goes. But sometimes it just doesn’t work.
Firstly you should ensure you are not trying to boot from UEFI partition. Some bioses give you this option to choose and you should not do it.

<img src="http://forum.hiveos.farm/uploads/editor/b0/5rpntezwp5sf.jpg">

Your USB settings should have Legacy mode On. Like for mouse and keyboard to work at boot time, otherwise USB drive will not be detected. IOMMU might be an issue on some motherboards. Sometimes it’s called CSM (compatibility support module).

<img src="http://forum.hiveos.farm/uploads/editor/sa/nkq21zwkxe4t.jpg">

Ok, drive is detected, it starts, but fails after like this:

<img src="http://forum.hiveos.farm/uploads/editor/bn/ebj16b6y9jub.jpg">

This tells you that’s there is some problem with the image written. Usually it’s solved with trying to write the image with alternative software:
- [Etcher](https://www.balena.io/etcher/)
- [Rufus](https://rufus.akeo.ie/)
- [Chrysocome](http://www.chrysocome.net/dd)
- [SourceForge](https://sourceforge.net/projects/win32diskimager/)
- [HDDGURU](http://hddguru.com/software/HDD-Raw-Copy-Tool/)
