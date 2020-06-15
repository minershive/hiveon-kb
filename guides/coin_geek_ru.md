---
title: Как майнить GeekCash на Hive OS
parent_category: Гайды
path: /guides-coin_geek_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

<img src="https://lbd.hiveos.farm/kbase/images/golos/DQmdua5LfZqEeuho8faPdsh2qt5WtzR57Yr9EXLnAY9L8bo.png">

Для майнинга на Hive OS вам нужно:
1. Добавьте адрес GeekCash кошелека куда будете майнить монетку:
<img src="https://lbd.hiveos.farm/kbase/images/golos/DQmZworYwjUqAuhXi9pTqV5aiuZLxK2Cho5jMjdjagwvn9L.png">

2. Создайте Полетный Лист, где выберите монету и кошелек, и укажите "Custom miner" как майнер. Нажмите **Setup Miner Config**:
<img src="https://lbd.hiveos.farm/kbase/images/golos/DQmV2xvAt1FkDAGa5gG86aNU4Eit4JD5z8y3qYAwQ5Qvi7U.png">

3. Для видеокарт Nvidia в конфигурации майнера укажите:
<img src="https://lbd.hiveos.farm/kbase/images/golos/DQmae8Gsror11SpLWAxPjdFcbMnJTxmE3bkE82HNZHFd3e6.png">

- Miner name: geekminer
- Installation URL: http://files.miner.ninja/geekminer.tar.gz
- Hash algorithm: geek
- Wallet and worker template: %WAL%
- Pool URL: stratum+tcp://geek.miner.ninja:5555
- Pass: x
- Extra config arguments: -i 21

Сохраняем конфигурацию майнера и создаем полетный лист: **Create Flight Sheet**.

***Важно:*** при запуске GeekCash майнера подождите, пока скачается майнер (2-3 минуты, все зависит от скорости вашего интернета).

4. Для видеокарт AMD в конфигурации майнера указываем:
<img src="https://lbd.hiveos.farm/kbase/images/golos/DQmTnMKg6E3TToA3cdsNPTX5DcbWoU33eygUkogBRqqcE3n.png">

- Miner name: sgminer_geek
- Installation URL: http://files.miner.ninja/sgminer_geek.tar.gz
- Hash algorithm: geek
- Wallet and worker template: %WAL%
- Pool URL: stratum+tcp://geek.miner.ninja:5555
- Pass: x
- Extra config arguments: -g 2

Сохраняем конфигурацию майнера и создаем полетный лист: **Create Flight Sheet**.

***Важно:*** при запуске GeekCash майнера подождите, пока скачается майнер (2-3 минуты, все зависит от скорости вашего интернета).

### Рекомендуемый пул для GeekCash майнинга - Geek.Miner.Ninja
- Всего 0.5% комиссия пула
- Предварительно сконфигурированный .BAT-файл с GPU и CPU майнером
- Для повышения устойчивости майнер автоматически перезагружается каждые 30 минут.

***Discord:*** https://discord.gg/cguh8pz

***GeekCash Discord:*** https://discord.gg/XwkgTxr

***Ссылка на сайт:*** https://geekcash.org

***Ссылка на кошелёк:*** https://geekcash.org/#wallets

***Nvidia GPU майнер с .BAT файлом можно скачать по ссылке:*** http://files.miner.ninja/geekminer.zip.

***Ссылка на CPU майнер:*** http://files.miner.ninja/cpuminer.zip.

***Командная строка для Nvidia GPU майнера:*** `geekminer.exe -a geek -o stratum + tcp: //geek.miner.ninja: 5555 -u {WALLET-ADDRESS}`

***Командная строка для CPU майнера:***
`cpuminer.exe -a geek -o stratum + tcp: //geek.miner.ninja: 3333 -u {WALLET-ADDRESS}`
