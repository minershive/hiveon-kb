---
title: Adding ASIC to Hive OS
category: Guides
---

### Prepare
Beware of recent Bitmain firmware:
- Antminer Series 9 (S9/S9i/S9j/T9/T9+): never upgrade to firmware newer than 10-Jun-2019
- Antminer Series 17: never upgrade to firmware newer than 01-Dec-2019

All newer versions of official firmware have defensive countermeasures against remote tampering, so you won't be able to install Hive OS Client or Hiveon ASIC Firmware.

### Install
You can install Hive OS Client via firmware file download or via SSH.

#### Three basic install options
**1. ASIC web interface**

**Antminer Series 15, Series 17 and Series 9 models S9k and S9SE**

These models are special. They're loading OS right to the RAM in read-only mode. Hive OS Client installation is possible only by upgrading ASIC with a special firmware file. That file contains stock Bitmain firmware with built-in Hive OS client:

- [Antminer S9k](https://download.hiveos.farm/asic/S9k/stock%2Bclient/S9k-stock%2Bclient-20190929.tar.gz)
- [Antminer S9SE](https://download.hiveos.farm/asic/S9se/stock%2Bclient/S9se-stok%2Bclient.tar.gz)
- [Antminer S11](https://download.hiveos.farm/asic/S11/stock%2Bclient/S11-hive.tar.gz)
- [Antminer S15](https://download.hiveos.farm/asic/S15/stock%2Bclient/S15-%28stock%2Bclient%29-v19.08.12-ln.tar.gz)
- [Antminer T15](http://download.hiveos.farm/asic/T15/stock%2Bclient/T15-%28stock%2Bclient%29-v19.08.12-ln.tar.gz)
- [Antminer S17, S17 pro](http://download.hiveos.farm/asic/s17/stock%2Bclient/)
- [Antminer S17+](http://download.hiveos.farm/asic/S17%2B/stock%2Bclient/)
- [Antminer S17E](http://download.hiveos.farm/asic/S17E/stock%2Bclient/)
- [Antminer T17](http://download.hiveos.farm/asic/T17/stock%2Bclient/)
- [Antminer T17+](http://download.hiveos.farm/asic/T17%2B/stock%2Bclient/)
- [Antminer T17E](http://download.hiveos.farm/asic/T17E/stock%2Bclient/)

>After successful flashing, you have to open up ASIC web interface, click Hive OS tab, enter your FARM_HASH and then click Apply&Save button. The page will refresh itself. Wait a minute and worker will appear in the Hive dashboard.

**All other Antminer Series 3/7/9**

Hive OS Client for Antminer Series 3/7/9, firmware date before 10.06.2019. Just upgrade ASIC firmware with [hive_install_unsig_antminers.tar.gz](http://download.hiveos.farm/asic/repo/unsig/hive_install_unsig_antminers.tar.gz).

**2. BTC Tools**

All things you do with an ASIC web interface you could do better with [BTC Tools](https://url.btc.com/btc-tools-download) utility. It's the best choice in case you have ASICs in numbers. Scan your network, select ASICs to update and then click "Firmware Upgrade".

**3. SSH**

Login with SSH to your miner and run the following command:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade`

For Antminer D3 **Blissz**, before installation run:

`ln -s /usr/lib/libcurl-gnutls.so.4 /usr/lib/libcurl.so.5`

Force set up FARM_HASH or RIG ID and password, change API URL:

`firstrun` or `firstrun FARM_HASH` - set when there is no config

`firstrun -f` or `firstrun FARM_HASH -f` - force set to replace the config

Default SSH logins and passwords:

Antminer - default user: **root**, default password: **admin**

Innosilicon - default (ssh/telnet) user:**root**, default password: **blacksheepwall** or **innot1t2** or **t1t2t3a5**

>If other login and password values were set up before you, then reset the ASIC to the factory settings. To do this, on the turned on ASIC, hold the ipreport and reset buttons, hold for 20 seconds, turn off the power supply, without releasing the pressed buttons. Wait for 10 seconds, without releasing the ipreport and reset buttons, turn on the power supply and hold ipreport and reset for 20 more seconds. Then release and wait for the load.

### Options for automation
#### Promptless installation
You could add ASIC without entering RIG_ID, password and API Server URL.

**To add ASIC without entering RIG\_ID and password, you should fill FARM_HASH variable.**

Get your FARM\_HASH from Hive OS dashboard. Replace `your_farm_hash` string you see below with your FARM\_HASH. Transform the text below and then run as a single command:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade --farm-hash=YOUR_FARM_HASH`

**To use another API Server, you should fill HIVE\_HOST\_URL variable.**

Replace `http://your_api_server` string you see below with your API Server URL. Transform the text below and then run as a single command:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade --hive-host-url=http://your_api_server`

**Of course you could set FARM\_HASH and API Server simultaneously.**

Replace `your_farm_hash` string you see below with your FARM\_HASH. Replace `http://your_api_server` string you see below with your API Server URL. Transform the text below and then run as a single command:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade --farm-hash=YOUR_FARM_HASH --hive-host-url=http://your_api_server`

### Bulk installation
You can install Hive OS Client on all the ASICs you have on your local network. For this you need to have a running Linux box (like Hive OS GPU rig) or Antminer ASIC with Hive OS Client. You could do it with just three commands.

1. Skip this step if you're on the ASIC with Hive OS Client. Install sshpass and curl:

`apt-get install -y sshpass curl`

2. Download script:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/hive-asic-net-installer/download.sh && sh download.sh`

3. Execute it:

`cd /tmp/hive-bulk-install`

Edit `config.txt` to set your FARM_HASH or firmware URL, edit `ips.txt` to set IPs list of your new ASICs. Or you can scan the local network to search for Antminer. Example: `ipscan.sh 192.168.0.1/24 > ips.txt`

To install Hive OS Client just run `install.sh`.

To install firmware on Antminer S9/i/j just run `firmware.sh`.

>Optionally, you can add WORKER_NAME to `ips.txt` (e.g. `192.168.1.100 asic_01`).

>When IP was being processed then it will become #commented.

### Other models

#### Antminer S9 signed (please use Hiveon firmware)
[Hiveon ASIC installation - Antminer S9 Cannot Find Signature Fix](https://forum.hiveos.farm/t/hiveon-asic-installation-antminer-s9-cannot-find-signature-fix/12466)

[Hiveon ASIC firmware 1.02 for S9 installation manual](https://forum.hiveos.farm/t/hiveon-asic-s9-firmware-v1-02/13944)

#### Antminer S9 (MSKMINER), S10 (MSKMINER)
You don't need to unlock SSH or do anything complicated. For any ASIC with mskminer custom firmware, you have to download [Hive OS Client Installer for MSKMINER firmware](http://download.hiveos.farm/asic/repo/s9/hive-msk-installer.tar.gz) and then flash the ASIC with it. That's all.

#### Antminer S17/S17 Pro/T17
[Hiveon ASIC firmware installation manual](https://hiveos.farm/hiveon-asic-firmware-S17-S17-Pro-s17installation)

#### Innosilicon new models
[Hive OS Client installation manual for Innosilicon](https://forum.hiveos.farm/t/innosilicon-t2t-t3-series/13610)

#### Innosilicon old models
Note: some Innosilicon factory firmware have a memory leak, and ASIC freezes every few days. To solve this problem, you can enable the miner or ASIC reboot for every 24 hours. Run the following commands:

<pre><code>
inno-reboot miner enable/disable
inno-reboot asic enable/disable
inno-reboot status
</code></pre>

#### Todek Toddminer C1
`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade`

or, if you need to use FARM_HASH

`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade --farm-hash=YOUR_FARM_HASH`

#### Zig Z1+
[Hive OS Client installation manual for Zig Z1+](https://github.com/minershive/hiveos-asic/blob/master/hive/share/zig/README.md)

`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade`

or, if you need to use FARM_HASH

`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && selfupgrade --farm-hash=YOUR_FARM_HASH`

### Start working in Hive OS
#### Get FARM_HASH
To link ASIC to your Hive Farm you could use these options, sorted by ease:

- Hive OS tab in the ASIC web interface (simpliest!)
- `firstrun` command via SSH
- Download a special .tar.gz file via BTC Tools (mass deployment)

In all cases, you'll need the FARM_HASH string. You will find it in Hive OS dashboard, right in the farm's Settings tab.

#### Create and Apply the Flight Sheet
To start mining, be sure to create a Flight Sheet first. Apply it to start hashing.

### Useful commands
#### asic-find (Antminer)
To search for an Antminer ASIC among a large number of ASICs, you can flash a red LED on it. To do this, execute the command via the web interface or via SSH:

`asic-find 5`

The red LED will be blinking for 5 minutes.

#### Rename the workers
To rename the workers in the Hive web interface as the hostname, run the command from the web interface:

`hello hostname`

### Downgrade and Version change
If you want to install specific version or downgrade please append version as an argument to selfupgrade. E.g. 0.1-02:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade 0.1-02`

To see all selfupgrade options, run `selfupgrade --help`

To install specific version you should provide a release number: `selfupgrade 0.1-14`

If you want to reinstall current version, add --force: `selfupgrade --force`

To install stable development version, run `selfupgrade master`

To install night build development version directly from Github, run `selfupgrade master --github`

### Uninstall
`hive-uninstall`

`Cron` jobs might have to be removed manually with `crontab -e`, even if they are left there they would do nothing.

### Recovery boot images
#### Antminer
You can find recovery boot images at [repository](https://download.hiveos.farm/asic/) (highly recommended) or [Bitmain's official site](https://service.bitmain.com/support/download?product=Flashing%20SD%20card%20with%20image).

>Please note the two different file formats of recovery images:
- `.img` file. It's a raw disk image. Should be written to SD with a special imaging software.
- `.zip` file. A ZIP archive containing files like `u-boot.img` and `uImage.bin` inside. Unzip that file to SD card formatted with FAT32.

- [S9 Recovery image](https://download.hiveos.farm/asic/s9/recovery-stock/Recovery_S9.img)
- [S17 Hiveon recovery image](http://download.hiveos.farm/asic/s17/SD-S17-S17pro_Hiveon_2.00-200608_sig.zip)
- S17, S17 Pro, T17
	- Download [recovery boot image](https://download.hiveos.farm/asic/s17/recovery-stock/SD_S17-T17_650M.05.06.2019.zip)
	- Use SD card <16 Gb
	- Format SD card with FAT32
	- Unzip it to SD card
	- Boot ASIC with SD card
	- ASIC booted in recovery mode
	- Flash any suitable [old stock Bitmain firmware](https://download.hiveos.farm/asic/) (.tar.gz format) via web interface.

In case of issues, please read Bitmain's [control board program recovery manual](https://support.bitmain.com/hc/en-us/articles/360033757513-S17-S17Pro-S9-SE-S9k-Z11-control-board-program-recovery-SD-card-flashing-with-customized-PW-).
