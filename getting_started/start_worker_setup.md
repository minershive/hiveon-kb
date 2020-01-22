---
title: Worker Installation and Setup
---

## Getting Started with Hive OS — Worker Installation and Setup
<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/header.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/header.png"
  />

Hive OS is an all-in-one monitoring and management tool for your mining rigs. Whether its a single rig or several thousands, you and your team can easily manage them all from a single dashboard.

In this article we’ll walk you through the first time installation process and explain what different installation types there are, and how to easily set up your rigs and connect them to your account dashboard.

### Creating An Account
Before installing Hive OS on your rig, we recommend <a href="https://the.hiveos.farm/">creating an account</a> first, or logging into your <a href="https://the.hiveos.farm/">existing one</a>. Make sure to create a secure password.

>_We strongly suggest setting up Two Factor Authentication (2FA) for additional account security. You can find these settings by clicking on your user name in the top right corner and then going to the Account tab. Scroll down to the Two-factor Authentication option and switch 2FA on then follow the onscreen instructions carefully._

### Adding Your Workers
As soon as you’re done with setting up your account, it’s time to connect your rigs to the dashboard. GPU rigs and ASICs are uniformly referred to as workers. You will have two options of connecting your workers, via **Farm Hash** or via **manual setup**. Farm Hash is used for connecting your workers to a Farm without pre-creating the rig in the dashboard. This is our new and fast method of connecting a worker to a Farm, so we recommend this setup method for most users. We will go into more details on Farms and how to use them in our next articles.

1. **Farm Hash**

Each Farm has its unique Farm Hash. You can find your Farm Hash by going to your Farm’s Settings tab. Once you write the installation image, you may then add your `FARM_HASH` to the `rig.conf` file which you will find in the root folder of the image. We’ll explain this step in detail below.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/fh_sample.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/fh_sample.png"
  />

Farm Hash can be effectively used with Hive Flasher for bulk rig installations. More details on Hive Flasher are available <a href="https://github.com/minershive/hive-flasher">here</a>.

2. **Manual Setup**

Users that have previously used Hive OS will be familiar with this option of connecting their worker to the dashboard. It involves using a rig ID and a password for each miner to be configured. Although it’s a bit more tedious than connecting workers via Farm Hash, we left it for our old school users’ convenience.

Click on the plus in the top right corner and choose Add Worker option.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/add_worker.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/add_worker.gif"
  />

A window, Add New Worker, will pop up with the following fields:

1. Choose between **GPU** or **ASIC** type.
2. **Name** — your rig name. This can be anything. For example, _rig01_; _garage_rig_; etc. or leave it blank.
3. **Password** — your miner’s password. You can enter a convenient password for you, or generate one by clicking the double arrow button instead.
4. **Tags** — custom tags to help you logically separate projects by filters for various farms and workers. Tags can be created by going to the Settings tab.
5. **Description** — your rigs description. This is for your convenience only. For Example: _The rig at my parent’s garage_; _Store room rig_; _Rig on Park St. 251, that I only use for mining Monero_; etc.
6. Once done, click the **Add** button.

You will now see your rig added to the list of workers, but first you will need your rig ID. After you pre-created your worker, you will be forwarded to the worker’s dashboard. Go to the worker’s Settings tab and you should see the rig ID and the Password.

The ID of the rig and the password will be needed during the initial installation and first boot, in case you opted for this option instead of Farm Hash, so we recommend writing it down.

### Choosing An Installation Type
Hive OS can be installed on both GPU rigs and ASICs as well. Below we will describe the different types of installations:

* GPU — installs the OS on GPU based rigs
* ASIC — installs the OS on ASIC miners

### Downloading The Image
Go to the <a href="https://hiveos.farm/install/">download</a> page to get the latest version of Hive OS. You can download the image from our website as a .zip file or via .torrent if you prefer. You will also have the option of downloading Hive OS for ASICs or our Bulk Installation tool.

