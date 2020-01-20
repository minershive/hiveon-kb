title: Drivers Update

## Drivers Update
Sometimes users want to try other drivers. Really advanced would not ask such questions,
but if you want to play here is a guide.

Starting from 0.5-70 there is an utility to Nvidia install driver which you can use from web or on shell. It will install the latest stable driver for Hive:
`nvidia-driver-update`

Or you can give URL of driver to install: `nvidia-driver-update http://download.hiveos.farm/drivers/NVIDIA-Linux-x86_64-390.59.run`

On some systems overclocking may fail after upgrade, try to run this to fix: `apt-get install --reinstall -y nvidia-settings`

### General notes
You need to have SSH or Teleconsole or physical access to the rig.

By default TMP directory is on RAM disk so you need to enable logs to have some space:

`logs-on`

`reboot`

Go to /hive-drivers-pack
If you need some historical drivers please find them here:
http://download.hiveos.farm/drivers/
Or download a new one you want.

Stop X server with `systemctl stop hivex` or `killall xinit`.
Stop miner with `miner stop`.

### For AMD
`tar -Jxvf amdgpu-pro-XXXX.tar.xz`

`cd amdgpu-pro-XXXX`

`./amdgpu-pro-install -y`

`dpkg -l amdgpu-pro`

To install new AMD driver you need to uninstall the previous one, please run 'amdgpu-pro-uninstall'.
Please unpack the currently installed driver tar.gz to /var/opt/amdgpu-pro-local, then `amdgpu-pro-uninstall` will work.
It was removed to save space.

### For NVIDIA
Just run `NVIDIA-Linux-x86_64-3xx.yy.run`.
In rare cases it fails to compile DKMS module or something, then reboot and try again. Usually it works from the second try.
