---
title: Замена Работающего Linux на Hive
parent_category: Гайды
path: /guides-hive_replace_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## Замена Работающего Linux на Hive
Используя скрипт `hive-replace`, вы можете сменить ваш работающий Linux на Hive буквально на лету. Вы можете запустить его на любой стандартной Ubuntu или другой конкурентной операционной системе для майнинга. Он также может быть использован для замены/обновления системы в работающей установке Hive.

После успешного написания вы перезагрузитесь с новой системой. Вот как это выглядит:

<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/1/1a226a504cd5b52dcd645fe0cc45e91249d25ac6_2_476x500.png">

### Прежде, чем вы начнете...
В идеале вам следует скачать ZIP-файл системного образа и файл VERSIONS.txt. Затем нужно сделать их доступными в локальной сети через HTTP, FTP, NFS, SMB (Windows). Да, можно предоставить URL-адрес изображения из официального репозитория, но скорость загрузки будет низкой, и, как было сказано, лучше хранить его в локальной сети.

Если вы запустите это из Hive, текущий файл `rig.conf` будет сохранен. В других Linux потребуется `FARM_HASH`.

Лучший способ выполнить эту команду - использовать прямое SSH-соединение (из другого Linux/Mac или через Putty из Windows). ShellInABox должен работать, как и соединение OpenVPN. Соединение Teleconsole будет закрыто, поэтому вы не увидите прогресс.

***ПРЕДУПРЕЖДЕНИЕ: Эта команда может потенциально испортить установку вашей системы. Пожалуйста, проведите несколько экспериментов, когда вы физически закроете риг.***

### Инструкция по применению
Вам нужно обновить Hive из веба, чтобы получить самую последнюю версию скрипта. Если у вас другой Linux, загрузите скрипт из [репозитория](https://github.com/minershive/hiveos-linux).

`cd /tmp`

`wget https://raw.githubusercontent.com/minershive/hiveos-linux/master/hive/sbin/hive-replace`

`chmod +x hive-replace`

Вот общая инструкция по применению:

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

### Примеры
Получите образ через HTTP:

`hive-replace http://192.168.0.100/hiveos-0.6-01@181121.zip`

Используйте локально загруженный файл (хотя в этом нет особого смысла, это возможно):

`hive-replace /tmp/hiveos-0.6-01@181121.zip`

NFS:

`hive-replace -y -f --hash=46e9602837d0bda99f0 --nfs 192.168.0.100:/home/john/hive/hiveos-0.6-01@181121.zip`

Windows SMB:

`hive-replace -y -f --hash=46e9602837d0bda99f0 --smb --smbuser=winuser --smbpass=secret //192.168.0.100/shared_folder/hiveos-0.6-01@181121.zip`