>_We recommend installing the OS image to an SSD. SSDs are much more reliable and we advise using them in production environments. Because many users still prefer using a USB flash drive, we have the logs turned off by default. If you installed the OS on an SSD, you can optionally turn logging back on by running the logs-on command after installation._

Here is some more information on flash drives, SSD and HDD:
When to use flash drives? Firstly when you want to test. This is easy, you just grab one you have and in a dozen of minutes you can plug it in and test Hive without ruining your current Windows, for instance). Any flash will work, USB 3.0 is not required. It’s just a matter of boot speed. Then if you are happy with it you can leave it as it is.

The downfalls of using flash pen drives. They are slow to write. Even if it’s 3.0 it still may have slow writes speed line 10-15mbps, while reading can be 60-100mbps. So waste time on writing new images if you have a lot of rigs.

They can work like forever or die in few days. Some show you corrupt file system with messages like this:
<img src="https://forum.hiveos.farm/uploads/editor/4f/bggzcyridn1z.jpg" alt="corrupt file system"/>

Some even fail to boot.

But what is great about the flash drives is that they are cheap. You can buy a bucket of them and just throw them out when they fail.

But if your location is distant this is not your choice. Go SSD. SSD is the best option. The only bad thing is the price. Probably you can find some cheap on aftermarket.

HDD. This is the option if you just have it and that’s it. The price for 32gb SSD and 200gb HDD is roughly the same and there is no reason you should choose HDD over SSD.

And the last thing. Buy a SSD USB 3.0 pocket or tray to connect it to your computer.
<img src="https://forum.hiveos.farm/uploads/editor/ac/d1xfobk7avkl.jpg" alt="SSD USB 3.0 pocket"/>
From version 0.5-30 you can run `logs-off` to put log in RAM to save your USB flash drive.

And a few more words about common booting problems.
In general you just plug your drive in the rig and it goes. But sometimes it just doesn’t.
Firstly you should ensure you are not trying to boot from UEFI partition. Some bioses give you this option to choose and you should not do it.
<img src="https://forum.hiveos.farm/uploads/editor/b0/5rpntezwp5sf.jpg" alt="booting problem"/>

Your USB settings should have Legacy mode On. Like for mouse and keyboard to work at boot time, otherwise USB drive will not be detected.
IOMMU might be an issue on some motherboards. Sometimes it’s called CSM (compatibility support module)
<img src="https://forum.hiveos.farm/uploads/editor/sa/nkq21zwkxe4t.jpg" alt="legacy mode"/>

Okay, drive is detected it starts but fails after like this:
<img src="https://forum.hiveos.farm/uploads/editor/bn/ebj16b6y9jub.jpg" alt="drive failure"/>
This tells you that’s there is some problem with the image written. Usually it’s solved with trying to write the image with alternative software:
<a href="https://www.balena.io/etcher/">Etcher</a>
<a href="https://rufus.ie">Rufus</a>
<a href="http://www.chrysocome.net/dd">Chrysocome</a>
<a href="https://sourceforge.net/projects/win32diskimager/">Source Forge</a>
<a href="http://hddguru.com/software/HDD-Raw-Copy-Tool/">HDD Raw Copy Tool</a>

### GPU Installation

#### Writing Disk Image
You will need to write Hive OS image onto an SSD. Although many user prefer to use USB drives, we recommend opting to an SSD instead. Start by extracting the image from the .zip file first and then writing the .img file onto a drive.

**Windows** user can write the image using <a href="http://hddguru.com/software/HDD-Raw-Copy-Tool/">HDD Raw Copy Tool</a>, <a href="https://sourceforge.net/projects/win32diskimager/">Win32 Disk Imager</a>, <a href="https://rufus.akeo.ie/">Rufus</a> or <a href="https://etcher.io/">Etcher</a>.

