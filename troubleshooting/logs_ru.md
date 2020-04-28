---
title: Журналы
parent_category: Исправление проблем
path: /troubleshooting-logs_ru
lang: ru
parent_category_path: /troubleshooting_ru
order: 1
---

### Журналы майнера
Простой способ: нажмите на кнопку **Log** под панелью выбора майнера.

<img src="http://forum.hiveos.farm/uploads/editor/yr/nilcobp2yg17.png" >

В ответ вы получите нечто подобное. Нажмите на иконку чата рядом с **miner log**:

<img src="http://forum.hiveos.farm/uploads/editor/t1/j1eymexf8r2o.jpg">

На самом деле, это не настоящий журнал - это всего лишь экран майнера. Настоящие файлы хранятся в /var/log/miner/xxxx/*.log.

Итак, откройте **mc** на риге и перейдите в **/var/log/miner/claymore**. Найдите там **lastrun_noappend.log**.
<img src="http://forum.hiveos.farm/uploads/editor/r4/0z64iupn4v06.jpg">

На последние 100 строк можно взглянуть при помощи следующей команды:

`tail -n 100 /var/log/miner/claymore/lastrun_noappend.log.`

Журналы вращаются с каждой перезагрузкой майнера, так что есть lastrun_noappend.1.log, lastrun_noappend.2.log,...

### Журналы системы
Главный системный журнал, содержащий все сообщения: `less /var/log/syslog`.

Стартовые журналы Hive со всех загрузок: `journalctl -u hive`.

Стартовый журнал Hive X сервер (графический интерфейс). “-b0” - это опция, показывающая только текущую загрузку. Может быть полезна при проверке проблем сервера X. Также есть журнал VNC-сервера, и вы можете проверить доступ к VNC и логины: `journalctl -u hivex -b0`.

Для отображения загрузочных сообщений и текущих ошибок ядра или драйвера: `dmesg`.

Журналы аутентификации. Эта команда покажет вам, кто залогинился через SSH: `cat /var/log/auth.log | grep "Accepted"`.

И, разумеется, есть агентский журнал Hive, где находится вся коммуникация с сервером: `less /var/log/hive-agent.log`.
