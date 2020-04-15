---
title: Инструкция по Установке L3+/L3++
parent_category: Прошивка Hiveon ASIC
category: L3+/L3++
path: /hiveon-asic-firmware-L3_installation_ru
lang: ru
parent_category_path: /hiveon-asic-firmware_ru
category_path: /hiveon-asic-firmware-L3_ru
order: 1
---

## Инструкция по установке прошивки Hiveon ASIC: L3+/L3++

## Варианты установки
Поскольку универсальных инструкций не существует, мы рассмотрим три сценария установки или обновления вашего оборудования при помощи Hiveon ASIC. Будут рассмотрены следующие темы:

- Установка через веб-интерфейс ASICа — подходит для установки на несколько устройств (для пользователей, которые ранее не использовали Hive OS);
- Массовая установка — подходит для установки на целые фермы;
- Обновление уже имеющихся ASICов через веб-интерфейс Hive OS — подходит для тех, кто уже использует Hive на своих ASICах;
- Массовое обновление уже имеющихся ASICов — подходит для обновления целых ферм.

### Вариант 1: Установка через веб-интерфейс ASICа
Перейдите на [эту страницу](https://hiveos.farm/asic/) и скачайте прошивку:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\L3+\Screenshot_38.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\L3+\Screenshot_38.png"
  />

Когда ваша ASIC включен (предполагается, что он находится в одной сети с вами), подключитесь к нему с помощью компьютера или мобильного устройства. Введите IP-адрес вашего майнера. У большинство майнеров DHCP уже включен, поэтому вам не нужно вручную устанавливать IP-адрес для него. Вместо этого посмотрите на таблицу IP на вашем маршрутизаторе или используйте инструмент сканирования.

<img src="https://miro.medium.com/max/1594/0*eboE5sjqgcnXDAuM">

Войдите в майнер. Логин и пароль по умолчанию - root. Вы будете авторизованы в окне обзора системы. Если вы впервые настраиваете ASIC, не забудьте сначала изменить пароль по умолчанию на вкладке Admin.

<img src="https://miro.medium.com/max/1594/0*CPGII9JKr1qVvZOL">

Перейдите на вкладку **Upgrade**, там вы увидите раздел образа **Flash new firmware**. Нажмите на **Choose File**, чтобы выбрать образ, который вы предварительно загрузили, а затем нажмите на кнопку **Flash image…** и подождите, пока он установится.

Если будет ошибка **Cannot Find Signature!!!**, то перед прошивкой на Hiveon прошейте ASIC [этим файлом](http://download.hiveos.farm/asic/L3%2B/tools/remsig_L3_for_hiveon.tar.gz) и повторите процесс перепрошивки файлом прошивки Hiveon.

Теперь вам нужно будет получить ваш Farm Hash в <a href="https://the.hiveos.farm/">веб-интерфейсе Hive OS</a>. Перейдите во вкладку настроек вашей фермы (**Settings**), там вы увидите ваш **Farm Hash**. Скопируйте его в буфер обмена.

<img src="https://miro.medium.com/max/1569/0*wkNCiVtWtNRB92s7">

Как только ASIC был прошит и перезагружен, снова подключитесь к нему и перейдите на вкладку **Hive OS** в **System window**. Вставьте ваш Farm Hash в поле **FARM_HASH** и нажмите **Save & Apply**. Ваш ASIC будет добавлен к вашей ферме в Hive OS.

<img src="https://miro.medium.com/max/1750/0*sPTOf6QkmcQhBkxI">

Вот и всё, теперь вы можете настраивать ваш ASIC.

### Вариант 2: массовая установка
Используйте BTC_TOOLS для массовой прошивки ASIC-ов. Укажите в нем путь к файлу прошивки Hiveon.

Если будет ошибка **Cannot Find Signature!!!**, то перед прошивкой на Hiveon прошейте ASIC [этим файлом](http://download.hiveos.farm/asic/L3%2B/tools/remsig_L3_for_hiveon.tar.gz) и повторите процесс перепрошивки файлом прошивки Hiveon.

## Hiveon ASIC: автоматическая настройка тюнера
После установки новой прошивки вы можете снова войти в свой ASIC майнер. На этот раз вас встретит новая страница обзора пользовательского интерфейса Hiveon ASIC. Давайте пока посмотрим на Профили и основные настройки.

**Внимание! Чтобы использовать большинство из этих опций, вам необходимо иметь кастомный источник питания, подключенный к вашему ASICу. Заводской блок питания недостаточно мощный, чтобы справиться с нагрузкой, и ваш ASIC выключится.**


<img src="https://miro.medium.com/max/1598/0*p_4TaOOpSKRnJPP9">

Чтобы выбрать нужный **Profile**, перейдите на вкладку **Miner Configuration**, а затеам - на **Auto Tuner Configuration**. Там вы сможете выбрать профиль, который соответствует вашим потребностям лучше всего.

Небольшой дисклеймер: **Мы не рекомендуем выбирать ручной режим (Manual mode), если вы не обладаете достаточными навыками ручной настройки ASIC.** Мы не будем описывать ручную процедуру, поскольку её практически невозможно описать кратко.

<img src="https://miro.medium.com/max/1589/0*pNPYfVdlrcuFH7fg">

Затем нажмите кнопку **Apply Changes** внизу страницы и подождите, пока алгоритм завершит автонастройку ASICа. Это может занять до часа (в зависимости от выбранного профиля). Ваш хешрейт может сильно колебаться во время процесса - это нормально.

## Обновление

### Вариант 1: при помощи веб-интерфейса Hive OS
Предполагая, что вы уже используете Hive OS с вашими ASICами, вам нужно сначала обновить их до совместимой прошивки. Если ваша модель ASIC совместима, вы увидите желтый текст **Switch** рядом с версией ОС в нижней части страницы **Overview** вашего воркера.

<img src="https://miro.medium.com/max/429/0*SY96QIG33Br2aa8_">

Нажмите на него, и появится новое контекстное окно **Change ASIC Firmwares**. Затем нажмите на выпадающий список **Select firmware** и выберите нужную версию прошивки. В данном примере это будет **Antminer-S9-all-Hiveon** (для L3+/L3++ процесс такой же, просто выберите соответствующий файл). Нажмите **Apply**.

<img src="https://miro.medium.com/max/1260/0*ssmeT6INSpHJgLKg">

ASIC отключится и перезагрузится, но вскоре он снова появится онлайн, и его название модели изменится с Antminer S9 на Antminer S9 Hiveon (с L3+ на L3+ Hiveon соответственно). Версия прошивки также изменится.

<img src="https://miro.medium.com/max/1581/0*lp4ZUANA-e0btQfk">

Вот и все, теперь вы можете настроить ASIC с помощью авто-тюнера.

### Вариант 2: Массовое обновление
Предполагая, что вы уже используете Hive OS со своими ASICами, вам нужно сначала обновить их до совместимой прошивки.

<img src="https://miro.medium.com/max/1590/0*6FpiMVYCUCghtbC1">

На вкладке **Workers**, выберите воркеры, которые вы хотите обновить. Вы увидите несколько действий в правом верхнем углу экрана.

<img src="https://miro.medium.com/max/911/0*KkPY3QOPvbUkbrpd">

Нажмите на кнопку **ASIC Firmware**, и появится новое контекстное окно **Change ASIC Firmwares**. Затем нажмите на выпадающий список **Select firmware** и выберите нужную версию прошивки. В данном примере это будет **Antminer-S9-all-Hiveon** (для L3+/L3++ процесс такой же, просто выберите соответствующий файл). Нажмите **Apply**.

<img src="https://miro.medium.com/max/1260/0*AWw3uCKwWV_jvxNB">

ASICи отключатся и перезагрузятся, но вскоре они снова появятся онлайн, и их названия модели изменится с Antminer S9 на Antminer S9 Hiveon (с L3+ на L3+ Hiveon соответственно). Версия прошивки также изменится.

<img src="https://miro.medium.com/max/1581/0*869YrhWn8EAKGOhz">

Вот и все, теперь вы можете настроить ASIC с помощью авто-тюнера.

## Веб-интерфейс Hive OS: автоматическая настройка тюнера
После успешной прошивки ASICов, вы можете настроить наши предварительно созданные профили автоматической настройки. Там вы можете выбрать профиль, который соответствует вашим потребностям лучше всего.

Небольшой дисклеймер: **Мы не рекомендуем выбирать ручной режим (Manual mode), если вы не обладаете достаточными навыками ручной настройки ASIC.** Мы не будем описывать ручную процедуру, поскольку её практически невозможно описать кратко.

**Внимание! Чтобы использовать большинство из этих опций, вам необходимо иметь кастомный источник питания, подключенный к вашему ASICу. Заводской блок питания недостаточно мощный, чтобы справиться с нагрузкой, и ваш ASIC выключится.**

На вкладке **Workers** выберите воркеры, на которых вы хотите запустить скрипт автонастройки.

<img src="https://miro.medium.com/max/1590/0*VaoCeqoiLP3rbK8k">

Вы увидите несколько действий в правом верхнем углу экрана. Нажмите на кнопку **Overclocking**. Появится новое контекстное окно.

<img src="https://miro.medium.com/max/959/0*OGNBrUL3NWFR-CVn">

Выберите нужный профиль, затем нажмите кнопку **Apply Changes** в нижней части окна и подождите, пока алгоритм завершит автонастройку ASICа. Это может занять до часа (в зависимости от выбранного профиля). Ваш хешрейт может сильно колебаться во время процесса - это нормально.

<img src="https://miro.medium.com/max/560/0*RYEhl5muvMs9S8su">

Вот и все! Наши поздравления, и счастливого майнинга!