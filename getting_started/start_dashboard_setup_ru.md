---
title: Панель управления
parent_category: Начало Работы
path: /getting_started-start_dashboard_setup_ru
lang: ru
parent_category_path: /getting_started_ru
order: 1
meta_description: Узнайте, как работать с фермами, настраивать кошельки, создавать полетные листы, выбирать серверы пула и настраивать майнер.
---

В нашей [предыдущей статье](https://hiveos.farm/getting_started-start_worker_setup_ru) мы обсудили установку и настройку воркеров. Теперь же мы продолжим знакомить вас с Hive и покажем, как работать с её основными функциями. Начнем с ферм.

## Работа с фермами
Ферма - это группа воркеров, объединенных для создания отдельного проекта. Проще говоря, у вас может быть отдельная ферма для всех ваших воркеров, или же вы можете создать несколько ферм для разных групп воркеров в одном локации, например, в центре обработки данных (скажем, _"1st floor rigs"_, _"2nd floor rigs"_, _"rigs on East str"_, и так далее). Количество ферм на одну учетную запись не ограничено. Это относится как к вашей ферме, так и к тем, доступ к которым был предоставлен вам другими пользователями. Другие пользователи могут предоставлять доступ к своим фермам или даже полностью передавать их между учетными записями. Таким образом, можно легко настроить целую ферму для клиента, а затем передать полную собственность на его учетную запись. Вы даже можете организовать свой собственный бизнес по настройке ферм, если хотите.

### Создание фермы
Нажмите на значок "плюс" в верхнем правом углу панели управления. Появится окно **Create New Farm**. Дайте вашей ферме имя и выберите вашу временную зону. Это должна быть временная зона, в которой будут раположены ваши воркеры. Это необходимо для отображения правильных временных кодов журнала. Как только вы закончите, нажмите на кнопку **Save** - вы будете перенаправлены на панель управления вашей новой фермы.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/create_farm.gif" />

_Создание новое фермы_

### Уровни доступа фермы
Существует несколько уровней доступа к ферме. Вы можете увидеть их в нижней части каждой фермы на панели управления.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/farms_access.png" />

_Список ферм (ваших собственных и тех, к которым у вас есть доступ)_

Вы можете предоставить другим пользователям доступ к вашей ферме. Например, вы можете предоставить привилегии полного доступа своим администраторам, чтобы они могли управлять всем, что у вас есть. Или же вы можете дать доступ только на чтение и предоставить его вашему техническому персоналу, который выполняет простое обслуживание и мониторинг и ничего более.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/add_user.gif" />

_Предоставление доступа к ферме другому пользователю_

Каждый следующий уровень включает в себя разрешения предыдущего.

* __Monitor__ — Мониторинг и статистика, информация о риге. Теги могут быть назначены для ограничения видимости ригов для доверенного аккаунта.
* __Tech__ — Разгон, перезагрузка и выключение, обновление.
* __Rocket__ — Применение майнера и кошелька к воркеру. Создание и удаление воркеров.
* __Advanced__ — Выполнение команд, VPN, кошельки, настройка.
* __Full Access__ — пароль, двухфакторная аутентификация, уведомления, платежи, право собственности.

Чтобы предоставить другому пользователю доступ к своей ферме, перейдите во вкладку **Farm**, а затем в **Access**. Вы увидите сообщение “_No users found so far. You can create one_”. Нажмите кнопку **create one** или же кнопку **Trust user**. Введите логин пользователя (это должен быть логин Hive). Выберите уровень доступа из выпадающего меню. Если вы выберете уровень Monitor level, появится дополнительно поле **Tags** will be available. Вы можете дать доступ только к воркерам с выбранными тегами, чтобы ограничить видимость других воркеров.

### Настройка кошельков
Теперь, когда вы познакомились с фермами поближе, вы можете приступить к настройке кошельков. Вы можете создать несколько кошельков для любой монеты, которая вам нравится. По факту, если вы планируете майнить несколько монет, мы рекомендуем создать разные кошельки, которые вы сможете потом привязать к разным майнерам и разным пулам. При выборе монеты для майнинга в Полетных Листах, вы увидите, что в зависимости от выбранной монеты, выбор кошельков будет ограничен этой конкретной монетой.

Чтобы добавить новый кошелек, перейдите во вкладку **Wallets** и нажмите кнопку **Add Wallet**. Вы увидите всплывающее окно со следующими полями:

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/new_wallet.gif" />

_Создание нового кошелька_

* __Coin__ — выберите монету для кошелька из выпадающего списка.
* __Address__ — введите адрес вашего кошелька.
* __Name__ — введите имя, которое лучше всего отразит цель кошелька. Например, _Ethereum on Claymore_, _ZEC on CCminer_, а так далее.
* Нажмите **Create**, чтобы сохранить ваш новый кошелек.

Когда вы закончите создавать кошельки, перейдите во вкладку **Flight Sheets**.

### Настройка Полетных Листов
Полетные Листы (Flight Sheets) - это файлы конфигурации вашего воркера, которые определяют его режим работы. Полетные Листы позволяют вам создавать предварительные настройки воркеров и переключаться между ними "на лету", буквально за несколько кликов. Вы можете создать несколько комбинаций монет, кошельков, пулов и майнеров, и переключаться между ними практически мгновенно.

При добавлении нового Полетного Листа, обратите внимание, что сначала вы можете выбрать только монету. Другие опции в это время будут выделены серым цветом. Это сделано для вашего удобства. Когда вы выберете монету, вы сможете выбрать кошелек из списка ранее созданных кошельков, который вы добавили заранее. Выбор кошельков также будет ограничен теми, которые связаны с ранее выбранной монетой. То же касается пулов и майнеров, вы можете видеть только те, которые связаны с этой конкретной монетой.

### Создание Полетного Листа

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/new_fs.gif" />

_Настройка нового Полетного Листа_

Начните заполнять следующие поля в секции **Add New Flight Sheet**:

* __Flight Sheet Name__ — используйте имя, которое лучше всего опишет цель вашего Полетного Листа. Например, _ETH on nanopool using claymore_; _flypool zcash on dstm_; и так далее.
* __Coin__ — это работает как фильтр, вы можете увидеть кошельки, пулы и майнеры только для выбранной монеты. Например, если вы выбрали ETH, фильтр спрячет все ранее созданные кошельки и пулы, которые не поддерживают или не связаны с этой монетой.
* __Wallet__ — выберите кошелек для вашего Полетного Листа. Здесь будут кошельки, которые вы создали во вкладке **Wallets**.
* __Pool__ — пул, на котором вы будете майнить. Выберите пул из выпадающего списка. Появится всплывающее окно с настройками. Вы также сможете изменить эти настройки позже, нажав **Configure Pool**.
* __Select Pool Server__ — список доступных серверов пула.
* __Email__ — email вашей учетной записи пула. Эта опция доступна на некоторых пулах, которые аутентифицируют пользователей по электронной почте, у других данной настройки может не быть.
* __Miner__ — выберите майнер, который будет использован для данного Полетного Листа. Нажмите на **Setup Miner Config** для конкретных настроек майнера. Вам следует ознакомиться с документацией вашего майнера для получения дополнительной информации.

Как только вы закончите, нажмите кнопку **Create Flight Sheet**.

## Выбор серверов пула
В отношении пулов следует отметить порядок, в котором вы выбираете серверы. Давайте используем **dwarfpool** как пример и предположим, что вы выбираете европейский сервер. Следующие серверы, которые вы выбираете - это следующие серверы, к которым ваш воркер присоединится, если он потеряет связь с европейским (в том же порядке, в котором вы их выбрали). Например, первым вы выбрали европейский сервер, потом - Россию, а затем - Китай. Это точный порядок очередности, в котором ваш воркер присоединится к данному пулу.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/pool_conf.gif" />

_Выбор серверов пула_

### Настройка конфигурации майнера
Окно конфигурации майнера будет меняться в зависимости от выбранного вами майнера. Как упоминалось ранее, выбор майнеров ограничен выбранной монетой. У майнеров будет текст Nvidia, AMD или CPU, указывающий его совместимость с конкретными типами оборудования. Это означает, что если у майнера есть только Nvidia, то он будет работать только на графических процессорах Nvidia, то же самое с AMD и наоборот. CPU указывает, что майнер может быть запущен на CPU.

Эти параметры можно оставить в покое, и майнер будет работать с настройками по умолчанию. Вы можете изменить их. Если, например, серверы пула не были выбраны на вкладке **Pool**, тогда эти настройки можно установить в конфигурации майнера. Это поля кастомных настроек, которые можно использовать для переопределения специфических параметров, таких как форки, адрес пула, строки кошелька или параметры переопределения конфигурации оборудования. Мы рекомендуем обратиться к документации вашего майнера для получения более подробной информации.

Как только вы закончите, нажмите кнопку **Create Flight Sheet**. Помните, что на вашей ферме может быть любое количество Полетных Листов.

### Пример: Настройка Monero на Nicehash
Теперь, когда мы показали вам, как настроить ваш воркер, давайте применим знания на практике и настроим Monero (XMR) на Nicehash используя майнинг-алгоритм CryptoNoghtv7 как пример.

Перейдите в ваши **Wallets** и нажмите на кнопку **Add Wallet**. В окне **New Wallet**, начните печатить `nicehash` в поле **Coin**, и вы увидите полный список алгоритмов, поддерживаемых Nicehash. Они не перечислены по умолчанию в выпадающем списке, поскольку они не являются реальными монетами как таковыми.
Выберите протокол _Nicehash-CryptoNightV7_, адрес вашего кошелька Nicehash. Заметьте, что если вы хотите увидеть свою статистику в <a href="https://www.nicehash.com/dashboard">Nicehash Dashboard</a>, вам следует использовать сгенерированный адрес кошелька, полученные при <a href="https://www.nicehash.com/register">регистрации</a>. Вы можете дать имя вашему новому кошельку, затем нажмите **Create**.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/wallet_nh.gif" />

Для продолжения, настройте Полетный Лист во вкладке **Flight Sheets**. Выберите теперь доступный _Nicehash-CryptoNight_ из выпадающего списка **Coin**, затем выберите только что созданный кошелек, и выберите пул. Обратите внимание, что вы можете выбрать сервера пула по умолчанию или же выбрать опцию **Configure in miner**, чтобы настроить все вручную. Выберите майнер или, если вы предпочли опцию _Configure in miner_, настройте этот майнер вручную, нажав на кнопку **Setup Miner Config**.

Ниже приведен пример того, как мы настроили наш второй майнер для CPU-майнинга на риге. Ваши настройки могут различаться в зависимости от выбранного вами майнера, серверов, алгоритмов, монет и т.д. Но для этого примера мы решили майнить Monero (XMR), используя CPU нашего рига. У нас уже есть майнер GPU, поэтому нам нужно было добавить наш CPU майнер в тот же Полетный Лист. Мы сделали это только на одном из наших воркеров, создав таким образов конкретную конфигурацию рига.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/nh_monero_fs.gif" />

_Добавление второго майнера_

Чтобы добавить второй майнер к конкретному воркеру, перейдите к этому воркеру и нажмите на вкладку **Flight Sheet**, затем выберите ваш текущий Полетный Лист, нажмите на кнопку с троеточием, и затем - **Edit**. Нажмите на **Add Miner** и начните заполнять поля:

* __Coin__ — Nicehash-CryptoNightV7
* __Wallet__ — кошелек, который мы создали, используя наш адрес депозита Nicehash
* __Pool__ — Настроить в майнере
* __Miner__ — мы выбрали `cpuminer-opt`

Так как мы решили выбрать наш сервер и настройки майнера вручную, нам нужно настроить эти параметры при помощи окна **Setup Miner Config**. Нажмите кнопку **Setup Miner Config** в **Miner**, и заполните следующие поля:

* __Hash algorithm__ — выберите `cryptonightv7 — Monero (XMR)` из выпадающего списка
* __Wallet and worker template__ — `%WAL%.%WORKER_NAME%:x` эти шаблонные параметры будут заменены автоматически, так что мы оставляем их, как есть
* __Pool URL__ — `stratum+tcp://cryptonight.eu.nicehash.com:3355` наш выбор сервера
* __Pass__ — `x` настройка по умолчанию, оставлена, как есть
* __Config override__ — `“threads”: 4 “cpu-affinity”: 0`

Обратите внимание, что количество потоков будет варьироваться в зависимости от количества ядер вашего CPU. В нашем случае это 4. Обычно, **Config override** может быть оставлено пустым в большинстве случаев.

* Нажмите __Apply Changes__, и всё.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/miner_conf.gif" />

_Настройка конфигурации майнера_

Для получения более подробной информации о Nicehash и его настройке, пожалуйста, обратитесь к их <a href="https://www.nicehash.com/help">разделу помощи</a>.

Продолжайте следовать приведенным ниже инструкциям, чтобы применить вновь созданный Полетный Лист к вашему воркеру.

## Начните майнить
Теперь вы можете применить созданный вами Полетный Лист. У вас есть два варианта применения Полетного Листа к вашему воркеру. Первый: перейдите во вкладку **Workers**, затем выберите конкретный воркер, перейдите во вкладку **Flight Sheet** в меню воркера и нажмите на кнопку в виде ракеты с правой стороны того Полетного Листа, который вы хотите применить.

Второй вариант: перейдите во вкладку **Workers**, затем установите "флажки" с левой стороны воркеров, к которым вы хотите применить Полетный Лист. Вы должны увидеть иконку с ракетой в строке меню в верхнем правом углу.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/cp.png" />

_Контрольная панель_

Кликните на неё, и увидите окно с количеством выбранных воркеров и список всех ваших Полетных Листов.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/launch_fs.png" />

_Список выбранных воркеров и доступных Полетных Листов_

Выберите Полетный Лист, который вы хотите применить, затем нажмите кнопку **Apply**. Вы должны увидеть сообщение о том, что команда Flight Sheet была отправлена на воркер. Через несколько секунд ваши воркеры должны применить изменения, и вы должны увидеть сообщение `Config applied` в журналах активности во вкладке **Overview** вашей фермы.

<img src="https://lbd.hiveos.farm/kbase/images/start_dashboard_setup/activity_log.png" />

_Журналы активности фермы_

Вы справились! Ваш риг должен начать майнить, отправив данные на вашу панель управления. Теперь вы должны видеть его показатели в режиме реального времени.
