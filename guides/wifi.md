---
title: Wi-Fi
category: Guides
---

Wifi, adapters and Linux have tough relations. Though some of them are supported and you can try to use it.

In general, it’s simple. On your first run, you’ll be asked for a rig password, but since you have no internet connection open a new terminal tab and run `wifi` command there. You will be prompted for SSID and password. If everything is ok then it just works.

Later if you really know that your adapter is working you could use `/hive-config/network/wifi.txt` which is also visible under Windows to set your SSID and password.

There are some useful commands

`iwconfig` - to show you wireless adapters

`ifconfig` - to check assigned IP address

You really never know will it work until you plug it in. We’ve seen some expensive adapters that did not work out of the box or required additional or patched drivers. At the same time, the cheapest Chinese $5 one just works.
<img src="https://forum.hiveos.farm/uploads/editor/fr/15r49yq975r6.jpg">

What to do if your adapter does not work but you bloody need it? Use Wifi repeater with LAN port like this, so it will be your wifi client and you plug rig to it’s LAN.
<img src="https://forum.hiveos.farm/uploads/editor/vl/84uusnwpusqc.jpg">

Another option and our strong advise is to use Powerline, that’s a really cool technology. It gives your LAN access over a 220V wire in your apartment or building. Though it’s a bit more expensive (you can find some cheaper ones on the aftermarket).
<img src="https://forum.hiveos.farm/uploads/editor/91/g8qpyxvasnez.jpg">
