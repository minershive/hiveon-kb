---
title: Как начать майнить на пуле Hiveon
parent_category: Пул Hiveon
path: /hiveon-pool-hiveon-setting-up_ru
lang: ru
parent_category_path: /hiveon-pool_ru
meta_description: Начать майнинг на Hiveon Pool для пользователей Hive OS очень легко. Просто создайте кошелек, создайте полетный лист с пулом Hiveon и примените его к воркеру. Пользователи Windows также могут легко использовать Hiveon Pool.
order: 1
---

Вы собираетесь начать майнить на пуле Hiveon? Прекрасно! Чтобы облегчить вам жизнь, мы подробно описали процесс перехода на пул как для пользователей Hive OS, так и для пользователей Windows. Следуйте данной инструкции.

## Если вы - пользователь Hive OS
### Шаг 1: Создайте кошелек
Чтобы начать майнить Ethereum на пуле Hiveon, вам нужно сперва создать кошелек. Чтобы сделать это, войдите в систему, перейдите на вкладку **Wallets** и нажмите кнопку **Add Wallet**. Вам нужно будет указать монету (ETH), адрес, имя и источник.

<img src="https://lbd.hiveos.farm/kbase/images/hiveon-pool/hiveonpool1.png">

Когда вы закончите, нажмите на кнопку **Create**. Ваш кошелек готов!

### Шаг 2: Создайте Полетный Лист
Чтобы создать Полетный Лист, перейдите во вкладку **Flight Sheets**. Вы увидите следующее:

<img src="https://lbd.hiveos.farm/kbase/images/hiveon-pool/hiveonpool2.png">

Вам нужно будет заполнить такие поля:

- Coin: выберите ETH
- Wallet: выберите ваш кошелек Ethereum wallet
- Pool: выберите пул Hiveon из выпадающего списка
- Miner: выберите майнер
- Name: введите имя для вашего Полетного Листа (опционально)
- Нажмите кнопку **Create Flight Sheet**

<img src="https://lbd.hiveos.farm/kbase/images/hiveon-pool/hiveonpool3.png">

### Шаг 3: Примените Полетный Лист к вашему воркеру

Есть два способа это сделать:

**Способ 1**: Перейдите во вкладку **Workers**, выберите конкретный воркер, а затем перейдите во вкладку **Flight Sheets** в меню рига. Нажмите на иконку в виде ракеты в верхнем правом углу.

<img src="https://lbd.hiveos.farm/kbase/images/hiveon-pool/hiveonpool4.png">

**Способ 2**: Перейдите во вкладку **Workers** и отметьте флажками те риги, к которым вы хотите применить Полетный Лист. Опять же, вы должны будете нажать на иконку с ракетой.

Как только вы нажмете на ракету, вы увидите окно с количеством выбранных вами воркеров и список всех ваших Полетных Листов. Выберите Полетный Лист, который вы создали, и нажмите кнопку **Apply**. Вы должны увидеть сообщение о том, что команда была отправлена на воркер (или воркеры). Через несколько секунд ваши риги должны применить изменения, и вы увидите сообщение Config в журналах активности:

<img src="https://lbd.hiveos.farm/kbase/images/hiveon-pool/hiveonpool5.png">

Теперь все готово! Ваша установка должна начать добычу, посылая данные на панель управления. Вы сможете видеть ее показатели в режиме реального времени.

## Если вы - пользователь Windows
Если вы майните на Windows без использования Hive OS, вам нужно выполнить следующие шаги:

### Шаг 1: Скопируйте пакетный файл

Мы подготовили ряд [пакетных файлов](http://download.hiveos.farm/hiveon/) для наиболее популярных майнеров: Claymore's ETH Miner, PhoenixMiner и ETHminer. Выберите пакетный файл для вашего майнера и скопируйте его в папку с майнером.

### Шаг 2: Oткройте файл
Откройте файл текстовым редактором (Notepad++) и впишите ваши данные:

- Ваш кошелек вместо `PUT_YOUR_WALLET_HERE`.

- При необходимости, введите имя вашего воркера в `WORKER_NAME`.

- Задайте локацию, в которой вы находитесь (или ближайшую к вам) в `POOL_URL - RU, EU, NAW`

Теперь сохраните файл, запустите его и начинайте использовать Hiveon pool. Счастливого майнинга!

## Видео
Если вам нужно больше подробностей о пуле Hiveon и его настройке, ознакомьтесь с данными видео. Кроме того, если у вас есть вопросы о пуле Hiveon, вы всегда можете задать их [здесь](https://t.me/hiveon_ru).

- <a href="https://www.youtube.com/watch?v=CTneKYGOBzg">Новый пул для майнинга ETH + ETC + XMR = Hiveon Pool</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=CTneKYGOBzg
" target="_blank"><img src="http://img.youtube.com/vi/CTneKYGOBzg/0.jpg"
alt="Новый пул для майнинга ETH + ETC + XMR = Hiveon Pool"></a>

- <a href="https://www.youtube.com/watch?v=vCejU1r2MhM">Hive OS Пул для ETH // Настройка Hiveon.net Mining PooL Ethereum</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=vCejU1r2MhM
" target="_blank"><img src="http://img.youtube.com/vi/vCejU1r2MhM/0.jpg"
alt="Hive OS Пул для ETH // Настройка Hiveon.net Mining PooL Ethereum"></a>
