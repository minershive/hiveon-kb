title: Selfupgrade

## Selfupgrade
Sometimes there can be situation when Ubuntu repo is out of sync and it can’t find some package. This happens because Hive is updating itself only but not the whole Ubuntu to minimize traffic. In a long run some package can be required and then it needs to be downloaded and Ubuntu’s repo cache old to know where it is.

It looks like this:
<pre><code>
Get:1 http://download.hiveos.farm/repo/binary  InRelease [1,741 B]
Get:2 http://download.hiveos.farm/repo/binary  Packages [14.8 kB]
Fetched 16.6 kB in 0s (90.7 kB/s)
Reading package lists...
------------------------------------------------------
Reading package lists...
Building dependency tree...

??????????????????

Get:175 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 xserver-xorg-video-ati-hwe-16.04 amd64 1:18.0.1-1~16.04.1 [7,126 B]
Get:176 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 xserver-xorg-video-intel-hwe-16.04 amd64 2:2.99.917+git20171229-1~16.04.1 [729 kB]
Get:177 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 amd64-microcode amd64 3.20180524.1~ubuntu0.16.04.2 [32.2 kB]
Err:178 http://us.archive.ubuntu.com/ubuntu xenial-updates/main amd64 intel-microcode amd64 3.20180425.1~ubuntu0.16.04.2
  404  Not Found [IP: 91.189.91.23 80]
Fetched 196 MB in 4min 9s (784 kB/s)
E: Failed to fetch http://security.ubuntu.com/ubuntu/pool/main/l/linux/linux-libc-dev_4.4.0-133.159_amd64.deb  404  Not Found [IP: 91.189.91.23 80]

E: Failed to fetch http://us.archive.ubuntu.com/ubuntu/pool/main/i/intel-microcode/intel-microcode_3.20180425.1~ubuntu0.16.04.2_amd64.deb  404  Not Found [IP: 91.189.91.23 80]

E: Unable to fetch some archives, maybe run apt-get update or try with --fix-missing?
Upgrade failed
</code></pre>
<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/d/d708a239fd934c9332e8274052a610939e6e8a66_2_690x401.png" alt="55" width="690" height="401" class="d-lazyload" srcset="https://forum.hiveos.farm/uploads/default/optimized/2X/d/d708a239fd934c9332e8274052a610939e6e8a66_2_690x401.png, https://forum.hiveos.farm/uploads/default/optimized/2X/d/d708a239fd934c9332e8274052a610939e6e8a66_2_1035x601.png 1.5x, https://forum.hiveos.farm/uploads/default/optimized/2X/d/d708a239fd934c9332e8274052a610939e6e8a66_2_1380x802.png 2x">

This can be resolved with running 'apt update' and then repeating 'selfupgrade'.
Though there can come up another problem with interactive dialog from grub:
<img src="https://forum.hiveos.farm/uploads/default/original/2X/0/0e0fc90430c2664fcbac3c18e20da11447a524d3.png" alt="image" width="631" height="442" class="d-lazyload">

If you are upgrading in shell (SSH or Teleconsole) then it’s fine, but with running it from web it can be a problem.

### Solution
`nohup bash -c 'apt update; export DEBIAN_FRONTEND=noninteractive; apt-get -y --only-upgrade install hive; hello restartminer; screen -S agent -X quit; agent-screen' > /tmp/nohup.log 2>&1 &`

A pretty long line, but paste it in Linux Execute and run.
