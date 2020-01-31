---
title: Вачдоги
category: Гайды
---

## Вачдоги
Изначально подклчается к нему виндовый клиент, настраивается таймаут срабатывания.
На ригах надо создать файл
`/hive-config/watchdog_srrv2.txt`

С содержимым:
<pre><code>
ENABLE=1
SERIAL_NUMBER=000306
SLOT_NUMBER=4
</code></pre>
Где SERIAL_NUMBER - серийник устройства, SLOT_NUMBER - слот, к которому подключен риг.

После ребута рига нужно выключить виндовый клиент (в интерфейсе есть отключение), иначе он вместе с ригом будет отправлять “пинги”.

### Внешние Ресурсы
- <a href="http://finance-quality.ru/podklyuchenie-i-nastrojka-opendev-watchdog-v-hive-os/">Подключение и настройка OpenDev Watchdog в HIVE OS.</a>
