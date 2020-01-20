---
title: Кастом майнер
---

## Кастом Майнер
Как добавить майнер, которого нет в системе? Следуйте инструкции:

1. Подбор подходящего майнера
Полный список, с архивами, уже подготовленными для установки в HIVE OS, находится тут: http://download.hiveos.farm/custom/.
<img data-attachment-id="567" data-permalink="http://finance-quality.ru/nastrojka-hive-os-kak-dobavit-majner-kotorogo-net-v-sisteme/custom-hiveos/#main" data-orig-file="https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?fit=697%2C399" data-orig-size="697,399" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="custom-hiveos" data-image-description="" data-medium-file="https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?fit=250%2C143" data-large-file="https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?fit=480%2C275" class="size-full wp-image-567" src="https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?resize=697%2C399" alt="Страница HIVE OS с кастомными майнерами." width="687" height="394" srcset="https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?w=697 697w, https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?resize=150%2C86 150w, https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?resize=250%2C143 250w, https://i0.wp.com/finance-quality.ru/wp-content/uploads/2018/11/custom-hiveos.jpg?resize=480%2C275 480w" sizes="(max-width: 697px) 100vw, 697px">

Для установки архива вручную: скачайте и распакуйте содержимое архива в папку /hive/custom. Учтите, что даже скопировав и распаковав архив самостоятельно, вам всё равно придется указать ссылку на архив с майнером, при настройке Полетного Листа.

2. Настройка Полетного Листа
Перейдите на вкладку "Полетные Листы", в панели управления вашими фермами, и начните заполнять форму для добавления нового полетного листа:

- Имя  - название полетного листа в списке. Например: ETH на nanopool майнер claymore; flypool zcash on dstm; и т.д. Хотя и без заполнения этого поля полетные листы прекрасно читаются.
- Монета — либо выбирайте из списка, либо впишите название сами.
- Кошелек — выберите кошелек для монеты, если уже добавили, либо добавьте на данном этапе.
- Пул — выбирайте Настроить майнер.
- Майнер — выбирайте "Custom" и переходите в "Конфиг. майнера", для настройки пользовательского майнера. Обратите внимание, что все майнеры разные, и имеют разные настройки!

3. Настройка майнера
Так как мы настраиваем сторонний майнер, нам нужно сконфигурировать настройки самостоятельно, через окно Конфиг. майнера:

- Имя майнера — используйте название архива. Например: если архив назывался phoenixminer-3.5_c.tar.gz, то имя майнера надо указать как phoenixminer.
- Установочный URL — скопируйте прямую ссылку на нужный майнер из списка майнеров HIVE OS.
- Хеш алгоритм — выберите алгоритм для майнинга из списка, если он там есть. Если нет — то и не выбирайте.
- Кошелек и воркер шаблона — зависит от настроек майнера. Но, скорее всего, как минимум %WAL% надо будет вписать.
- Адрес пула — адрес пула, а также настройки пула (урл и порты).
- Пароль — x как настройка по умолчанию, иногда указывается тикер монетки, если на пуле, на одном алгоритме, монет много. Иногда бывает указывается порог выплат. Зависит от настроек и возможностей пула.
- Дополнительные параметры конфигурации — специфические настройки майнеров, или пула. Например, указываются алгоритмы майнинга. Рекомендуем читать инструкцию к майнеру.
- Нажмите "Применить изменения".

Закончив настройку, нажмите кнопку "Создать полетный лист". Теперь им можно пользоваться!

### Пример: как установить и настроить Phoenix Miner на HIVE OS?
Для примера показана настройка стороннего майнера Phoenix Miner 3.5c пул HIVE с алгоритмом ethash.

1. Настройка полетного листа
<img data-attachment-id="568" data-permalink="http://finance-quality.ru/nastrojka-hive-os-kak-dobavit-majner-kotorogo-net-v-sisteme/hive-os-custom-flightsheet/#main" data-orig-file="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-flightsheet.gif?fit=1210%2C250" data-orig-size="1210,250" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="hive-os-custom-flightsheet" data-image-description="" data-medium-file="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-flightsheet.gif?fit=250%2C52" data-large-file="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-flightsheet.gif?fit=480%2C99" class="wp-image-568 size-full" src="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-flightsheet.gif?zoom=2.0000000298023224&amp;resize=800%2C166" alt="" width="340" height="70" data-recalc-dims="1" srcset="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-flightsheet.gif?zoom=1.25&amp;resize=800%2C166" src-orig="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-flightsheet.gif?resize=900%2C186" scale="2.0000000298023224">

- Монета — ETH
- Кошелек — в примере кошелек ETH уже был создан заранее.
- Пул — выберите "Настроить майнер".
- Майнер — выберите "Custom" и нажмите "Конфиг. майнера".
- Имя — Phoenix on Hiveon.

2. Настройка майнера

<img data-attachment-id="569" data-permalink="http://finance-quality.ru/nastrojka-hive-os-kak-dobavit-majner-kotorogo-net-v-sisteme/hive-os-custom-miner-config/#main" data-orig-file="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-miner-config.gif?fit=544%2C588" data-orig-size="544,588" data-comments-opened="1" data-image-meta="{&quot;aperture&quot;:&quot;0&quot;,&quot;credit&quot;:&quot;&quot;,&quot;camera&quot;:&quot;&quot;,&quot;caption&quot;:&quot;&quot;,&quot;created_timestamp&quot;:&quot;0&quot;,&quot;copyright&quot;:&quot;&quot;,&quot;focal_length&quot;:&quot;0&quot;,&quot;iso&quot;:&quot;0&quot;,&quot;shutter_speed&quot;:&quot;0&quot;,&quot;title&quot;:&quot;&quot;,&quot;orientation&quot;:&quot;0&quot;}" data-image-title="hive-os-custom-miner-config" data-image-description="" data-medium-file="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-miner-config.gif?fit=250%2C270" data-large-file="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-miner-config.gif?fit=480%2C519" class="wp-image-569 size-full" src="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-miner-config.gif?zoom=2.0000000298023224&amp;resize=534%2C577" alt="" width="340" height="367" data-recalc-dims="1" srcset="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-miner-config.gif?zoom=1.25&amp;resize=534%2C577" src-orig="https://i2.wp.com/finance-quality.ru/wp-content/uploads/2018/11/hive-os-custom-miner-config.gif?resize=544%2C588" scale="2.0000000298023224">

- Имя майнера — в данном случае будет: phoenixminer.
- Установочный URL — добавьте урл архива http://download.hiveos.farm/custom/phoenixminer-3.5_c.tar.gz.
- Хеш алгоритм — выберите ethash из выпадающего списка.
- Кошелек и воркер шаблона — null, т.к. мы используем уже имеющийся ETH кошелек.
- Адрес пула — используем следующие параметры:

POOL: eu-eth.hiveon.net:4444, WALLET: %WAL%, WORKER:%WORKER_NAME%

POOL: eu-eth.hiveon.net:14444, WALLET: %WAL%, WORKER:%WORKER_NAME%
- Пароль — установите x.
- Дополн. параметры конфигурации — в данном примере ничего заполнять не надо.
- Нажмите "Применить изменения".
- Нажмите "Создать полетный лист".
