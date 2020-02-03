---
title: Как Майнить EXCC с Hive OS
category: Гайды
---

## Как майнить EXCC с Hive OS
Майнинг EXCC с Hive OS - это очень просто. Следуйте нашей инструкции:

***Шаг 1.*** Войдите в вашу ферму и, прежде всего, добавьте новый кошелек:
<img src="https://support.excc.co/hc/article_attachments/360020929152/hive1.png">

Учтите, что вам нужно будет создать монету ExchangeCoin, так как EXCC не встроена в Hive OS (пока что). Просто начните печатать ExchangeCoin в поле **Coin**, и система позволит вам сохранить новую монету. Поле **Address** - это ваш адрес EXCC, куда будут отправляться добытые монеты. Мы настоятельно рекомендуем использовать для этой цели программное обеспечение Exilibrium.

***Шаг 2.*** После создания нового кошелька и монеты, вам нужно создать новый Полетный Лист. Кликните на **Flight Sheets** в меню Hive OS и заполните следующие поля:
- Coin - выберите ExchangeCoin (если её нет, значит, вы не совсем верно выполнили Шаг 1)
- Wallet - выберите недавно созданный вами кошелек
- Pool - выберите **Configure In Miner**
- Miner - выберите lolMiner и нажмите **Setup Miner Config**

<img src="https://support.excc.co/hc/article_attachments/360020853671/mceclip0.png">

***Шаг 3.*** Теперь вы увидите окно конфиурации lolMiner. С помощью нашего примера, заполните поля:
- Wallet and worker template - %WAL%.%WORKER_NAME%
- Coin - EXCC
- Pool server: 35.176.212.123
- Port: 3052
- Pass: x
- Extra config arguments: Вы можете оставить это поле пустым, но, следуя рекомендации автора lolMiner, вы также можете использовать --devices AUTO
- Version: The latest

<img src="https://support.excc.co/hc/article_attachments/360020929572/mceclip2.png">

***Шаг 4.*** Как только вы закончите, вернитесь к списку ваших воркеров, проверьте ваши воркеры, кликните на иконку с ракетой наверху, и выберите только что созданный Полетный Лист.

<img src="https://support.excc.co/hc/article_attachments/360020929612/mceclip3.png">

Счастливого майнинга!
