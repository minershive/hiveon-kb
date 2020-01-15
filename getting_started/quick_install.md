# Hive OS Quick Installation Guide

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/header.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/header.png"
  />

Before installing Hive OS on your rig, we recommend <a href="https://the.hiveos.farm/">creating an account</a> first, or logging into your <a href="https://the.hiveos.farm/">existing one</a>.

# Add Worker
After creating an account, you will be greeted by your farm’s overview tab. Click the **add one** button to add a new rig.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/add_worker.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/add_worker.gif"
  />

_Adding a new worker_

Enter a name for your rig and a password. Optionally you can add a description of your rig. And then click **Add**.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/worker_info.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/worker_info.gif"
  />

_Filling out the worker details_

You’ll see a screen with tons of alternative installation options with which you can get acquainted [here](getting_started/start_worker_setup.md). Click the `rig.conf` to download this file.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/dl_rig_conf.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/dl_rig_conf.png"
  />

_Downloading the rig.conf file_

# Download Image
Go to the <a href="https://hiveos.farm/install/">download</a> page to get the latest version of Hive OS. Choose between a .zip or a .torrent file.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/install.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/install.png"
  />

_Choosing a download option_

# Flash Image
Insert a USB drive with 8Gb or more into your PC or Mac. Windows, MacOS and Linux users can use <a href="https://sourceforge.net/projects/win32diskimager/">Win32 Disk Imager</a>, <a href="https://etcher.io/">Etcher</a>, <a href="https://rufus.akeo.ie/">Rufus</a> or any other software of their choice. This example shows using Etcher to flash the image:

**1. Select Image**

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_select.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_select.png"
  />

**2. Select Drive**

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_drive.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_drive.png"
  />

**3. Flash!**

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_flash.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/etcher_flash.png"
  />

Wait for the image to flash unto your USB drive.

As soon as the image is done flashing, you should see a new drive called “Hive”. Click to open it’s contents.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive.png"
  />

Add the `rig.conf` file you downloaded previously to the Hive image drive.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive_conf.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/hive_drive_conf.png"
  />

Remove the USB drive from your computer and then insert into the rig.

# Install Image
Insert the USB into your rig. Boot your rig and wait for it to install the image. Once done, you’ll see this screen.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/os_install.jpeg?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/os_install.jpeg"
  />

_An example of what you should bee seeing once the OS was successfully installed_

Done! It will connect to Hive and you can start working with your rig.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/new_rig.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/quick_install/new_rig.png"
  />

_Your new rig will appear in your farm_

Check this article to find out how to [configure your rig](start_dashboard_setup.md).
