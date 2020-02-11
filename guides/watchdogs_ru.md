---
title: Вачдоги
parent_category: Гайды
path: /guides-watchdogs_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## Вачдоги

### SimpleRigResetter SRRv2 Вачдог
https://shop.simplemining.net/ssrv2.html?___SID=U

https://bitcointalk.org/index.php?topic=1695298.0

Изначально к нему подключается виндовый клиент, настраивается таймаут срабатывания.
На ригах надо создать файл:
`/hive-config/watchdog_srrv2.txt`

Его содержимое:
<pre><code>
ENABLE=1
SERIAL_NUMBER=000306
SLOT_NUMBER=4
</code></pre>
Где SERIAL_NUMBER - серийник устройства, SLOT_NUMBER - слот, к которому подключен риг.

После ребута рига нужно выключить виндовый клиент (в интерфейсе есть отключение), иначе он вместе с ригом будет отправлять "пинги".

### Китайские вачдоги
На рынке есть много китайских вачдогов. Вы можете найти их на Aliexpress или Ebay. Они могут быть разных форм, но в их основе лежит один и тот же чип.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/9bfddcddf808f2d89c34ce558beaec77255c723c.jpeg">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/b/b9e6090c9f33833ca3e4e3a3561590f9832a8071.jpeg">

Чтобы проверить сброс, вы можете запустить следующую команду после подключения к системе: `hive/opt/qinheng/hl340 reset`

Запустите эту команду, чтобы проверить ID устройства: `lsusb`

Список поддерживаемых чипов:

- 1a86:7523
- 5131:2007
- 0471:2379

Существует также другой тип вачдога, с таким же ID, но на Arduino Nano. Он не может быть обнаружен. Чтобы использовать его, запустите команду `/hive/opt/qinheng/wd-nano on`.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/6/60d77df72b177f246c71d5d7bdf8ef65ae170192.jpeg">

### OpenDev Вачдог
Поддерживаемый вачдог - https://open-dev.ru/watchdog.
Вы можете просто подключить его, и все. Конфигурация не требуется.

Вы можете проверить, обнаружен ли он, с помощью следующей команды:

`$ journalctl -u hive -b0`

`Oct 28 23:37:55 worker hive[861]: > Detecting watchdogs`

`Oct 28 23:37:55 worker hive[861]: Watchdogs InUa found: 0`

`Oct 28 23:37:55 worker hive[861]: Watchdogs OpenDev found: 1`

**Как протестировать работу вачдога:**

Отсоедините от вачдога провода (или не отсоединяйте, если сомневаетесь) и выполните следующую команду: `/hive/opt/opendev/watchdog-opendev reset`.

Это отправит команду сброса вачдога: `/hive/opt/opendev/watchdog-opendev power`.

Pro версия также поддерживает эту команду. Вы должны увидеть, как мигает светодиод. Если мигает — всё в порядке!
