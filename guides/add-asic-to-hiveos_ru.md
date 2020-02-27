---
title: Как Добавить ASIC в Hive OS
parent_category: Гайды
path: /guides-add-asic-to-hiveos_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## Как добавить ASIC в Hive OS
### Установка
Вы можете установить Hive OS Клиент на ваш ASIC при помощи файла прошивки или через SSH.

**НЕ ОБНОВЛЯЙТЕ ваш Antminer до версии прошивки новее, чем 10.06.2019. Bitmain не допускает изменений в этой прошивке.**.

### Веб-интерфейс или btc-инструменты
Клиент для Antminer (серии 3/7/9) series, прошивка до 10.06.2019:
<a href="http://download.hiveos.farm/asic/repo/unsig/hive_install_unsig_antminers.tar.gz">hive_install_unsig_antminers.tar.gz</a>

Стоковая прошивка Bitmain + интегрированный Hive OS клиент + вкладка Hive OS в веб-интерфейсе для **farm_hash**:
- <a href="http://download.hiveos.farm/asic/repo/unsig/S11-hive.tar.gz">Antminer S11</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/S15-hive.tar.gz">Antminer S15</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/T15-hive.tar.gz">Antminer T15</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/S17-hive.tar.gz">Antminer S17</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/S17pro-hive.tar.gz">Antminer S17pro</a>
- <a href="http://download.hiveos.farm/asic/repo/unsig/T17-hive.tar.gz">Antminer T17</a>

### SSH
Логины и пароли SSH по умолчанию:

Antminer - пользователь по умолчанию: **root**, пароль по умолчанию: **admin**

Innosilicon - пользователь по умолчанию (ssh/telnet): **root**, пароль по умолчанию: **blacksheepwall** или **innot1t2** или **t1t2t3a5**

Войдите в ваш майнер через SSH и запустите следующую команду:

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade`

Для Antminer D3 **Blissz**, запустите следующую команду перед установкой:

`ln -s /usr/lib/libcurl-gnutls.so.4 /usr/lib/libcurl.so.5`

Принудительно настройте FARM_HASH или RIG ID и password, измените API URL:
`firstrun` или `firstrun FARM_HASH` - когда нет конфигурации

`firstrun -f` или `firstrun FARM_HASH -f` - для замены конфигурации

#### Быстрая установка
Вы можете использовать FARM_HASH, чтобы добавить ASIC автоматически, без введения ID рига и его пароля. Поместите ваш хеш в командную строку. (FARM_HASH=$FARM_HASH)

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && FARM_HASH=your_hash_from_web sh selfupgrade`

Измените сервер API. (HIVE_HOST_URL=$HIVE_HOST_URL)

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && FARM_HASH=your_hash_from_web HIVE_HOST_URL=http://api.exaple.com sh selfupgrade`

### Массовая установка
Вы можете установить Hive на все ASICи вашей локальной сети, или же установить прошивку на Antminer S9/i/j. Для этого вам нужен работающий Linux компьютер (возможно, Hive OS на GPU риге) или Antminer ASIC с Hive клиентом. Скачайте файлы при помощи этой команды:

<pre><code>
apt-get install -y sshpass curl
cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/hive-asic-net-installer/download.sh && sh download.sh
cd /tmp/hive-bulk-install
</code></pre>

Отредактируйте `config.txt`, чтобы настроить ваш FARM_HASH или URL прошивки. Отредактируйте `ips.txt`, чтобы настроить список IP адресов для ваших новых ASICов. Вы также можете просканировать локальную сеть для поиска Antminer. Пример: `ipscan.sh 192.168.0.1/24 > ips.txt`

Опционально, вы можете добавить имя воркера в `ips.txt` (например, `192.168.1.100 asic_01`).

Чтобы установить Hive, просто запустите команду `install.sh`.

Чтобы установить прошивку на Antminer S9/i/j, запустите команду `firmware.sh`.

Если IP-адрес был подключен, это будет отмечено в файле.

### Понижение и изменение версии
Если вы хотите установить конкретную версию или же понизить версию, добавьте версию, как аргумент в selfupgrade. Например, 0.1-02:

`cd /tmp && curl -L --insecure -s -O https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade 0.1-02`

