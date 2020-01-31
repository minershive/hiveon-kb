---
title: Setting-up RX550
category: Guides
---

## Setting-up RX550

Here is a guide on how to make RX 550 to work in Hive OS. The main idea is to have 4.13 kernel and OpenCL from 16.60 driver. If you can, do `amdgpu-pro-uninstall`.

Download 4.13 kernel:
<pre><code>
wget http://download.hiveos.farm/kernels/linux-headers-4.13.12-mytest_1_amd64.deb
wget http://download.hiveos.farm/kernels/linux-firmware-image-4.13.12-mytest_1_amd64.deb
wget http://download.hiveos.farm/kernels/linux-image-4.13.12-mytest_1_amd64.deb
</code></pre>
And install it:
<pre><code>
dpkg -i linux-headers-4.13.12-mytest_1_amd64.deb
dpkg -i linux-firmware-image-4.13.12-mytest_1_amd64.deb
dpkg -i linux-image-4.13.12-mytest_1_amd64.deb
</code></pre>

Choose booting kernel to the latest:
`grub-set-default "1>0"; update-grub`

Reboot and check if you’ve booted the right kernel:
<pre><code>
uname -a
Linux rig2 4.13.12-mytest #1 SMP Thu Nov 9 15:31:09 EET 2017 x86_64
 x86_64 x86_64 GNU/Linux
</code></pre>
Go to folder with drivers in hive and install only OpenCL from 16.60 version:
<pre><code>
cd /hive-drivers-pack
tar xvf amdgpu-pro-16.60-379184.tar.xz
cd amdgpu-pro-16.60-379184
./amdgpu-pro-install --compute
</code></pre>
And, finally, reboot.

For sgminer get attached kernel.tar.gz and replace kernels in /hive/sgminer_gm folder on the rig. RX 550 has only 512 shader cores so there is no sense to set 'rawintensity' > 512 as it will crash.

Recommended settings are:

“rawintensity”: 420

“gpu-threads”: “2”

And in case you are lazy, you can try [this image](http://193.111.83.51/test/hive-0.5-20-rx550_sgminer.zip). It works for RX 550 only and is based on the latest HiveOs 0.5-20 with the core 4.13.
