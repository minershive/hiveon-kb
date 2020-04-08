---
title: Инструкция по Установке Прошивки Через SD-карту (серии S17 и Т17)
parent_category: Прошивка Hiveon ASIC
category: Общие Вопросы
path: /hiveon-asic-firmware-general-installation_sd_card_ru
lang: ru
parent_category_path: /hiveon-asic-firmware_ru
category_path: /hiveon-asic-firmware-general_ru
order: 1
---

## Инструкция по Установке Прошивки Через SD-карту (серии S17 и Т17)

### Порядок действий:

**Шаг 1:** Скачайте архив восстановления в соответствии с моделью:

S17/S17Pro: http://download.hiveos.farm/asic/s17/SD-S17-S17pro-Hiveon-latest.zip

S17+:  http://download.hiveos.farm/asic/S17%2B/SD-S17%2B-Hiveon-latest.zip

S17E: http://download.hiveos.farm/asic/S17E/SD-S17E-Hiveon-latest.zip

T17: http://download.hiveos.farm/asic/T17/SD-T17-Hiveon-latest.zip

T17+: http://download.hiveos.farm/asic/T17%2B/SD-T17%2B-Hiveon-latest.zip

T17E: http://download.hiveos.farm/asic/T17E/SD-T17E-Hiveon-latest.zip

**Шаг 2:** Вставьте карту MicroSD в компьютер и отформатируйте в FAT32.
- Обязательна эмуляция стандартного usb или usb-hdd, никаких uzb-zip или usb-fdd
- Только FAT32
- Никаких загрузчиков, mbr, или дополнительных разделов

**Шаг 3:** Разархивируйте загруженный файл и скопируйте содержимое на карту MicroSD. В корневой папке есть файлы. Заполните их, и ASIC после прошивки привяжется к Hive OS:
- FARM_HASH - в этот файл вставить FARM_HASH из настроек фермы
- HIVE_HOST_URL - вставить API сервер, если необходимо его заменить. Если файл пустой, то используется стандартный api.hiveos.farm

**Шаг 4:** Извлеките карту MicroSD из компьютера и вставьте ее в слот для карты на плате управления.

**Шаг 5:** Включите плату управления. Подождите около 30 секунд, пока файлы загрузятся автоматически. После загрузки красный и зеленый индикаторы на плате управления будут мигать (для разных моделей может потребоваться разное время для завершения этого процесса).

**Шаг 6:** Выключите майнер и вытащите карту MicroSD. Включите ASIC, он уже прошит на прошивку Hiveon.

**Шаг 7:** Если в 3 шаге вы не заполнили файл с FARM_HASH, то привязать ASIC к Hive OS можно через веб-интерфейс ASIC-а на вкладке **FarmConfig**. Также можно привязать массово, через функцию прошивки в BTC Tools (файлом, сгенерированным по этой ссылке: http://download.hiveos.farm/asic/repo/farm_hash_hiveon_17/).

### Возможные решения для устранения ошибки прошивки:

1. Переформатируйте MicroSD и убедитесь, что вы скопировали правильную прошивку.

2. Мягко нажмите на MicroSD, чтобы убедиться, что она надежно прикреплена.

3. Почистите MicroSD.

4. Попробуйте с другой, хорошо известной MicroSD. Не рекомендуется тип SDXC.

5. Попробуйте MicroSD меньшего объема.
