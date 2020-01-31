---
title: Nicecash
category: Гайды
---

## Nicehash
<img src="http://forum.hiveos.farm/uploads/editor/vp/1fs7ux2lalf8.png" width="205" height="67">

Один из наиболее популярных вопросов от новичков - поддерживает ли HiveOS найсхеш и как его настроить.
Если кратко то да, HiveOS прекрасно работает с этим сервисом.
О том, как его настроить, далее.

Прежде всего, стоит напомнить, что используя сервис NiceHash, Вы не добываете криптовалюту в привычном понимании майнинга. Этот сервис покупает у вас мощность, за что выплачивает Вам вознаграждение в биткоинах.
HiveOS же в свою содержит все необходимые программы для работы с этим сервисом как на картах AMD так и Nvidia.
Выплаты данный сервис может осуществлять как на внешний, так и внутренний кошелек. В большинстве случаев выплата на внутренний кошелек более удобна, и именно она будет здесь рассматриваться.

В меню управления ригом есть готовый шаблон для найсхеш:
<img src="https://forum.hiveos.farm/uploads/editor/ua/iq1dhcc4nq6u.png">

После клика на этот шаблон вам остается только заменить кошелек на свой, как показано на картинке:
<img src="http://forum.hiveos.farm/uploads/editor/xw/6n0vbcqy513e.png">

Где взять этот адрес? В вашем личном кабинете NiceHash в меню “Кошелек” отображается как “Ваш Биткоин-адрес”.
HiveOS, как уже было отмечено, обладает всем спектром майнинговых программ. Второе что необходимо знать - это адрес и порт под определенный алгоритм.
Где брать адрес и порт под определенный алгоритм? Всё там же.
<img src="http://forum.hiveos.farm/uploads/editor/ur/a10znb744gvh.png">

Переходим на [эту](https://www.nicehash.com/cpu-gpu-mining) страницу, выбираем протокол и вуаля.
<img src="http://forum.hiveos.farm/uploads/editor/th/v4hbxjkigiz8.png">

Сервис НайсХеш поддерживает разделение по ригам поэтому Вы можете задать адрес в формате:
YourNiceHashBTCaddress.Worker,
где:
- YourNiceHashBTCaddress - адрес Вашего биткоин кошелька на сервисе
- Worker - имя рига (воркера)

В HiveOS Вы можете для удобства воспользоваться макроподстановками
- %EWAL% - для майнеров Claymore Dual, Etherminer (алгоритм DaggerHashimoto)
- %ZWAL% - для майнеров Claymore ZCash, ewbf, dstm (алгоритм Equihash)
- %DWAL% - для всех остальных майнеров и алгоритмов
- %WORKER_NAME% - имя рига (воркера)

### Видео
- <a href="https://www.youtube.com/watch?v=W9bnWIwitow">Hive OS. 2.0 настройка Майнинга nicehash CryptoNightV8</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=W9bnWIwitow
" target="_blank"><img src="http://img.youtube.com/vi/W9bnWIwitow/0.jpg"
alt="Hive OS. 2.0 настройка Майнинга nicehash CryptoNightV8" width="630" height="400" border="10" /></a>

- <a href="https://www.youtube.com/watch?v=yHTYCNw-n6k">HiveOS 2.0 настройка алгоритма X16R на Nicehash. Обзор доходности. Обновление проблемного рига.</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=yHTYCNw-n6k
" target="_blank"><img src="http://img.youtube.com/vi/yHTYCNw-n6k/0.jpg"
alt="HiveOS 2.0 настройка алгоритма X16R на Nicehash. Обзор доходности. Обновление проблемного рига." width="630" height="400" border="10" /></a>

- <a href="https://www.youtube.com/watch?v=JKnCA50lDDU">HiveOS 2.0 Nicehash настройка</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=JKnCA50lDDU
" target="_blank"><img src="http://img.youtube.com/vi/JKnCA50lDDU/0.jpg"
alt="HiveOS 2.0 Nicehash настройка" width="630" height="400" border="10" /></a>
