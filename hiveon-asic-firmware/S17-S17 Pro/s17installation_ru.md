---
title: Инструкция по Установке S17 (S17 Pro)
---

## Прошивка Hiveon ASIC S17 и S17 Pro: Инструкция по Установке
Чтобы облегчить процесс установки прошивок, мы приготовили для вас инструкцию. И перед тем, как объяснить все детали, позвольте напомнить вам, почему кастомная прошивка (особенно наша ;)) лучше заводской.

### Прошивка Hiveon ASIC: Характеристики
**S17:**

- До 72TH/s при охлаждении на воздухе.

**S17 Pro:**

- 80.1TH/s при подключении к стандартному блоку питания;
- 85TH/s с водным охлаждением.

**Кроме того:**
- Более высокая энергоэффективность благодаря андервольту;
- Чипы отключаются, когда ASIC переходит в режим оффлайн;
- Разгон ASIC чипов;
- Авто-настройка изношенных ASIC чипов (так они проживут дольше);
- Исправлены баги заводской прошивки;
- В случае поломки вентилятора или чипа, начнут мигать светодиоды, так что вы сразу же заметите проблему;
- Контроллеры температуры и хешрейта;
- Встроенный ваттметр;
- Надежная защита от вирусов;
- Восстановление устройств, которые были поражены вирусами ранее;
- 2,8% devfee;
- Hive OS для управления вашими фермами: бесплатно!

Теперь давайте посмотрим на основные профили потребления на S17.

<img class="nm ph eq t u hy ak ih" width="800" height="450" role="presentation" src="https://miro.medium.com/max/1000/0*L4brHN5bMKa06B_3">

Более развернутые данные вы можете увидеть в вашей учетной записи Hive OS.

### Важно!
А теперь вернемся к процессу установки. Универсального мануала не существует, так как для S17 и S17 Pro есть 3 версии заводской прошивки. Следовательно, для каждого конкретного случая существует своя инструкция по установке кастомной прошивки. Мы рассмотрим их все.

Учтите, что все шаги, требующие использования BTC_TOOLS, могут быть также выполнены через веб-интерфейс ASIC-а (BTC_TOOLS обычно применяется при большом количестве устройств).

### Подготовительные этапы (необходимы для всех вариантов)
1. Скачайте и распакуйте этот архив: http://download.hiveos.farm/asic/repo/fw/Antminer/s9k-s9se-st15-st17-installer.zip.

2. Просканируйте сеть через BTC_TOOLS, экспортируйте список в **csv**. Из csv скопируйте список **ip** и вставьте его в **ips.ini**. Если устройств немного, список можно составить вручную.

3. Сверьте в **config.ini** логин и пароль на веб или ssh ASIC-а. Если менялся пароль на веб, такой же будет и на ssh. Пропишите **FARM_HASH** для привязки к Hive или API при необходимости.

4. Скачайте файл прошивки (в названии должно быть “Hiveon”):
http://download.hiveos.farm/asic/s17/

Для S17 и S17 Pro мы предлагаем один и тот же файл прошивки. Впрочем, есть две опции: с подписью (signed) и без неё (nosigned). Прошивка с подписью может быть обновлена ТОЛЬКО на другую Hiveon прошивку с подписью, через веб-интерфейс ASIC-а или BTC_TOOLS. Сторонние или официальные прошивки не могут быть установлены таким образом. Тем не менее, вы можете использовать команду `rm -rf /etc/bitmain-pub.pem` — отправьте её на ваш ASIC через веб Hive. В результате, сертификат будет временно удален, но если вы перезагрузите ASIC, он вернется. После этого вы сможете перейти на любую прошивку в меню обновления прошивки (через веб Hive). Можно будет выбрать прошивку из списка или же использовать URL.

Скачать прошивку с подписью можно здесь:
http://download.hiveos.farm/asic/s17/Antminer-S17-S17pro-Hiveon-1.00-sign.tar.gz

<a href="https://forum.hiveos.farm/t/hiveon-asic-s9-firmware-v1-02/13944/2">Здесь</a> можно узнать о разнице прошивок с подписью и без. Теперь давайте подробно рассмотрим 3 варианта установки.

### Если заводская прошивка вашего ASIC-а была выпущена до 1 июля 2019
1. Прошейте ваши устройства файлом из архива **“remsig_all_before_2019–07–01.tar.gz”**. Это можно сделать или через веб-интерфейс ASIC-а, или же через BTC_TOOLS (если у вас много устройств). Вы увидите ошибку в статусе, но на данном этапе так и должно быть.

2. Прошейте устройства файлом прошивки. Опять же, это можно сделать через веб-интерфейс ASIC-а или через BTC_TOOLS.

3. Запустите из архива **“3_hash_farm_for_signed.cmd”**. ASIC привяжется к вебу.

### Если заводская прошивка была выпущена с июля 2019 до декабря 2019
1. Запустите из архива **“1_open_ssh.cmd”** и дождитесь выполнения скрипта. Устройства будут перезагружены. После перезагрузки подождите около 3 минут.

2. Запустите из архива **“2_upgrade_replace.cmd”** и дождитесь выполнения скрипта.

3. Прошейте устройства файлом прошивки (через веб-интерфейс ASIC-а или через BTC_TOOLS).

4. Запустите из архива **“3_hash_farm_for_signed.cmd”**. ASIC привяжется к вебу.

### Если заводская прошивка была выпущена после декабря 2019
На данный момент, способов установки нет. Как только они появятся, мы сразу же вас оповестим.

Мы **не рекомендуем** обновлять Antminer устройства до последней официальной прошивки, так как Bitmain не позволяет устанавливать кастомную прошивку.

Что ж, теперь вы знаете, как установить нашу прошивку Hiveon ASIC для Antminer S17 и S17 Pro. Но если у вас все же остались вопросы, вы можете задать их <a href="https://t.me/hiveonasic">здесь</a>.