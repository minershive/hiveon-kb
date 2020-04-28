---
title: Installation guide S17 (S17 Pro)
parent_category: Hiveon ASIC Firmware
category: S17, S17 Pro
---

Have you decided to upgrade your ASIC Antminer S17 or S17 Pro with our custom firmware? Great! Here is a guide on how to install your new firmware. But before we go through the installation details, let us quickly explain to you what cool features our custom firmware has.

### Hiveon ASIC Firmware Features
**S17:**
- Up to 72TH/s with air cooling.

**S17 Pro:**
- 80.1TH/s with standard PSU connected;
- 85TH/s with liquid cooling.

**Moreover:**
- Higher energy efficiency thanks to undervolting;
- When ASIC is offline, the chips turn off;
- ASIC chips overclocking;
- Auto-tuning of worn ASIC chips (so they will live longer);
- Easy integration with Hive OS: only 2.8% dev fee (Hive OS is free for you in case you are a Hiveon ASIC user);
- Bugs of the stock firmware are fixed;
- If a fan or a chip fails, the LED will start blinking, so you will notice the problem immediately;
- Temperature and hashrate watchdogs;
- A wattmeter embedded in the web interface;
- Reliable virus protection;
- Recovery of those devices which were affected by viruses in the past.

Now let’s take a look at the main consumption profiles on S17.

<img src="https://miro.medium.com/max/1000/1*KkyVKuSSz0GTqCxOV1Wrrg.jpeg">

Check the full list in your Hive OS account.

### Important Notes
And now let’s go back to the installation process. There is no universal manual, for S17 and S17 Pro there are 3 versions of stock firmware. Therefore, every particular case has its own manual on the custom firmware installation. We will cover all of them.

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

So, now you know how to install our Hiveon ASIC firmware for Antminer S17 and S17 Pro. However, if you still have any questions, don’t hesitate to <a href="https://t.me/hiveonasic_en">contact us</a>.
