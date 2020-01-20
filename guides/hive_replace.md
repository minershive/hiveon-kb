title: OS Live Replacement

## OS Live Replacement
With 'hive-replace' script you can replace your running Linux with Hive on the fly. You can run this on any standard Ubuntu, or other competitor mining OS (like e**os, s*os, …). This can also be used to replace/upgrade system on a running Hive installation.

After successful writing you will reboot with a new system. This is how it looks like:
<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/1/1a226a504cd5b52dcd645fe0cc45e91249d25ac6_2_476x500.png" alt="hive-replace" width="476" height="500" class="d-lazyload" srcset="https://forum.hiveos.farm/uploads/default/optimized/2X/1/1a226a504cd5b52dcd645fe0cc45e91249d25ac6_2_476x500.png, https://forum.hiveos.farm/uploads/default/optimized/2X/1/1a226a504cd5b52dcd645fe0cc45e91249d25ac6_2_714x750.png 1.5x, https://forum.hiveos.farm/uploads/default/optimized/2X/1/1a226a504cd5b52dcd645fe0cc45e91249d25ac6_2_952x1000.png 2x">

### Before you start
Ideally you should download system image ZIP file and VERSIONS.txt. Then make them available on your local network via HTTP, FTP, NFS, SMB (Windows). Yes, it’s possible to provide image URL from official repository but the download speed will be slow and as it was said it’s better to store it in local network.

If you run this from Hive then current `rig.conf` will be preserved. In other Linuxes `FARM_HASH` will be asked.

The best way to run this command is to use direct SSH connection (from other Linux/Mac or with Putty from Windows). ShellInABox should work. OpenVPN connection is also OK. Teleconsole connection will be closed so you will not see the progress.

***WARNING: This command can potentially ruin your system installation. So please do some experiments when you are close the rig physically.***

### Usage Instructions
You need to update Hive from web to get the latest script version. If you are running other Linux then the script should be downloaded from [Git repository](https://github.com/minershive/hiveos-linux).

`cd /tmp`

`wget https://raw.githubusercontent.com/minershive/hiveos-linux/master/hive/sbin/hive-replace`

`chmod +x hive-replace`

Here are the general usage instructions:

<pre><code>
Usage: hive-replace [option] <Path or URL to ZIP file with Hive OS image>

Options:
  -y|--yes                    Do not ask for confirmation, answer yes to all questions
  -f|--force                  Forced replace. Do not check the checksum of ZIP archive. Use with caution!
  --nfs                       To use NFS Shared resource. e.g.: IP_NFS_server:/shared_dir/hive_zip
  --smb                       To use Windows Shared resource. e.g.: //IP_Windows_comp/shared_folder/hive_zip
  --smbuser=Windows user      UserName for Windows Shared resource. Do not set this option for guest/anonymous access
  --smbpass=Windows password  Password for Windows Shared resource. Do not set this option for guest/anonymous access
  --hash=FARM_HASH            FARM_HASH from Web-interface
  -h|--help                   Show this message
</code></pre>
### Examples
Get image via HTTP:

`hive-replace http://192.168.0.100/hiveos-0.6-01@181121.zip`

Use locally downloaded file (though this has little sense it’s possible):

`hive-replace /tmp/hiveos-0.6-01@181121.zip`

NFS network share:

`hive-replace -y -f --hash=46e9602837d0bda99f0 --nfs 192.168.0.100:/home/john/hive/hiveos-0.6-01@181121.zip`

Windows SMB share:

`hive-replace -y -f --hash=46e9602837d0bda99f0 --smb --smbuser=winuser --smbpass=secret //192.168.0.100/shared_folder/hiveos-0.6-01@181121.zip`
