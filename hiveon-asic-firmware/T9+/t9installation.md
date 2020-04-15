---
title: Installation Guide T9+
parent_category: Hiveon ASIC Firmware
category: T9+
---

## Hiveon ASIC Firmware Installation Guide: T9+
___The installation here is described on the example of S9 - the process is the same for T9+.___

While current cryptocurrency prices keep wildly fluctuating, miners need any advantage they can get in order to stay on top of their game and keep making profits. With that in mind we set out to make something that will give them that advantage and decided to bring some love to our ASIC users by introducing Hiveon ASIC.

### What is it and how it works
If we were to describe it in a nutshell, then Hiveon ASIC is a custom firmware that boosts an ASIC’s performance by increasing its output by approximately 1TH/s while staying at the same power consumption level. It allows the ASIC to get approximately 16.3–16.4TH/s on a standard power supply or up to 19TH/s on custom more “beefy” power supplies. Though this power consumption optimisation works only with pools that have implemented support for <a href="https://www.asicboost.com/">AsicBoost</a>, a patent-pending technology that lowers power consumption while letting you maintain the same hashrate.

That’s a significant boost, but how is it achieved? Unlike the stock firmware, where you click and mine right away, Hiveon ASIC sets the frequency to each chip individually rather than a single value across all chips simultaneously. It controls the frequency of each chip allowing you to lower the frequencies on “bad” chips, and raise them on the “good” ones. This way you’re getting more hashrate with less consumption in watts enabling the chips to live longer without wearing them out as fast.

The chip tuning is as simple as choose a profile from a preset list with the desired power consumption level that gives you an approximation of the expected hashrate. Then the autotune script initiates and begins fine tuning each chip individually, checking for potential chip errors, checks optimal load, etc. This can easily take up to half an hour or more until the script finds the ideal parameters for each chip.
**Our firmware includes a 2% devfee** while you’ll still be getting higher profit than with the stock firmware.

## Installation Options
There are no one-size-fits-all instructions, instead we’re going to cover three scenarios of installing or updating your machines with Hiveon ASIC. The following topics will be covered:

- Installing using ASICs via web interface — suitable for installing on a handful of machines for users who haven’t used Hive OS before;
- Bulk installation — suitable for installing unto entire farms;
- Updating existing ASICs via Hive OS’s web interface — suitable for those who’re already using Hive with their ASICs;
- Bulk updating existing ASICs — suitable for updating entire farms in a few clicks.

### Option 1: Installing using ASIC’s web interface
Go to your farm’s **Settings** tab, there you will see the **Download Firmware** button, click it to begin downloading the file locally.

<img src="https://miro.medium.com/max/1569/0*7hZoOcAZB2chkUG_">

When your ASIC is powered up and assuming it’s on the same network with you, connect to it using a computer or a mobile device. Enter your miner’s IP address. Most miners come with DHCP enabled thus you do not have to manually set an IP address, for it. Instead look at the IP table on your router or use a scanning tool.

<img src="https://miro.medium.com/max/1594/0*eboE5sjqgcnXDAuM">

Log in into the miner. In our case we’re using an S9 as an example. The default username login is root and the password is also root. You’ll be logged in the system overview window. If this is your first time setting up an ASIC don’t forget change the password from the default in the Admin tab first.

<img src="https://miro.medium.com/max/1594/0*CPGII9JKr1qVvZOL">

Go into the **Upgrade** tab, there you will see the **Flash new firmware** image section. Click the **Choose File** to choose the image you previously downloaded and then click the **Flash image…** button and wait for it to install.
Now we’ll need to get your Farm Hash in the <a href="https://the.hiveos.farm/">Hive OS web UI</a>. Go to your farm’s **Settings** tab, there you will see your **Farm Hash**, copy it to clipboard.

<img src="https://miro.medium.com/max/1569/0*wkNCiVtWtNRB92s7">

As soon as the ASIC was flashed and rebooted, reconnect to it and go to the **Hive OS** tab in the **System window**. Paste your Farm Hash in to the **FARM_HASH** field and click **Save & Apply**. Your ASIC will be added to your farm in Hive OS.

<img src="https://miro.medium.com/max/1750/0*sPTOf6QkmcQhBkxI">

You’re done, now you can configure your ASIC.

### Option 2: Bulk Installation
To bulk install our firmware across multiple ASICs, you’ll need either a computer with Linux or a rig with Hive OS installed on it, that’s on the same network with your other ASIC machines.
To install from a computer with Linux (or a rig running Hive OS), download the bulk install scripts first by running the following command:

<pre><code>
apt-get install -y sshpass curl

cd /tmp && curl -L — insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/hive-asic-net-installer/download.sh && sh download.sh

cd /tmp/hive-bulk-install
</code></pre>

Once all the files are downloaded go to the `/tmp/hive-bulk-install` directory. You’ll need to add the ASICs’ IPs into `ips.txt`. If you know the list of IPs already then enter them one per line in `ips.txt` file. If the full list of IPs isn’t known to you, then you can scan your LAN and search for all Antminers using the following command:

`ipscan.sh 192.168.0.1/24> ips.txt`

**Warning! The script will find all the ASICs in the network, not just S9, S9i, S9j, T9 or T9+. And you must not flash anything other than S9/T9 series with this firmware!**

Now we’ll need to get your Farm Hash in the <a href="https://the.hiveos.farm/">Hive OS web UI</a>. Go to your farm’s **Settings** tab, there you will see the **Download Firmware** and copy the link. It will be pre-formatted to include your Farm Hash. For example:

`http://download.hiveos.farm/asic/s9/Antminer-S9-all-Hiveon-YOUR_FARMHASH.tar.gz`

