---
title: Как работает Биллинг в Hive
---
## Как работает Биллинг в Hive
### Используемые термины

**Майнинг** - вычисления, производимые устройством для добычи криптовалют.

**Криптовалюта** - разновидность цифровых электронных денег, которые используются как альтернатива национальным валютам.

**Воркер** - устройство, подключенное к Hive OS для отображения статистики, мониторинга и управления процессом майнинга.

К Hive OS могут быть подключены следующие устройства: **CPU риг**, **GPU риг**, **ASIC**.

**CPU риг** - устройство, в составе которого не более одной видеокарты. Майнинг криптовалюты производится центральным процессором или процессорами без участия видеокарт.

**GPU риг** - устройство, содержащее одну или более видеокарт, используемых для майнинга криптовалют.

**ASIC** - специализированное устройство, предназначенное для майнинга криптовалюты.

**Ферма** - совокупность воркеров, объединенных по определенному признаку или без него.

**Hiveon ASIC** - серия прошивок для различных моделей ASIC, разработанные для использования ASIC совместно c Hive OS, обладающих по сравнению с заводской  прошивкой дополнительными возможностями и отсутствием платы за Hive OS.

**Бесплатный аккаунт** - аккаунт, в котором суммарно находится 4 и менее воркеров (с определенными условиями).

**Платный аккаунт** - аккаунт, в котором суммарно находится 5 и более воркеров.

Ознакомьтесь со всеми условиями бесплатных и платных аккаунтов ниже!

### Тарификация в Hive OS

Баланс в Hive OS представляет собой предоплаченную систему. Вам нужно сделать депозит, чтобы иметь больше 4 (четырех) бесплатных воркеров в вашем аккаунте или пользоваться платными услугами в бесплатном аккаунте.

Депозит может быть минимальным, не обязательно заранее оплачивать весь месяц. Есть возможность пополнить баланс даже на 1 доллар, например, чтобы попробовать.

Воркеры тарифицируются за каждый день, а не помесячно. Тарификация в течении дня проводится каждые 5 минут. Это означает, что воркер, который был активен лишь некоторое время, будет тарифицирован пропорционально активному времени, а не за целые сутки. Если воркер был в сети, и мы видим его в статистике, он будет учитываться. Если воркер был отключен, он не учитывается - не нужно деактивировать его в интерфейсе, чтобы остановить выставление счетов по нему.

Списание средств с баланса происходит за предыдущий день. Например: 0.5$ спишется с вашего баланса в 02:15 4 июня за 5 ригов онлайн с 02:15 3 июня по 02:15 4 июня.

>Важно! При обнаружении мошеннических действий с тарификацией со стороны пользователя, счет будет выставлен в полном объеме.

### Тарифные пакеты

