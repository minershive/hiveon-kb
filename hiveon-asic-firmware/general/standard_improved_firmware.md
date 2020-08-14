---
title: Difference between standard and improved firmware
parent_category: Hiveon ASIC Firmware
category: General
meta_description: Previously the Hiveon ASIC firmware existed in two versions - Improved and Standard. What is the difference? The answer is in this article. 
---

The difference between Improved and Standard firmware in the presence or absence of a digital signature. Hiveon firmware previously existed in two versions - Improved (with signature) and Standard (without signature).

### What is  improved firmware?
Improved firmware gives maximum protection against viruses.
Also, such firmware cannot be changed to the third-party one through the ASIC's web interface. The change is possible only through the Hive OS web interface.

There are two ways to identify if your firmware is improved. First of all, you can try to flash. Secondly - launch `ls /etc/bitmain-pub.pem`. If there is a file, the firmware is improved.

To change the improved firmware to another firmware, you should use this command to disable signature verification - `rm -rf /etc/bitmain-pub.pem`. Send it to your ASICs via the Hive web. It will temporarily delete the certificate, but you can reboot your ASIC to bring it back. After this, you will be able to move to any firmware via the firmware update menu (in the Hive web). It will be possible to choose the firmware from the list or to use the URL.

Apart from this, you can flash from improved firmware to the stock one via SD-card or the **IP Report** button.

### What is standard firmware?
With standard firmware, it is possible to change firmware via the web interface of ASIC, without Hive. But if the password for the web interface is standard or simple, then viruses, picking up the password, can infect your device. You need to be sure that there are no infected devices on the network.

**The release of standard firmware was discontinued in April 2020 due to the increased number of cases of mass infection.**

Standard firmware can be changed to any other firmware.
