---
title: Полезные команды для ASICов на прошивке Hiveon
parent_category: Прошивка Hiveon ASIC
category: Общие Вопросы
path: /hiveon-asic-firmware-general-commands_ru
lang: ru
parent_category_path: /hiveon-asic-firmware_ru
category_path: /hiveon-asic-firmware-general_ru
order: 1
meta_description: Управляйте своими устройствами легко и просто.
---

`selfupgrade master` - обновление Hive OS Client для ASICов (агента сбора статистики ASICа, не путать с обновлением прошивки).

`miner log all` - покажет всё доступные логи совмещённо и с сортировкой по дате и времени.

`miner log watchdog` - покажет лог вочдога.

`asic-oc retune` - перетюнит ASIC на текущем профиле разгона.

`asic-oc status` - покажет все сохраненные (оттюненые) профили разгона.

`asic-oc clear-cache` - сотрет все профили разгона (нужно запускать тюн заново).

`ntpdate pool.ntp.org` - синхронизация даты и времени на ASICе.

`have-passwd NEW_PASSWORD --web` - смена пароля в веб-интерфейсе (**NEW_PASSWORD** замените на ваш пароль).

`asic-find 5` - мигание светодиодами 5 минут для поиска ASICа.

P.S.: Почти все утилиты можно запустить с ключом `--help` и посмотреть их возможности:

`selfupgrade --help`

`miner --help`

`hive-passwd --help`

`asic-oc --help`