Стандартный тариф:
- CPU риг - 0.30$/месяц с устройства
- GPU риг - 3$/месяц с устройства
- ASIC без прошивки [Hiveon][https://hiveos.farm/asic] - 2$/месяц с устройства

Стандартный тариф применяется к платным воркерам и указан без учета возможных скидок.

ASIC с прошивкой [Hiveon](https://hiveos.farm/asic) не тарифицируется и не учитывается в общем количестве воркеров, подлежащих оплате.
Например. Если у вас 10 Antminer S17, работающих на прошивке Hiveon ASIC, вы можете пользоваться Hive OS для менеджмента бесплатно.
Если же у вас 10 Antminer S17 - на прошивке Hiveon ASIC, и 10 Antminer S9k - на стоковой прошивке, стоимость использования Hive OS в таком случае будет составлять 20$/месяц (2$/месяц с одного ASIC устройства * 10 устройств)

Плата за использование Hive OS зависит от тарифного пакета. Пакеты отличаются максимальным числом воркеров в системе  и перечнем предоставляемых услуг. Переход от одного пакета к другому осуществляется путем подключения или отключения воркеров.

### Бесплатный пакет

Владельцы бесплатных аккаунтов могут использовать до 4х воркеров без оплаты, при соблюдении определенных правил:
- 1 риг бесплатен без каких-либо ограничений.

Для владельцев от 2 до 4-х воркеров, пользование системой остается бесплатным в случае:
- майнинга Ethereum на пуле [Hiveon](https://www.hiveon.net)
- майнинга других монет, кроме Ethereum, на любых других пулах


Если 2 и более ваших воркеров майнят Ethereum не на пуле [Hiveon](https://www.hiveon.net), применяется стандартный тариф 3$/мес. за каждый такой воркер.
Система остается бесплатной до тех пор, пока у вас **4** воркера и соблюдены все условия бесплатных аккаунтов. Если вы добавляете 5-й воркер в ваш аккаунт, будет произведен расчет и списана ежедневная плата **за все 5 воркеров**.

### Оплата системы: депозиты

Hive OS принимает только криптовалюту. Осуществить оплату за Hive OS можно несколькими способами:
- на генерируемый в личном кабинете ваш персональный адрес Ethereum;

- на генерируемый в личном кабинете ваш персональный адрес ERC20 стейблкоинов (поддерживаются USDT, USDC, TUSD);

- с помощью платежного шлюза [Coinpayments](https://www.coinpayments.net/) (принимаются BTC, BEAM, ETC, LTC, XMR, XRP);

- за счет реферальных вознаграждений (читайте ниже в разделе “Реферальная система”).


Узнать об осуществлении платежей подробнее можно [здесь](https://forum.hiveos.farm/t/payments-faq/3537/2).

### Оплата системы: комиссия на пуле Hiveon

Для платных пользователей, которые добывают криптовалюту Ethereum, существует опциональная возможность оплачивать Hive OS за счет майнинга на пуле Hiveon и удерживаемой комиссии 3% от добычи в качестве оплаты за Hive OS.

Обратите внимание, что этот способ применим только к устройствам, осуществляющим добычу Ethereum на пуле Hiveon. К остальным устройствам будет применен стандартный тариф.

### Комиссия разработчика HiveOn ASIC

С прошивкой Hiveon ASIC нет платы за использование Hive OS, и такие ASIC не учитываются в общем количестве устройств для расчета оплаты, но учитываются для получения скидки от количества устройств.

Прошивка содержит комиссию разработчика от 2% до 2.8%, в зависимости от модели ASIC.

### Возврат средств

Так как баланс Hive OS представляет собой предоплаченную систему, то возврат или снятие средств недоступны. Вы можете переводить средства между пользователями и фермами, но вариант вывода отсутствует.

### Реферальная система

Вы можете приглашать друзей и свою аудиторию в Hive OS, и зарабатывать на этом - 10% от того, что каждый приведенный вами реферал платит за использование Hive OS. Реферальные награды выплачиваются раз в месяц на указанный в настройках ETH адрес.
Реферальные выплаты могут быть использованы также для пополнения баланса.
Подробнее про условия реферальной системы читайте [здесь](https://hiveos.farm/pricing/).

### Скидки

Скидки применяются к общему числу воркеров во всех фермах, которыми вы владеете. Например, в ферме1 у вас 40 воркеров, а в ферме2 20 воркеров, в этом случае скидка применяется как за 60 воркеров (40+20).

С тарифами и скидками можно ознакомиться [здесь](https://hiveos.farm/pricing/).

Тарифы на ASIC ниже, чем для ГПУ ригов, потому что они имеют более простой функционал. Воркеры с прошивкой [Hiveon ASIC](https://hiveos.farm/asic) не тарифицируются и не учитываются в общем количестве для оплаты.

### Кредит

Если задолженность на вашей ферме от $1, у вас есть возможность получить кредит на 5 дней. Даже при отрицательном балансе, ваши воркеры будут работать.

Через 5 дней ферма заблокируется, майнинг будет остановлен. Отрицательный баланс будет покрываться автоматически после того, как вы внесете новый депозит.

### Пользовательский баланс и баланс фермы

Для более удобного управления средствами фермы имеют свои собственные балансы. Вы можете сделать депозит на свой пользовательский счет, а затем пополнить баланс конкретной фермы. Если баланс фермы равен 0, плата будет автоматически сниматься  с баланса пользователя, и вы можете не беспокоиться о пополнении баланса фермы напрямую.

### Платные функции

На странице биллинга присутствует кнопка, с помощью которой вы сможете активировать платные функции.

В перечне платных функций: SSL соединение воркера с серверами Hive, статистика за месяц и другие. Этот список будет изменяться и дополняться по мере имплементации новых функций [здесь](https://hiveos.farm/pricing/).

Будучи бесплатным пользователем (с 4 и менее воркерами) вы можете поддержать проект и получить выгоду от использования платных функций.

### Плательщик

Вы можете сделать другого пользователя ответственным за депонирование ферм, которыми вы владеете. Этот пользователь может быть вашим финансовым менеджером, например. Для этого требуется уровень доступа "Мониторинг".