<img src="https://miro.medium.com/max/1569/0*kO65_Y2NDstOrUHV">

Enter this link in the `config.txt` file. It should look like this:

`URL=http://download.hiveos.farm/asic/s9/Antminer-S9-all-Hiveon-YOUR_FARMHASH.tar.gz`

Once you’re done, run the firmware.sh script to install the custom firmware. The script will flash the ASICs from the IP list. ASICs that were already flashed with the custom firmware will be commented out in the list of the IPs. This is useful in case you need to suddenly stop the flashing procedure as this way the machines that got flashed already, will be excluded next time you run the script.

*For more details regarding other ASIC installation options, please refer to this <a href="https://github.com/minershive/hiveos-asic">GitHub page</a>.*

## Hiveon ASIC auto tuner configuration
After installing the new firmware you can now login back into your ASIC miner. This time you’ll be greeted by the new Hiveon ASIC UI overview page. Lets look at Profiles and basic configs for the time being.

**Attention! In order to use most of these options, you need to have a custom power supply connected to your ASIC. The factory PSU is not powerful enough to handle the load and your ASIC will turn off.**

<img src="https://miro.medium.com/max/1598/0*p_4TaOOpSKRnJPP9">

In order to choose the **Profile** you want, go to the **Miner Configuration** tab, then click the **Auto tuner configuration** tab. There you can choose the Profile that suits your needs best. A small disclaimer first: **We don’t recommend choosing Manual mode unless you have sufficient skills in manually fine tuning an ASIC.** We won’t be covering the manual procedure as this profile is too difficult to explain in a short comprehensive form.

<img src="https://miro.medium.com/max/1589/0*pNPYfVdlrcuFH7fg">

Then click the **Apply Changes** button at the bottom of the page and wait for the algorithm to finish auto tuning the ASIC. This may take up to an hour depending on the selected profile. Your hashrates may wildly fluctuate during the process — this is normal.

## Updating Options

## Option 1: Updating using Hive OS’s web interface
Assuming you’re already using Hive OS with your ASICs, you’ll need to update them to the compatible firmware first. If your ASIC model is compatible, you’ll see a yellow **Switch** text near the OS version at the bottom of your worker **Overview** page.

<img src="https://miro.medium.com/max/429/0*SY96QIG33Br2aa8_">

Click it and a new **Change ASIC Firmware** context window will pop-up. Then click the **Select firmware** dropdown list and choose the appropriate firmware version. In this example it’ll be the **Antminer-S9-all-Hiveon**. Click **Apply**.

<img src="https://miro.medium.com/max/1260/0*ssmeT6INSpHJgLKg">

The ASIC will go offline and reboot, then it will re-appear as online shortly and it’s model name will change from Antminer S9 to Antminer S9 Hiveon (from T9 to T9 Hiveon accordingly). The firmware version will also change.

<img src="https://miro.medium.com/max/1581/0*lp4ZUANA-e0btQfk">

You’re done, now you can configure your ASIC using the auto tuner.

*For more details regarding other ASIC installation options, please refer to this <a href="https://github.com/minershive/hiveos-asic">GitHub page</a>.*

## Option 2: Bulk Update
Assuming you’re already using Hive OS with your ASICs, you’ll need to update them to the compatible firmware first.

<img src="https://miro.medium.com/max/1590/0*6FpiMVYCUCghtbC1">

In the **Workers** tab, select the workers you want to update. You’ll see several actions appear in the top right corner of the screen.

<img src="https://miro.medium.com/max/911/0*KkPY3QOPvbUkbrpd">

Click the **ASIC Firmware** button and a new **Change ASIC Firmware** context window will pop-up. Then click the **Select firmware** dropdown list and choose the appropriate firmware version. In this example it’ll be the **Antminer-S9-all-Hiveon**. Click **Apply**.

<img src="https://miro.medium.com/max/1260/0*AWw3uCKwWV_jvxNB">

The ASICs will go offline and reboot, then they will re-appear as online shortly and their model names will change from Antminer S9 to Antminer S9 Hiveon (from T9 to T9 Hiveon accordingly). The firmware version will also change.

<img src="https://miro.medium.com/max/1581/0*869YrhWn8EAKGOhz">

You’re done, now you can configure your ASIC using the auto tuner.

*For more details regarding other ASIC installation options, please refer to this <a href="https://github.com/minershive/hiveos-asic">GitHub page</a>.*

## Hive OS web UI auto tuner configuration
Once your ASICs were successfully flashed, you can then set our pre-created auto tuning profiles. There you can choose the Profile that suits your needs best. A small disclaimer first: **We don’t recommend choosing Manual mode unless you have sufficient skills in manually fine tuning an ASIC.** We won’t be covering the manual procedure as this profile is too difficult to explain in a short comprehensive form.

**Attention! In order to use most of these options, you need to have a custom power supply connected to your ASIC. The factory PSU is not powerful enough to handle the load and your ASIC will turn off.**

In the **Workers** tab, select the workers you want to run the auto tuning script on.

<img src="https://miro.medium.com/max/1590/0*VaoCeqoiLP3rbK8k">

You’ll see several actions appear in the top right corner of the screen. Click the **Overclocking** button and a new context window will appear.

<img src="https://miro.medium.com/max/959/0*OGNBrUL3NWFR-CVn">

Select the profile you want then click the **Apply Changes** button at the bottom of the window and wait for the algorithm to finish auto tuning the ASIC. This may take up to an hour depending on the selected profile. Your hashrates may wildly fluctuate during the process — this is normal.

<img src="https://miro.medium.com/max/560/0*RYEhl5muvMs9S8su">

And you’re all done! Congratulations and happy mining!