**MacOS** and **Linux** users can do it with ease using <a href="https://etcher.io/">Etcher</a>, or several other programs.

After the image is flashed you will discover a newly created drive in your system where you will be able to pre-configure your worker with either Farm Hash or it’s ID and password. Find `rig-config-example.txt` on HIVE drive and open it with a .txt editor. You can use the integrated text editors on Windows, MacOS and Linux or download a free alternative. For example, <a href="https://notepad-plus-plus.org/">Notepad++</a> for Windows or <a href="https://www.sublimetext.com/">Sublime Text</a> for MacOS and Linux.

Now choose one of the two options below:

#### Optional Step — Farm Hash
Once the image copy is complete, you can go to your drive in Windows, Linux or Mac and find `rig-config-example.txt` file in the root folder. Here’s how it looks:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/rig_conf_eg.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/rig_conf_eg.png"
  />

_The contents of rig-config-example.txt file_

Enter your Farm Hash in the `FARM_HASH=` field by copying the value from your Settings tab. Here’s how the field should look like:

`FARM_HASH=f019745da6ba65630b28ef3c92608e7022b4bf76`

No need to set RIG_ID or RIG_PASSWD in this case. That’s it, just save your config file and rename it into `rig.conf`. Proceed by finishing the image installation and boot your worker. It will connect to the dashboard automatically.

#### Optional Step — Manual Setup
Once the image copy is complete, you can go to your drive in Windows, Linux or Mac and find rig-config-example.txt file in the root folder. Here’s how it looks:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/rig_conf_eg-2.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_worker_setup/rig_conf_eg-2.png"
  />

_The contents of rig-config-example.txt file_

Find and fill in the two fields:

`RIG_PASSWD=`

`RIG_ID=`

That’s it, just save your config file and rename it into rig.conf. Proceed by finishing the image installation and boot your worker. It will connect to the dashboard automatically.

### ASIC Installation
Before proceeding with installation, make sure that your ASIC miner is supported. The current list of supported models:

* Antminer S9
* Antminer S9i
* Antminer L3+
* Antminer L3++
* Antminer D3
* Antminer A3
* Antminer T9+
* Antminer Z9-Mini
* Antminer E3
* Antminer X3

* Innosilicon A9 ZMaster

#### Installation
Remotely connect to your worker using SSH. You can do it with <a href="https://www.teleconsole.com/">Teleconsole</a>. Teleconsole is an SSH tunnel to your rig. In few words you start it on the rig and open SSH in browser or in Linux/Mac console. Does not require any VPN or being in local network. To start it run `telec start` with Linux Shell Execute on web. Then copy-paste the given link to the browser. Or run `teleconsole join <given id>` on your Linux/Mac terminal. Run “telec” to see if it’s running, check other commands like stop, log open.

Security
Teleconsole IS NOT started automatically. You need to start it from web. Given session id is almost impossible to guess, it’s alsmost like to guess a private key for your bitcoin wallet. Treat it like a random login and password.

If you don’t connect for 60 minutes the link will expire and teleconsole daemon will be terminated on the rig.

After you are done with Teleconsole run the following command:

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade`

For Antminer D3 Blissz run the following command before installation:

`ln -s /usr/lib/libcurl-gnutls.so.4 /usr/lib/libcurl.so.5`

#### Promptless Installation
You can use FARM_HASH to add your ASIC workers automatically without entering rig ID and password. Copy your FARM_HASH from the Settings tab of your Farm and enter it into the command line as shown below:

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && FARM_HASH=your_hash_from_web sh selfupgrade`

Replace the `your_hash_from_web` with your `FARM_HASH`.

For more details regarding ASIC installation, please refer to this <a href="https://github.com/minershive/hiveos-asic">GitHub page</a>.

### Finishing Setup
As soon as your worker connects to the dashboard, you’re all done! Your worker should now be ready for you to make a few final adjustments in the dashboard, which we will describe in our next article.
