---
title: Difference Between Standard and Improved Firmware
parent_category: Hiveon ASIC Firmware
category: General
---

## Difference Between Standard and Improved Firmware
### What is standard firmware?
With standard firmware, it is possible to change firmware via the web interface without Hive. But if the password for the web interface is standard or simple, then viruses, picking up the password, can infect your device. You need to be sure that there are no infected devices on the network.

In any case, we strongly recommend changing the username and password to access the ASIC through SSH. Keep in mind that most viruses have a list of the most common passwords, so you should not use passwords like 1234567890. One infected ASIC brought to the farm infects all the surrounding ASICs that have the standard password. Modern viruses, such as Antbuild v2, cannot be "cured" or removed. The issue can only be resolved by replacing the entire processor or control board.

### What is  improved firmware?
Improved firmware gives maximum protection against viruses.
Also, such firmware cannot be changed to the third-party one through the ASIC's web interface. The change is possible only through the Hive OS web interface.

### How to identify if I have improved firmware?
First of all, you can try to flash. Secondly - launch `ls /etc/bitmain-pub.pem`. If there is a file, the firmware is improved.

### How to flash from improved Hiveon ASIC firmware?
The improved firmware can be updated ONLY to another improved Hiveon firmware, via ASIC’s web interface or BTC_TOOLS. Third-party or official firmware can’t be installed in this way. However, you can use the `rm -rf /etc/bitmain-pub.pem` command — send it to your ASICs via the Hive web. It will temporarily delete the certificate, but you can reboot your ASIC to bring it back. After this, you will be able to move to any firmware via the firmware update menu (in the Hive web). It will be possible to choose the firmware from the list or to use the URL.
