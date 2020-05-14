---
title: Installation guide S17, S17 Pro, S17E, S17+
parent_category: Hiveon ASIC Firmware
category: S17, S17 Pro, S17E, S17+
---

### Important Notes
There are three ways to install Hiveon ASIC firmware for S17, S17 Pro, S17+ and S17E — everything depends on the stock firmware release date. We will cover all the options, so you will be able to install Hiveon ASIC firmware quickly and easily. 

Please note, that all the manual steps which involve using BTC_TOOLS can be done via ASIC’s web interface (BTC_TOOLS is usually used for a large number of devices).

### Preparation Stage (required for all the options):
1 .Download and unzip the following archive: http://download.hiveos.farm/asic/repo/fw/Antminer/s9k-s9se-st15-st17-installer.zip.

2. Scan the network using BTC_TOOLS and export the list to **csv**. From csv, copy the **IP list** and insert it in **ips.ini**. In case you don’t have a lot of devices, you can make this list manually.

3. Go to **config.ini** and check login and password for the ASIC’s SSH or web interface. If the password for the web interface was changed, the same would be for SSH. Set up **FARM_HASH** to connect to Hive or API, if necessary.

4. Download the firmware file (it has to have “Hiveon” in its title):
http://download.hiveos.farm/asic/s17/

For S17 and S17 Pro, we offer the same firmware file. It can be downloaded here:
http://download.hiveos.farm/asic/s17/Antminer-S17-S17pro-s17p-Hiveon.tar.gz

Now, let’s talk about 3 ways of installation in detail.

### If the stock firmware of your ASIC is released before 1 July 2019
1. Flash your devices with a file from the archive **“remsig_all_before_2019–07–01.tar.gz”**. This can be done via either ASIC’s web interface or BTC_TOOLS in case you have a lot of devices. You will see an error in status, but this is okay — it should be like this at the moment.

2. Flash the devices with the firmware file. Again, this can be done via either ASIC’s web interface or BTC_TOOLS.

3. Launch **“3_hash_farm_for_signed.cmd”** from the archive. The ASIC will get connected to the web.

### Stock firmware released from July 2019 to December 2019
1. Launch **“1_open_ssh.cmd”** from the archive and wait for the script to be performed. The devices will be rebooted. After the reboot, wait for around 3 minutes.

2. Launch **“2_upgrade_replace.cmd”** from the archive and wait for the script to be performed.

3. Flash the devices with the firmware file (via either ASIC’s web interface or BTC_TOOLS).

4. Launch **“3_hash_farm_for_signed.cmd”** from the archive. The ASIC will get connected to the web.

### Firmware released after 1 December 2019
In this case you will need an image for the SD card. Find the instruction [here](https://hiveos.farm/hiveon-asic-firmware-general-installation_sd_card).

We **do not recommend** to upgrade Antminer devices to the latest official firmware, as Bitmain doesn’t allow to install custom firmware.
