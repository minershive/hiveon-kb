---
title: Полезные команды для ASICов на прошивке Hiveon
parent_category: Прошивка Hiveon ASIC
category: Общие Вопросы
path: /hiveon-asic-firmware-general-commands_ru
lang: ru
parent_category_path: /hiveon-asic-firmware_ru
category_path: /hiveon-asic-firmware-general_ru
order: 1
---

`self upgrade master` - обновление агента асика (внутренний софт, не прошивка).

`miner log all` - покажет всё доступные логи совмещённо и с сортировкой по дате и времени.

`miner log watchdog` - покажет лог вочдога.

`asic-oc retune` - перетюнивает ASIC на текущем профиле разгона.

`asic-oc status` - показывает завершенные (оттюненые) профили разгона.

`asic-oc clear-cache` - стирает все профили разгона (нужно запускать тюн заново).

`ntpdate pool.ntp.org` - синхронизация времени на ASICе с сервером.

`have-passwd new_passwd -w` - смена пароля в веб-интерфейсе (**new_pass** замените на ваш пароль).

`asic-find 5` - мигание диодами 5 минут для поиска ASICа.

P.S.: Почти все утилиты можно запустить с ключом `--help` и посмотреть их возможности:

`self upgrade --help`

`miner --help`

`hive-passwd --help`

`asic-oc --help`
