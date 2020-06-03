---
title: Как добавить ASIC в Hive OS
parent_category: Гайды
path: /guides-add-asic-to-hiveos_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

### Подготовка
Будьте осторожны с последними прошивками Bitmain:
- Antminer, серия 9 (S9/S9i/S9j/T9/T9+): никогда не обновляйтесь на прошивку новее 10 июня 2019
- Antminer, серия 17: никогда не обновляйтесь на прошивку новее 1 декабря 2019

Все более новые версии официальных прошивок имеют защитные меры против удаленного вмешательства, поэтому вы не сможете установить Hive OS Client или прошивку Hiveon ASIC.

### Установка
Вы можете установить Hive OS Client через загрузку файла прошивки или через SSH.

#### Три базовые опции установки
**1. Веб-интерфейс ASICа**

**Antminer, серия 15, серия 17 и серия 9, модели S9k и S9SE**

Эти модели особенные. Они загружают операционную систему прямо в оперативную память в режиме "только для чтения". Установка клиента Hive OS возможна только путем обновления ASICа специальным файлом прошивки. Этот файл содержит стандартную прошивку Bitmain со встроенным клиентом Hive OS:

- [Antminer S9k](https://download.hiveos.farm/asic/S9k/stock%2Bclient/S9k-stock%2Bclient-20190929.tar.gz)
- [Antminer S9SE](https://download.hiveos.farm/asic/S9se/stock%2Bclient/S9se-stok%2Bclient.tar.gz)
- [Antminer S11](https://download.hiveos.farm/asic/S11/stock%2Bclient/S11-hive.tar.gz)
- [Antminer S15](https://download.hiveos.farm/asic/S15/stock%2Bclient/S15-%28stock%2Bclient%29-v19.08.12-ln.tar.gz)
- [Antminer T15](http://download.hiveos.farm/asic/T15/stock%2Bclient/T15-%28stock%2Bclient%29-v19.08.12-ln.tar.gz)
- [Antminer S17, S17 pro](http://download.hiveos.farm/asic/s17/stock%2Bclient/)
- [Antminer S17+](http://download.hiveos.farm/asic/S17%2B/stock%2Bclient/)
- [Antminer S17E](http://download.hiveos.farm/asic/S17E/stock%2Bclient/)
- [Antminer T17](http://download.hiveos.farm/asic/T17/stock%2Bclient/)
- [Antminer T17+](http://download.hiveos.farm/asic/T17%2B/stock%2Bclient/)
- [Antminer T17E](http://download.hiveos.farm/asic/T17E/stock%2Bclient/)

>После успешной прошивки необходимо открыть веб-интерфейс ASICа, нажать на вкладку Hive OS и ввести свой FARM_HASH, а затем нажать кнопку "Apply&Save". Страница обновится сама. Подождите минуту, и воркер появится в панели управления Hive.

**Все остальные Antminer, серии 3/7/9**

Hive OS Client для Antminer, серии 3/7/9, дата прошивки до 10.06.2019. Просто обновите прошивку ASICа при помощи [hive_install_unsig_antminers.tar.gz](http://download.hiveos.farm/asic/repo/unsig/hive_install_unsig_antminers.tar.gz).

**2. BTC Tools**

Все, что вы делаете с помощью веб-интерфейса ASICа, вы можете сделать лучше с помощью утилиты [BTC Tools](https://url.btc.com/btc-tools-download). Это лучший выбор, если у вас большое количество ASICов. Просканируйте вашу сеть, выберите ASICи для обновления и затем нажмите "Firmware Upgrade".

**3. SSH**

Войдите в ваш майнер через SSH и запустите следующую команду:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade`

Для Antminer D3 **Blissz**, запустите следующую команду перед установкой:

`ln -s /usr/lib/libcurl-gnutls.so.4 /usr/lib/libcurl.so.5`

Принудительно настройте FARM_HASH или RIG ID и пароль, измените API URL:

`firstrun` или `firstrun FARM_HASH` - когда нет конфигурации

`firstrun -f` или `firstrun FARM_HASH -f` - для замены конфигурации

Логины и пароли SSH по умолчанию:

Antminer - пользователь по умолчанию: **root**, пароль по умолчанию: **admin**

Innosilicon - пользователь по умолчанию (ssh/telnet): **root**, пароль по умолчанию: **blacksheepwall** или **innot1t2** или **t1t2t3a5**

>Если до вас были установлены иные значения логина и пароля, то сбросьте настройки ASICа на заводские. Для этого на включенном ASICe зажмите ipreport и reset, держите 20 секунд, выключите блок питания, не отпуская зажатые кнопки. Ждите 10 секунд, не отпуская кнопки ipreport и reset, включите блок питания и еще 20 секунд держите ipreport и reset. Потом отпустите и дождитесь загрузки.

### Варианты автоматизации
#### Быстрая установка
Вы можете добавить ASIC без ввода RIG_ID, пароля и URL API сервера.

**Чтобы добавить ASIC без ввода RIG\_ID и пароля, вам нужно заполнить переменную FARM_HASH.**

Получите ваш FARM\_HASH из панели управления Hive OS. В строке, которую вы видите ниже, замените `your_farm_hash` вашим FARM\_HASH. Затем запустите как одну команду:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade --farm-hash=YOUR_FARM_HASH`

**Чтобы использовать другой API сервер, вам нужно заполнить переменную HIVE\_HOST\_URL.**

В строке, которую вы видите ниже, замените `http://your_api_server` вашей URL API сервера. Затем запустите как одну команду:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade --hive-host-url=http://your_api_server`

**Вы также можете установить FARM\_HASH и API сервер одновременно.**

В строке, которую вы видите ниже, замените `your_farm_hash` вашим FARM\_HASH. Также замените `http://your_api_server` вашей URL API сервера. Затем запустите как одну команду:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade --farm-hash=YOUR_FARM_HASH --hive-host-url=http://your_api_server`

### Массовая установка
Вы можете установить Hive OS Client на все ASICи, которые есть в вашей локальной сети. Для этого вам нужно иметь работающий Linux-модуль (возможно, Hive OS на GPU риге) или Antminer ASIC с клиентом Hive OS. Вы можете сделать это всего тремя командами.

1. Если у вас ASIC с клиентом Hive OS, этот шаг можно пропустить. Установите sshpass и curl:

`apt-get install -y sshpass curl`

2. Скачайте скрипт:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/hive-asic-net-installer/download.sh && sh download.sh`

3. Выполните его:

`cd /tmp/hive-bulk-install`

Отредактируйте `config.txt`, чтобы настроить ваш FARM_HASH или URL прошивки. Отредактируйте `ips.txt`, чтобы настроить список IP адресов для ваших новых ASICов. Вы также можете просканировать локальную сеть для поиска Antminer. Пример: `ipscan.sh 192.168.0.1/24 > ips.txt`.

Чтобы установить Hive OS Client, просто запустите команду `install.sh`.

Чтобы установить прошивку на Antminer S9/i/j, запустите команду `firmware.sh`.

>Опционально, вы можете добавить имя воркера в `ips.txt` (например, `192.168.1.100 asic_01`).

>Если IP-адрес был подключен, он будет отмечен как #commented.

### Другие модели

#### Antminer S9 с подписью (используйте прошивку Hiveon ASIC)
[Установка Hiveon ASIC - Antminer S9, как решить проблему "Cannot find signature"](https://forum.hiveos.farm/t/hiveon-asic-installation-antminer-s9-cannot-find-signature-fix/12466)

[Прошивка Hiveon ASIC 1.02 для S9 - мануал по установке](https://forum.hiveos.farm/t/hiveon-asic-s9-firmware-v1-02/13944)

#### Antminer S9 (MSKMINER), S10 (MSKMINER)
Вам не нужно будет разблокировать SSH или делать что-то сложное. Для любого ASICа с кастомной прошивкой mskminer, вам нужно скачать [Установщик Hive OS Client для прошивки MSKMINER](http://download.hiveos.farm/asic/repo/s9/hive-msk-installer.tar.gz), и затем прошить им ASIC. Это все.

#### Antminer S17/S17 Pro/T17
[Прошивка Hiveon ASIC: мануал по установке для S17/T17](https://hiveos.farm/hiveon-asic-firmware-S17-S17-Pro-s17installation_ru)

#### Новые модели Innosilicon
[Hive OS Client: мануал по установке для Innosilicon](https://forum.hiveos.farm/t/innosilicon-t2t-t3-series/13610)

#### Старые модели Innosilicon
Некоторые заводские прошивки Innosilicon "страдают" утечкой памяти, и ASIC зависает каждые несколько дней. Чтобы решить эту проблему, вы можете активировать ежедневную перезагрузку майнера или ASICа (каждые 24 часа). Запустите следующие команды:

<pre><code>
inno-reboot miner enable/disable
inno-reboot asic enable/disable
inno-reboot status
</code></pre>

#### Todek Toddminer C1
`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade`

или, если вам нужно использовать FARM_HASH

`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade --farm-hash=YOUR_FARM_HASH`

#### Zig Z1+
[Hive OS Client: мануал по установке Zig Z1+](https://github.com/minershive/hiveos-asic/blob/master/hive/share/zig/README.md)

`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && bash selfupgrade`

или, если вам нужно использовать FARM_HASH

`sudo su -
cd /tmp && wget https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && selfupgrade --farm-hash=YOUR_FARM_HASH`

### Начните работать в Hive OS
#### Получите FARM_HASH
Чтобы привязать ASIC к вашей ферме Hive, вы можете использовать следующие опции (представлены в порядке сложности):

- вкладка Hive OS в веб-интерфейсе ASICа (самый простой вариант!)
- команда `firstrun` через SSH
- скачайте специальный файл .tar.gz через BTC Tools (массовая установка)

В любом случе, вам понадобится строка FARM_HASH. Вы найдете её в панели управления Hive OS, прямо во вкладке настроек фермы.

#### Создайте и примените Полетный Лист
Чтобы начать майнить, обязательно создайте Полетный Лист. Примените его, чтобы начать хеширование.

### Полезные команды
#### asic-find (Antminer)
Чтобы найти Antminer ASIC среди большого количества ASICов, вы можете запустить на нем мигание красного светодиода. Чтобы сделать это, выполните эту команду через веб-интерфейс или SSH:

`asic-find 5`

Красный светодиод будет мигать в течение 5 минут.

#### Как переименовать воркеры
Чтобы переименовать воркеры в веб-интерфейсе Hive по имени узла, запустите следующую команду из веб-интерфейса:

`hello hostname`

### Понижение и изменение версии
Если вы хотите установить конкретную версию или же понизить версию, добавьте версию, как аргумент в selfupgrade. Например, 0.1-02:

`cd /tmp && curl -kLsO https://raw.githubusercontent.com/minershive/hiveos-asic/master/hive/bin/selfupgrade && sh selfupgrade 0.1-02`

Чтобы просмотреть все варианты selfupgrade, запустите `selfupgrade --help`

Чтобы установить конкретную версию, укажите номер релиза: `selfupgrade 0.1-14`

Если вы хотите переустановить текущую версию, добавьте --force: `selfupgrade --force`

Чтобы установить стабильную версию разработки, запустите `selfupgrade master`

Чтобы установить версию night build development напрямую c Github, запустите `selfupgrade master --github`

### Удаление
`hive-uninstall`

Задания cron jobs могут быть удалены вручную при помощи `crontab -e`. Но даже если они останутся, они ничего не изменят.

### Восстановление: загрузочные образы
#### Antminer
Вы можете найти загрузочные образы для восстановления в [репозитории](https://download.hiveos.farm/asic/) (рекомендуемый вариант) или на [официальном сайте Bitmain](https://service.bitmain.com/support/download?product=Flashing%20SD%20card%20with%20image).

>Обратите внимание на два разных формата изображений.
- Файл `.img`  должен быть записан на SD карту при помощи специальной программы.
- Файл `.zip`, содержащий файлы `u-boot.img` и `uImage.bin`, должен быть разархивирован на SD карту, отформатированную в FAT32.

- [S9: образ восстановления](https://download.hiveos.farm/asic/s9/recovery-stock/Recovery_S9.img)
- [S17 Hiveon: образ восстановления (бета)](https://download.hiveos.farm/asic/s17/SD-S17-S17pro_Hiveon_1.01-200331_sig.zip)
- S17, S17 Pro, T17
	- Скачайте [образ восстановления](https://download.hiveos.farm/asic/s17/recovery-stock/SD_S17-T17_650M.05.06.2019.zip)
	- Используйте SD-карту <16 Гб
	- Отформатируйте SD-карту в FAT32
	- Распакуйте на SD-карту
	- Загрузите ASIC с SD картой
	- ASIC загрузился в режиме восстановления
	- Запишите любую подходящую [старую стоковую прошивку Bitmain](https://download.hiveos.farm/asic/) (формат .tar.gz) через веб интерфейс.

В случае возникновения проблем, пожалуйста, прочтите [данный мануал от Bitmain](https://support.bitmain.com/hc/en-us/articles/360033757513-S17-S17Pro-S9-SE-S9k-Z11-control-board-program-recovery-SD-card-flashing-with-customized-PW-).
