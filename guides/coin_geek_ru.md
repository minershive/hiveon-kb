title: GeekCash

## GeekCash
Как майнить GeekCash на HiveOS?
<img src="https://images.golos.io/DQmdua5LfZqEeuho8faPdsh2qt5WtzR57Yr9EXLnAY9L8bo/image.png" alt="image.png">

Для майнинга на HiveOS вам нужно:
1. Добавьте адрес GeekCash кошелека куда будете майнить монетку:
<img src="https://images.golos.io/DQmZworYwjUqAuhXi9pTqV5aiuZLxK2Cho5jMjdjagwvn9L/image.png" alt="image.png">

2. Создайте полетный лист "Flight Sheet", где выберите монету и кошелек, и укажите "Custom miner" как майнер. Нажмите "Setup Miner Config":
<img src="https://images.golos.io/DQmV2xvAt1FkDAGa5gG86aNU4Eit4JD5z8y3qYAwQ5Qvi7U/image.png" alt="image.png">

3. Для видеокарт Nvidia в конфигурации майнера укажите:
<img src="https://images.golos.io/DQmae8Gsror11SpLWAxPjdFcbMnJTxmE3bkE82HNZHFd3e6/image.png" alt="image.png">

Miner name: geekminer

Installation URL: http://files.miner.ninja/geekminer.tar.gz

Hash algorithm: geek

Wallet and worker template: %WAL%

Pool URL: stratum+tcp://geek.miner.ninja:5555

Pass: x

Extra config arguments: -i 21

Сохраняем конфигурацию майнера и создаем полетный лист "Create Flight Sheet"

***Важно:*** при запуске GeekCash майнера подождите, пока скачается майнер (2-3 миуты, все зависит от скорости вашего интернета).

4. Для видеокарт AMD в конфигурации майнера указываем:
<img src="https://images.golos.io/DQmTnMKg6E3TToA3cdsNPTX5DcbWoU33eygUkogBRqqcE3n/image.png" alt="image.png">

Miner name: sgminer_geek

Installation URL: http://files.miner.ninja/sgminer_geek.tar.gz

Hash algorithm: geek

Wallet and worker template: %WAL%

Pool URL: stratum+tcp://geek.miner.ninja:5555

Pass: x

Extra config arguments: -g 2

Сохраняем конфигурацию майнера и создаем полетный лист "Create Flight Sheet"

***Важно:*** при запуске GeekCash майнера подождите, пока скачается майнер (2-3 миуты, все зависит от скорости вашего интернета).

### Рекомендуемый пул для GeekCash майнинга - Geek.Miner.Ninja
- Всего 0.5% комиссия пула
- Предварительно сконфигурированный .BAT-файл с GPU и CPU майнером
- Для повышения устойчивости майнер автоматически перезагружаться каждые 30 мин.

***Discord:*** https://discord.gg/cguh8pz

***GeekCash Discord:*** https://discord.gg/XwkgTxr

***Ссылка на сайт:*** https://geekcash.org

***Ссылка на кошелёк:*** https://geekcash.org/#wallets

***Nvidia GPU майнер с .BAT файлом можно скачать по ссылке:*** http://files.miner.ninja/geekminer.zip.

***Ссылка на CPU майнер:*** http://files.miner.ninja/cpuminer.zip.

***Командная строка для Nvidia GPU майнера:***

geekminer.exe -a geek -o stratum + tcp: //geek.miner.ninja: 5555 -u {WALLET-ADDRESS}

***Командная строка для CPU майнера:***
cpuminer.exe -a geek -o stratum + tcp: //geek.miner.ninja: 3333 -u {WALLET-ADDRESS}