Локально на ASIC, вы можете запустить команду `selfupgrade command`. Чтобы установить конкретную версию, запустите `selfupgrade 0.1-02`. Если вы хотите переустановить версию, добавьте в команду `-f`. Вот так: `selfupgrade 0.1-02 -f`. Чтобы установить текущую версию разработки из репозитория, пожалуйста, запустите `selfupgrade master`.

**Для отображения данных в мониторинге, обязательно создайте Полетный Лист.**

### Удаление
`hive-uninstall`

Задания cron jobs могут быть удалены вручную при помощи `crontab -e`. Но даже если они останутся, они ничего не изменят.

### asic-find (Antminer)
Чтобы найти Antminer ASIC среди большого количества ASICов, вы можете запустить на нем мигание красного светодиода. Чтобы сделать этой, выполните эту команду через веб-интерфейс или SSH:

`asic-find 5`

Пример: `asic-find 15`, красный светодиод будет мигать в течение 15 минут.

### Как переименовать ASICи
Чтобы переименовать воркеры в веб-интерфейсе Hive по имени узла, запустите следующую команду из веб-интерфейса:

`hello hostname`

### Antminer S9: улучшенная прошивка
<a href="https://forum.hiveos.farm/t/hiveon-asic-s9-firmware-v1-02/13944">Мануал</a>

<a href="https://forum.hiveos.farm/t/hiveon-asic-installation-antminer-s9-cannot-find-signature-fix/12466">Как решить проблему "Cannot find signature"</a>

### Antminer S17/S17 Pro/T17

<a href="https://forum.hiveos.farm/t/antminer-s17-t17/12415">Мануал</a>

### Новые модели Innosilicon
<a href="https://forum.hiveos.farm/t/innosilicon-t2t-t3-series/13610">Мануал</a>

### Старые модели Innosilicon
Некоторые заводские прошивки Innosilicon "страдают" утечкой памяти, и ASIC зависает каждые несколько дней. Чтобы решить эту проблему, вы можете активировать ежедневную перезагрузку майнера или ASICа (каждые 24 часа). Запустите следующие команды:

<pre><code>
inno-reboot miner enable/disable
inno-reboot asic enable/disable
inno-reboot status
</code></pre>

>Если до вас были установлены иные значения логина и пароля, то сбросьте настройки ASICа на заводские. Для этого на включенном ASICe зажмите ipreport и reset, держите 20 секунд, выключите блок питания, не отпуская зажатые кнопки. Ждите 10 секунд, не отпуская кнопки ipreport и reset, включите блок питания и еще 20 секунд держите ipreport и reset. Потом отпустите и дождитесь загрузки.

### Zig Z1+
<a href="https://github.com/minershive/hiveos-asic/blob/master/hive/share/zig/README.md">Zig Z1+ SSH мануал</a> (на английском)

`cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade`

или

`cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && FARM_HASH=your_hash_from_web bash selfupgrade`

### Восстановление Antminer
Вы можете найти образы восстановления [здесь](https://service.bitmain.com/support/download?product=Flashing%20SD%20card%20with%20image).

>Обратите внимание на два разных формата изображений. Файл `.img`  должен быть записан на SD карту при помощи специальной программы. Файл `.zip`, содержащий файлы `u-boot.img` и `uImage.bin`, должен быть разархивирован на SD карту, отформатированную в FAT32.

- [Образ восстановления S9](https://download.hiveos.farm/asic/repo/fw/Antminer/recovery/Recovery_S9.img)
- S17, S17 Pro, T17
	- Скачайте [образ восстановления](https://download.hiveos.farm/asic/repo/fw/Antminer/recovery/SD_S17-T17_650M.05.06.2019.zip)
	- Используйте SD-карту <16 Гб
	- Отформатируйте SD-карту в FAT32
	- Распакуйте на SD-карту
	- Загрузите ASIC с SD картой
	- ASIC загрузился в режиме восстановления
	- Запишите любую подходящую [старую стоковую прошивку Bitmain](https://download.hiveos.farm/asic/) (формат .tar.gz) через веб интерфейс.

В случае возникновения проблем, пожалуйста, прочтите [данный мануал от Bitmain](https://support.bitmain.com/hc/en-us/articles/360033757513-S17-S17Pro-S9-SE-S9k-Z11-control-board-program-recovery-SD-card-flashing-with-customized-PW-).
