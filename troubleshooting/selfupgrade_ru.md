---
title: Самостоятельное обновление
parent_category: Исправление проблем
path: /troubleshooting-selfupgrade_ru
lang: ru
parent_category_path: /troubleshooting_ru
order: 1
meta_description: Вам нужно выполнить обновление самостоятельно? С этой инструкцией у вас не возникнет никаких проблем.
---

Иногда может возникнуть ситуация, когда репозиторий Ubuntu не синхронизирован и не может найти какой-либо пакет. Это происходит потому, что Hive обновляет только себя, но не всю Ubuntu, чтобы минимизировать трафик. В долгосрочной перспективе может потребоваться какой-то пакет, и затем его необходимо загрузить, а старая кэш-память Ubuntu не знает, где он находится.

Это выглядит вот так:
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
<img src="https://lbd.hiveos.farm/kbase/images/forum/d708a239fd934c9332e8274052a610939e6e8a66_2_690x401.png" alt="55" width="690" height="401" class="d-lazyload">

Это может быть решено запуском команды `apt update`, а потом повторением `selfupgrade`.
Хотя может возникнуть другая проблема с интерактивным диалогом из grub:
<img src="https://lbd.hiveos.farm/kbase/images/forum/0e0fc90430c2664fcbac3c18e20da11447a524d3.png" alt="image" width="631" height="442" class="d-lazyload">

Если вы выполняете обновление в SSH или Teleconsole, то это нормально, но при запуске из Интернета это может стать проблемой.

### Решение
`nohup bash -c 'apt update; export DEBIAN_FRONTEND=noninteractive; apt-get -y --only-upgrade install hive; hello restartminer; screen -S agent -X quit; agent-screen' > /tmp/nohup.log 2>&1 &`

Весьма длинная строка, но скопируйте её, вставьте в Linux Execute и запустите.
