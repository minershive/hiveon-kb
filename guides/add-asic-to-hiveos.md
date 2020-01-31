---
title: Adding ASIC to Hive OS
category: Guides
---

## Adding ASIC to Hive OS
### Installation
You can install Hive OS Client on your ASIC via firmware file or via SSH.

**DO NOT upgrade your Antminer to firmware newer than 10.06.2019. This firmware is protected by Bitmain against changes.**.

### Web interface or btc-tools
Client for Antminer 3/7/9 series before 10.06.2019 firmware:
<a href="http://download.hiveos.farm/asic/repo/unsig/hive_install_unsig_antminers.tar.gz">hive_install_unsig_antminers.tar.gz</a>

Stock Bitmain firmware + intergated Hive OS client + Hive OS tab on web interface for **farm_hash**:
- <a href="http://download.hiveos.farm/asic/repo/unsig/S11-hive.tar.gz">Antminer S11</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/S15-hive.tar.gz">Antminer S15</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/T15-hive.tar.gz">Antminer T15</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/S17-hive.tar.gz">Antminer S17</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/S17pro-hive.tar.gz">Antminer S17pro</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/T17-hive.tar.gz">Antminer T17</a>

### SSH
Default SSH login and password:

Antminer - default user: **root**, default password: **admin**

Innosilicon - default (ssh/telnet) user:**root**, default password: **blacksheepwall** or **innot1t2** or **t1t2t3a5**

Login with SSH to your miner and run the following command:

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade`

For Antminer D3 **Blissz**, before installation run:

`ln -s /usr/lib/libcurl-gnutls.so.4 /usr/lib/libcurl.so.5`

Force set up FARM_HASH or RIG ID and password, change API URL:
`firstrun` or `firstrun FARM_HASH` - set when there is no config

`firstrun -f` or `firstrun FARM_HASH -f` - force set to replace the config

#### Prompt installation
You can use FARM_HASH to add ASIC automatically without entering rig ID and password. Get your hash and put it on the command line. (FARM_HASH=$FARM_HASH)

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && FARM_HASH=your_hash_from_web sh selfupgrade`

Change API server. (HIVE_HOST_URL=$HIVE_HOST_URL)

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && FARM_HASH=your_hash_from_web HIVE_HOST_URL=http://api.exaple.com sh selfupgrade`

### Bulk installation
You can install Hive on all the ASICs you have on your local network. Or you can install firmware on Antminer S9/i/j. For this you need to have running Linux computer (maybe Hive OS on GPU rig) or Antminer ASIC with Hive client. Download files with this command:

<pre><code>
apt-get install -y sshpass curl
cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/hive-asic-net-installer/download.sh && sh download.sh
cd /tmp/hive-bulk-install
</code></pre>

Edit `config.txt` to set your FARM_HASH or firmware URL, edit `ips.txt` to set IPs list of your new ASICs. Or you can scan the local network to search for Antminer. Example: `ipscan.sh 192.168.0.1/24 > ips.txt`

Optionally, you can add WORKER_NAME to `ips.txt` (e.g. `192.168.1.100 asic_01`).

To install Hive just run `install.sh`.

To install firmware on Antminer S9/i/j just run `firmware.sh`.

If IP was connected then it will become commented in file.

### Innosilicon new models
Manual: https://forum.hiveos.farm/t/innosilicon-t2t-t3-series/13610

### Downgrade and Version change
If you want to install specific version or downgrade please append version as an argument to selfupgrade. E.g. 0.1-02:

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade 0.1-02`

Locally on ASIC you can run `selfupgrade command`. To install specific version you should run `selfupgrade 0.1-02`. If you want to reinstall version please add `-f` to the command like this `selfupgrade 0.1-02 -f`. To install current development version from repository please run `selfupgrade master`.

**To display data in monitoring, be sure to create a flight sheet.**

### Uninstall
`hive-uninstall`

Cron jobs might have to be removed manually with `crontab -e`, even if they are left there they would do nothing.

### Innosilicon old models
Some Innosilicon factory firmware have a memory leak, and ASIC freezes every few days. To solve this problem, you can enable the miner or ASIC reboot every 24 hours. Run the following commands:

<pre><code>
inno-reboot miner enable/disable
inno-reboot asic enable/disable
inno-reboot status
</code></pre>

### asic-find (Antminer)
To search for an Antminer ASIC among a large number of ASICs, you can flash a red LED on it. To do this, execute the command via the web interface or via SSH:

`asic-find 5`

Example: `asic-find 15`, the red LED will blinking for 15 minutes.

### Rename ASICs
To rename the workers in the Hive web interface as the hostname, run the command from the web interface:

`hello hostname`

### Zig Z1+
<a href="https://github.com/minershive/hiveos-asic/blob/master/hive/share/zig/README.md">Zig Z1+ ssh manual</a>

`cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade`

or

`cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && FARM_HASH=your_hash_from_web bash selfupgrade`

### Antminer S9 signed (deprecated)
<a href="https://forum.hiveos.farm/t/antminer-s9-signed/12466">Manual</a>

### Antminer S17/S17 Pro/T17 (deprecated)

<a href="https://forum.hiveos.farm/t/antminer-s17-t17/12415">Manual</a>

<a href="bee@hiveos.farm">Support</a>

### Recovery Antminer
S17/S17pro/T17

Download <a href="http://download.hiveos.farm/asic/repo/t17-s17/recovery_sd/t17_rec.zip">Recovery image</a>, unzip to SD card. Boot ASIC with SD card. Flash tar.gz firmware via web interface.
