---
title: Добавление кастомного майнера
parent_category: Начало Работы
path: /getting_started-start_custom_miner_ru
lang: ru
parent_category_path: /getting_started_ru
order: 1
meta_description: Вы не нашли желаемый майнер в списке? С Hive OS вы можете самостоятельно интегрировать нужный майнер, отсутствующий в образе.
---

Hive OS поддерживает не все алгоритмы майнеров - только несколько самых популярных. Чтобы решить этот вопрос, мы добавили новую функцию под названием Интеграция Кастомного Майнера, которая позволяет пользователям добавлять майнер, который не "заложен" в дистрибутивный образ Hive OS. У вас есть возможность либо установить предварительно созданный архив, либо создать его самостоятельно. В этом руководстве мы в основном рассмотрим шаги, необходимые для установки предварительно созданного архива.

### Установка кастомного майнера
Для начала перейдите на <a href="http://download.hiveos.farm/custom/">эту страницу</a> и просто скопируйте URL в файл.

<img src="https://lbd.hiveos.farm/kbase/images/start_custom_miner/custom_miners.png" />

_Репозиторий кастомного майнера_

Чтобы вручную установить кастомный архив на риг, вы можете скачать его и распаковать в папку `/hive/custom`. Учтите, что даже скопировав и распаковав архив самостоятельно, вам всё равно придется указать ссылку на архив с майнером, при настройке Полетного Листа.

### Настройка Полетного Листа
Мы описали процесс создания Полетных Листов и кошельков в одной из наших [предыдущих статей](https://hiveos.farm/getting_started-start_dashboard_setup_ru). Сейчас мы не будем вдаваться в подробности, предполагая, что вы уже знаете, как это делать.

Перейдите во вкладку **Flight Sheets** на панели управления вашей фермы. В разделе **Add New Flight Sheet**, начните заполнять следующие поля:

* __Flight Sheet Name__ — используйте имя, которое лучше всего опишет цель Полетного Листа. Например, _ETH on nanopool using claymore_; _flypool zcash on dstm_; и так далее.
* __Coin__ — это работает, как фильтр, вы можете видеть кошельки, пулы и майнеры только для выбранной монеты. Например, если вы выбрали ETH, фильтр скроет все ранее созданные кошельки и пулы, которые не поддерживают или не связаны с данной монетой.
* __Wallet__ — выберите кошелек для вашего Полетного Листа (из кошельков, которые вы ранее создали во вкладке Wallets).
* __Pool__ — выберите **Configure in miner**, чтобы в поле **Miner** появилась опция кастомного майнера.
* __Miner__ — выберите **Custom** и затем кликните **Setup Miner Config** для специфических настроек майнера. Затем заполните необходимые поля. Учтите, что у каждого майнера разный набор параметров и требуемых полей.

Так как мы настраиваем кастомный майнер, необходимо вручную настроить эти параметры через окно **Setup Miner Config**. Нажмите на кнопку **Setup Miner Config** в **Miner** и заполните следующие поля:

* __Miner name__ — используйте название архива. Например, если архив называется `phoenixminer-3.5_c.tar.gz`, майнер **должен** называть `phoenixminer`.
* __Installation URL__ — скопируйте прямую ссылку на нужный майнер из списка майнеров HIVE OS.
* __Hash algorithm__ — выберите алгоритм для майнера из списка, если он там есть. Если нет — не выбирайте.
* __Wallet and worker template__ — это будет зависеть от специфических настроек майнера. Но, скорее всего, как минимум `%WAL%` вам надо будет вписать.
* __Pool URL__ — адрес пула, а также его специфические настройки (пароли, кошельки и порты). Учтите, что мы рекомендуем вводить значения в следующем формате: `WALLET: %WAL%, WORKER:%WORKER_NAME%`. Также, все значения должны быть разделены запятой.
* __Pass__ — пароль. `x` как настройка по умолчанию, обычно её оставляют, как есть. Иногда указывается тикер монеты, если на пуле, на одном алгоритме, монет много. Иногда указывается порог выплат. Зависит от настроек и возможностей пула.
* __Extra config arguments__ — специфические настройка майнера (опционально). Учтите, что в некоторых случаях они могут быть важны, так что мы рекомендуем ознакомиться с документацией вашего майнера для получения дополнительной информации.
* Нажмите **Apply Changes**, и всё.

Когда вы закончите, нажмите на кнопку **Create Flight Sheet**. Теперь вы можете применить созданный Полетный Лист.

#### Пример: как установить и настроить Phoenix Miner на HIVE OS?
Мы показали вам, как настроить кастомный майнер, теперь пришло время применить знания на практике. В качестве примера, мы объясним, как установить и настроить сторонний майнер Phoenix Miner 3.5c на <a href="https://www.hiveon.net/"> пуле Hiveon</a> с использованием алгоритма ethash.

<img src="https://lbd.hiveos.farm/kbase/images/start_custom_miner/custom_fs.gif" />

_Полетный Лист кастомного майнера_

В разделе **Add New Flight Sheet**, начните заполнять следующие поля:

* __Coin__ — _ETH_
* __Wallet__ — _Example ETH_ (ранее созданный для примера кошелек).
* __Pool__ — выберите **Configure in miner**, чтобы в поле **Miner** появилась опция кастомного майнера.
* __Miner__ — выберите **Custom** и затем кликните **Setup Miner Config** для специфических настроек майнера. Затем заполните необходимые поля. Учтите, что у каждого майнера разный набор параметров и требуемых полей.
* __Flight Sheet Name__ — _Phoenix on Hiveon_

<img src="https://lbd.hiveos.farm/kbase/images/start_custom_miner/custom_conf.gif" />

_Конфигурация кастомного майнера_

Теперь нам нужно настроить майнер. Нажмите на кнопку **Setup Miner Config** в **Miner** и заполните следующие поля:

* __Miner name__ — в данном случае `phoenixminer`
* __Installation URL__ — добавьте URL архива `http://download.hiveos.farm/custom/phoenixminer-3.5_c.tar.gz`
* __Hash algorithm__ — выберите `ethash` из выпадающего списка.
* __Wallet and worker template__ — `null`, так как мы используем уже имеющийся ETH кошелек.
* __Pool URL__ — мы будем использовать <a href="https://www.hiveon.net/"> пул Hiveon</a>, так что нужны следующие параметры:

`POOL: eu-eth.hiveon.net:4444, WALLET: %WAL%, WORKER:%WORKER_NAME%`

`POOL: eu-eth.hiveon.net:14444, WALLET: %WAL%, WORKER:%WORKER_NAME%`

* __Pass__ — выбираем `x`
* __Extra config arguments__ — в нашем случае, мы оставляем это поле пустым.
* Нажимаем **Apply Changes**, и всё готово.

### Как создать свой собственный архив?
Hive 2.0 поддерживает кастомные майнеры, которые вы "создаете" сами. Вам нужно будет применить несколько простых скриптов, чтобы заставить ваш майнер работать и отправлять статистику в Hive. Пожалуйста, используйте следующее в качестве отправной точки:


Интеграционный документ находится <a href="https://github.com/minershive/hiveos-linux/blob/master/hive/miners/custom/README.md">здесь</a>. Чтобы установить кастомный архив вручную, вы можете просто распаковать его в `/hive/miners/custom`.

Чтобы установить его с URL, запустите `/hive/miners/custom/custom-get url-на-ваш-майнер`. Используйте аргумент “-f” в конце для переустановки: `/hive/miners/custom/custom-get url-на-ваш-майнер -f`. Начиная с v0.6, для обновления кастомного майнера достаточно сменить URL в вашем Полетном Листе на новую.
