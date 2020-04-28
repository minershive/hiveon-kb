---
title: NiceHash
parent_category: Гайды
path: /guides-nice_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

<img src="http://forum.hiveos.farm/uploads/editor/vp/1fs7ux2lalf8.png">

Один из наиболее популярных вопросов от новичков - поддерживает ли Hive OS NiceHash и как его настроить.
Если кратко то да, Hive OS прекрасно работает с этим сервисом.
О том, как его настроить, далее.

Прежде всего, стоит напомнить, что используя сервис NiceHash, вы не добываете криптовалюту в привычном понимании майнинга. Этот сервис покупает у вас мощность, за что выплачивает вам вознаграждение в биткоинах.

Hive OS же в свою содержит все необходимые программы для работы с этим сервисом как на картах AMD так и Nvidia.

Выплаты данный сервис может осуществлять как на внешний, так и внутренний кошелек. В большинстве случаев, выплата на внутренний кошелек более удобна, и именно она будет здесь рассматриваться.

В меню управления ригом есть готовые шаблоны для NiceHash:
<img src="https://forum.hiveos.farm/uploads/editor/ua/iq1dhcc4nq6u.png">

После клика на шаблон вам остается только заменить кошелек на свой, как показано на картинке:

<img src="http://forum.hiveos.farm/uploads/editor/xw/6n0vbcqy513e.png">

Где взять этот адрес? В вашем личном кабинете NiceHash, в меню “Кошельки”.

Второе что необходимо знать - это адрес и порт под определенный алгоритм.
Где брать адрес и порт под определенный алгоритм? Переходим на [эту](https://www.nicehash.com/stratum-generator) страницу, выбираем алгоритм и локацию:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\nice\16ru.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\nice\16ru.png"
  />

И вуаля:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\nice\15ru.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\nice\15ru.png"
  />

Сервис NiceHash поддерживает разделение по ригам поэтому вы можете задать адрес в формате:

**YourNiceHashBTCaddress.Worker**

- YourNiceHashBTCaddress - адрес Вашего Биткоин кошелька на сервисе
- Worker - имя рига (воркера)

В Hive OS вы можете для удобства воспользоваться макроподстановками:
- %EWAL% - для майнеров Claymore Dual, Etherminer (алгоритм DaggerHashimoto)
- %ZWAL% - для майнеров Claymore ZCash, ewbf, dstm (алгоритм Equihash)
- %DWAL% - для всех остальных майнеров и алгоритмов
- %WORKER_NAME% - имя рига (воркера)

### Видео
- <a href="https://www.youtube.com/watch?v=W9bnWIwitow">Hive OS. 2.0 настройка Майнинга NiceHash CryptoNightV8</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=W9bnWIwitow
" target="_blank"><img src="http://img.youtube.com/vi/W9bnWIwitow/0.jpg"
alt="Hive OS. 2.0 настройка Майнинга NiceHash CryptoNightV8" width="630" height="400" border="10" /></a>

- <a href="https://www.youtube.com/watch?v=yHTYCNw-n6k">Hive OS 2.0 настройка алгоритма X16R на NiceHash. Обзор доходности. Обновление проблемного рига.</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=yHTYCNw-n6k
" target="_blank"><img src="http://img.youtube.com/vi/yHTYCNw-n6k/0.jpg"
alt="Hive OS 2.0 настройка алгоритма X16R на NiceHash. Обзор доходности. Обновление проблемного рига." width="630" height="400" border="10" /></a>

- <a href="https://www.youtube.com/watch?v=JKnCA50lDDU">Hive OS 2.0 NiceHash настройка</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=JKnCA50lDDU
" target="_blank"><img src="http://img.youtube.com/vi/JKnCA50lDDU/0.jpg"
alt="Hive OS 2.0 NiceHash настройка" width="630" height="400" border="10" /></a>
