---
title: NVidia drivers update guide and CUDA 10.x
category: Guides
---

nvidia-driver-update default installation version: 440.36 (updated December 05, 2019)

This week we update NVidia drivers in our [repository](http://download.hiveos.farm/drivers/). All drivers are CUDA 10 compatible.
Added drivers version:

- 410.93 - R410 stable long term support (supported new RTX 2080 Ti, 2080, 2070)
- 415.27 - R415 current stable (as above + added support RTX 2060)
- 418.43 - R418 beta series (as above + added support GTX 1660, GTX 1660 Ti, RTX 2070 with Max-Q Design, RTX 2080 with Max-Q Design)

To update the drivers use the nvidia-driver-update tool.

After conducting our tests we choose version 418.43 for installation by default if no arguments given to nvidia-driver-update.
This version supports all the latest NVidia RTX cards and also gives 2x time lower system load on algos such as x16 family, cuckoo and others.

#### Update or not update?
Before we start let’s answer some typical questions:

#### Is it necessary to update?
No! If everything works for you - don’t touch.

#### Why then update?
New drivers include support for new cards such as 1660ti, 2060, 2070, 2080, 2080ti series
Sometimes special optimization in some miners have a positive effect on hashrate but only for some algorithms and Pascal family of top-end cards - 10xx.

#### Still not changing your mind?
Then we will start.

### Updating procedure
We strongly recommend using Hive Shell for proper driver update procedure. Of course, if you can use local console - use it or if your rigs located in the same LAN with your PC/laptop then you can use for example SSH-clients such as standlone app PuTTY or working in browser ShellInABox instead Hive Shell.

The update procedure is quite simple.
Step 1 - Start Hive Shell
Step 2 - Execute the following commands:

`apt update`

`nvidia-driver-update`

The driver update procedure takes 5-10 min if you’re using an SSD/HDD and 30+ min if you’re using a slow drive such as an USB 2.0 stick.
If the update procedure will finish successfully you will see the following message:

<img src="https://lbd.hiveos.farm/kbase/images/forum/9553243cace241898daa33377c83112c9118e588.png">

Now you can reboot your rig. After reboot check driver version and miner functionality.

### Update/downgrade to desired version
You can update driver to desired version. In this case command line for nvidia-driver-update tool must contain URL to desired driver version.
For example downgrade to 396.54:
`nvidia-driver-update http://download.hiveos.farm/drivers/NVIDIA-Linux-x86_64-396.54.run`

### Troubleshooting
#### Driver installation failed (module “nvidia-drm”)
In some cases the update procedure can sometimes fail with the following error:

<img src="https://lbd.hiveos.farm/kbase/images/forum/b1821d4e57e3c64d131dec53c211fbfdea7e415a.png">
In case this happens, please retry the update procedure - in most cases it will help fix the error.

#### Driver installation failed (module “nvidia-uvm”)
If installation stops with the following error:

<img src="https://lbd.hiveos.farm/kbase/images/forum/b1821d4e57e3c64d131dec53c211fbfdea7e415a.png">
in this case, reboot rig and repeat the update procedure.

#### Error during uninstallation previous driver (module “nvidia”)
During the installation new driver nvidia-driver-update uninstalls the previous version of the driver. If uninstallation stops with the following error:

<img src="https://lbd.hiveos.farm/kbase/images/forum/dd971d757777318adb5a70eb39a1ba9fa136b5d4.png">

It can be caused by falling current driver or application which is still using driver. Reboot the rig and retry the installation procedure.

#### Error during uninstallation previous driver (signal SIGBUS)
During installation new driver nvidia-driver-update uninstalls the previous version of the driver. If uninstallation stops with the following error (Received signal SIGBUS; aborting):

<img src="https://lbd.hiveos.farm/kbase/images/forum/dd971d757777318adb5a70eb39a1ba9fa136b5d4.png">
No solution yet… Not reproducible.

#### Not enough disk space
- use disk-expand tool to enlarge disk to use all space
- remove unused drivers at /hive-driver-pack (to do this, send the `rm /hive-drivers-pack/NV*` command to your worker - it will delete all the available Nvidia driver archives)
- uninstall miners by hpkg tool

#### Installation fail when unpacking driver
By default TMP directory is on RAM disk so you need to enable logs to have some space:
logs-on
reboot

#### After the update miner don’t start properly
If your miner doesn't start to work of works incorrectly after the update, you can repeat driver update procedure or downgrade driver version as described above (see install desired driver version).

#### Nothing helps?
Try:
- write to the support bee@hiveos.farm
- call community support on Telegram channel
- reflash the image
- remote update image via hive-replace tool
