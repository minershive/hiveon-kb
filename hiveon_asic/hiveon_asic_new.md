title: Hiveon ASIC — New User’s Initial Installation and Setup Manual

## Hiveon ASIC — New User’s Initial Installation and Setup Manual
<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/header.jpeg?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/header.jpeg"
  />

Our firmware includes a 2% devfee while you’ll still be getting higher profit than with the stock firmware.

### Installation Options
There are no one-size-fits-all instructions, instead we’re going to cover three scenarios of installing or updating your machines with Hiveon ASIC. We’ve split the process into two articles.

Part one will cover the following topics:

* __Installing using ASICs via web interface__ — suitable for installing on a handful of machines for users who haven’t used Hive OS before;
* __Bulk installation__ — suitable for installing unto entire farms.

[Part two](/hiveon_asic/hiveon_asic_old.md) will discuss the options for:

* __Updating existing ASICs via Hive OS’s web interface__ — suitable for those who’re already using Hive with their ASICs;
* __Bulk updating existing ASICs__ — suitable for updating entire farms in a few clicks.

### Installing using ASIC’s web interface

**Before we go into the installation details, keep in mind that currently this custom firmware is available for Antminer S9, S9i and S9j only. Other models will be available soon.**

Go to your farm’s **Settings** tab, there you will see the **Download Firmware** button, click it to begin downloading the file locally.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh.png"
  />

When your ASIC is powered up and assuming it’s on the same network with you, connect to it using a computer or a mobile device. Enter your miner’s IP address. Most miners come with DHCP enabled thus you do not have to set an IP address for it manually. Instead look at the IP table on your router or use a scanning tool.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/antminer_overview.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/antminer_overview.png"
  />

Login into the miner. In our case we’re using an S9 as an example. The default username login is `root` and the password is also `root`. You’ll be logged in the system overview window. If this is your first time setting up an ASIC don’t forget change the password from the default in the Admin tab first.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/antminer_upgrade.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/antminer_upgrade.png"
  />

Go into the **Upgrade** tab, there you will see the **Flash new firmware image** section. Click the **Choose File** to choose the image you previously downloaded and then click the **Flash image…** button and wait for it to install.

Now we’ll need to get your Farm Hash in the <a href="https://the.hiveos.farm/">Hive OS web UI</a>. Go to your farm’s **Settings** tab, there you will see your **Farm Hash**, copy it to clipboard.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh_download.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh_download.png"
  />

As soon as the ASIC was flashed and rebooted, reconnect to it and go to the **Hive OS** tab in the **System** window. Paste your Farm Hash in to the **FARM_HASH** field and click **Save & Apply**. Your ASIC will be added to your farm in Hive OS.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh_setup.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh_setup.png"
  />

_You’re done, now you can configure your ASIC._

### Hiveon ASIC auto tuner configuration
After installing the new firmware you can now login back into your ASIC miner. This time you’ll be greeted by the new Hiveon ASIC UI overview page. Lets look at **Profiles** and basic configs for the time being.

_**Attention! In order to use most of these options, you need to have a custom power supply connected to your ASIC. The factory PSU is not powerful enough to handle the load and your ASIC will turn off.**_

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/asic_overview.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/asic_overview.png"
  />

In order to choose the **Profile** you want, go to the **Miner Configuration** tab, then click the **Auto tuner configuration** tab. There you can choose the Profile that suits your needs best. A small disclaimer first: **We don’t recommend choosing Manual mode unless you have sufficient skills in manually fine tuning an ASIC.** We won’t be covering the manual procedure in any of our articles as this profile is too difficult to explain in a short comprehensive form.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/asic_profiles.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/asic_profiles.png"
  />

Then click the **Apply Changes** button at the bottom of the page and wait for the algorithm to finish auto-tuning the ASIC. This may take up to an hour depending on the selected profile. Your hashrates may wildly fluctuate during the process — this is normal.

### Bulk Installation
To bulk install our firmware across multiple ASICs, you’ll need either a computer with Linux or a rig with Hive OS installed on it, that’s on the same network with your other ASIC machines.

To install from a computer with Linux (or a rig running Hive OS), download the bulk install scripts first by running the following command:

`apt-get install -y sshpass curl`

`cd /tmp && curl -L — insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/hive-asic-net-installer/download.sh && sh download.sh`

`cd /tmp/hive-bulk-install`

Once all the files are downloaded go to the `/tmp/hive-bulk-install` directory. You’ll need to add the ASICs’ IPs into `ips.txt`. If you know the list of IPs already then enter them one per line in `ips.txt` file. If the full list of IPs isn’t known to you, then you can scan your LAN and search for all ant-miners using the following command:

`ipscan.sh 192.168.0.1/24> ips.txt`

**Warning! The script will find all the ASICs in the network, not just S9, S9i or S9j. And you must not flash anything other than S9 series with this firmware!**

Now we’ll need to get your Farm Hash in the <a href="https://the.hiveos.farm/">Hive OS web UI</a>. Go to your farm’s **Settings** tab, there you will see the **Download Firmware** and copy the link. It will be pre-formatted to include your Farm Hash. For example:

`http://download.hiveos.farm/asic/s9/Antminer-S9-all-Hiveon-YOUR_FARMHASH.tar.gz`

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh_download.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/fh_download.png"
  />

Enter this link in the `config.txt` file. It should look like this:

`URL=http://download.hiveos.farm/asic/s9/Antminer-S9-all-Hiveon-YOUR_FARMHASH.tar.gz`

Once you’re done, run the firmware.sh script to install the custom firmware. The script will flash the ASICs from the IP list. ASICs that were already flashed with the custom firmware will be commented out in the list of the IPs. This is useful in case you need to suddenly stop the flashing procedure as this way the machines that got flashed already, will be excluded next time you run the script.

_For more details regarding other ASIC installation options, please refer to this [GitHub page](https://github.com/minershive/hiveos-asic)._

### Hive OS web UI auto tuner configuration
Once your ASICs were successfully flashed, you can now go into the use our pre-created auto-tuning profiles. There you can choose the Profile that suits your needs best. A small disclaimer first: **We don’t recommend choosing Manual mode unless you have sufficient skills in fine-tuning an ASIC manually.** We won’t be covering the manual procedure in any of our articles as this profile is too difficult to explain in a short comprehensive form.

_**Attention! In order to use most of these options, you need to have a custom power supply connected to your ASIC. The factory PSU is not powerful enough to handle the load and your ASIC will turn off.**_

In the **Worker** tab, select the workers you want to run the auto tuning script on.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/asic_list.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/asic_list.png"
  />

You’ll see several actions appear in the top right corner of the screen. Click the **Overclocking** button and a new context window will appear.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/oc.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/oc.png"
  />

Select the profile you want then click the **Apply Changes** button at the bottom of the window and wait for the algorithm to finish auto-tuning the ASIC. **This may take up to an hour** depending on the selected profile. Your hashrates may wildly fluctuate during the process — this is normal.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/power_profiles.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_new/power_profiles.png"
  />

And you’re all done! Congratulations and happy mining!
