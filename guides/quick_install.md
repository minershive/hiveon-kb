# Hive OS Quick Installation Guide

![header](/images/quick_install/header.png)

Before installing Hive OS on your rig, we recommend [creating an account](creating an account) first, or logging into your [existing one](https://the.hiveos.farm/).

# Add Worker
After creating an account, you will be greeted by your farm’s overview tab. Click the **add one** button to add a new rig.

![add new worker](/images/quick_install/add_worker.gif)

_Adding a new worker_

Enter a name for your rig and a password. Optionally you can add a description of your rig. And then click **Add**.

![worker details](/images/quick_install/worker_info.gif)

_Filling out the worker details_

You’ll see a screen with tons of alternative installation options with which you can get acquainted [here](start_worker_setup.md). Click the `rig.conf` to download this file.

![download rig config](/images/quick_install/dl_rig_conf.png)

_Downloading the rig.conf file_

# Download Image
Go to the [download](https://hiveos.farm/install/) page to get the latest version of Hive OS. Choose between a .zip or a .torrent file.

![install page](/images/quick_install/install.png)

_Choosing a download option_

# Flash Image
Insert a USB drive with 8Gb or more into your PC or Mac. Windows, MacOS and Linux users can use [Win32 Disk Imager](https://sourceforge.net/projects/win32diskimager/), [Etcher](https://etcher.io/), [Rufus](https://rufus.akeo.ie/) or any other software of their choice. This example shows using Etcher to flash the image:

**1. Select Image**

![select image in etcher](/images/quick_install/etcher_select.png)

**2. Select Drive**

![select drive in etcher](/images/quick_install/etcher_drive.png)

**3. Flash!**

![flash image in etcher](/images/quick_install/etcher_flash.png)

Wait for the image to flash unto your USB drive.

As soon as the image is done flashing, you should see a new drive called “Hive”. Click to open it’s contents.

![hive drive in windows](/images/quick_install/hive_drive.png)

Add the `rig.conf` file you downloaded previously to the Hive image drive.

![add rig.conf to drive](/images/quick_install/hive_drive_conf.png)

Remove the USB drive from your computer and then insert into the rig.

# Install Image
Insert the USB into your rig. Boot your rig and wait for it to install the image. Once done, you’ll see this screen.

![os image installation](/images/quick_install/os_install.jpeg)

_An example of what you should bee seeing once the OS was successfully installed_

Done! It will connect to Hive and you can start working with your rig.

![new rig added to web](/images/quick_install/new_rig.png)

_Your new rig will appear in your farm_

Check this article to find out how to [configure your rig](start_dashboard_setup.md).
