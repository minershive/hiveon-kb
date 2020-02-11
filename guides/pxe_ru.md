---
title: Hive OS Deploy PXE - Как Развернуть Сотни Ригов
parent_category: Гайды
path: /guides-pxe_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---

## Hive OS Deploy PXE - Как Развернуть Сотни Ригов

### Вступление
Если у вас есть большая ферма с сотнями или тысячами графических процессоров, и вы планируете перейти на Hive OS, в этом случае использование Hive OS Deploy PXE может значительно сократить время миграции и дать полный контроль над процессом развертывания.
Hive OS Deploy PXE использует технологию сетевой загрузки PXE для развертывания Hive OS на ваших ригах.

***Системные и аппаратные требования:***
- Операционная система: Ubuntu 16.04 (протестировано)
- 2х ядерный процессор
- Статический IP адрес и кабельный Ethernet
- Минимум 4 Гб ОЗУ
- Минимум 6 Гб свободного места на диске

Вы должны настроить DHCP-сервер, добавив параметр `next-server` со значением CLONEDEPLOY_SERVER_IP (статический IP-адрес хоста, на котором вы устанавливаете Hive OS Deploy PXE).
Подробнее читайте в разделе “Конфигурация сетевой инфраструктуры”.

### Конфигурация сетевой инфраструктуры
В зависимости от конфигурации вашей локальной сети риги (клиенты) в вашей сети получают IP-адреса и другую сопутствующую информацию либо динамически с использованием DHCP, либо статически настраиваются для каждого клиента.

#### Сеть с динамическими IP-адресами
Это случай по умолчанию или когда вы планируете настроить DHCP-сервер в любой точке вашей сети.
Обратите внимание, что вы должны предоставить набор параметров dhcp-options:

- dhcp-server ip address. Пример: 192.168.1.1
- dhcp addresses range ИЛИ network mask. Пример: 192.168.1.10-192.168.1.200 или 192.168.1.0/24
- dhcp broadcast address. Пример: 192.168.1.255
- gateway (также известный router в dnsmasq). Пример: 192.168.1.1
- tftp-root (your tftp folder for storing kernels, initrds, pxe configs and binaries). Пример: /tftp
- dhcp-boot (PXE загрузчик относительно tftp-root). Должен иметь значение `,,CLONEDEPLOY_SERVER_IP`
- dns-server
- next-server (dhcp option 66)

Примечание: Вы должны указать `next-server` с адресом компьютера на который установлен Hive OS Deploy PXE. Это единственная опция, которую вы должны определить, если у вас уже работает DHCP-сервер.
По умолчанию большинство маршрутизаторов имеют предопределенные параметры dhcp и возможность их изменять, поэтому необходимо указывать только параметр next-server.

#### Сеть со статическими IP-адресами
В случае статической сети вы должны сконфигурировать dhcp-сервер в любой точке вашей сети для использования технологии PXE. Например, вы можете использовать 'dnsmasq' - облегченный сервер DNS, DHCP и TFTP.

#### Примеры конфигурации DHCP
Смотрите примеры файлов конфигурации в папке 'examples /'
- dnsmasq: example/dnsmasq.conf
- dnsmasq: examples/same-server.dnsmasq.conf - установка dhcp и развертывание сервера на одном компьютере

### Установка сервера развертывания
#### Процедура установки
Все команды установки и сценарии в оболочке должны выполняться с правами суперпользователя с помощью команды `sudo`.

1. Скачайте установочный пакет
<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/52e02a72d9b8d5babff66da3b112baae0b79ee13.png">

2. Запустите установочный скрипт:
`./install-ubuntu.sh -f`

Он запустит процедуру установки, загрузив и установив необходимые пакеты.
Во время установки вы должны ответить на несколько вопросов.
Следуйте этим шагам:

3.1. Введите IP-адрес сервера развертывания в окне приглашения
<img src="https://forum.hiveos.farm/uploads/default/original/2X/6/6730de53d8ea8cde0c403457b3299f6ae6b7a65a.png">

Давайте предположим, что наш хост имеет IP-адрес 192.168.1.2, тогда вы увидите
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d75b793a77119422ff452fe7b6629c08705f7719.png">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/deeac25b5f9f1c44dfec0d8c9867298bbd767994.png">

3.2. Запросит строку подключения БД по умолчанию, нажмите «Enter»
<img src="https://forum.hiveos.farm/uploads/default/original/2X/e/e83165987e6f851d3fc79bdd2b85aca37997aa7c.png">

Настройки по умолчанию будут использоваться, если пользовательская БД не указана.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fb5ba087742d5fff6b9ec34d3e92fe2fbe9e7cd6.png">

3.3. Подождите, пока mysql сервер установится, а затем запросит пароль root по умолчанию с пустой строкой (нажмите Enter).
<img src="https://forum.hiveos.farm/uploads/default/original/2X/7/7546ec0f54e9b5dfb6fabab3c5048de23381d6a5.png">
^Этот экран может появляться несколько раз на этом этапе.

3.4. Введите SMB пароли для ролей только для чтения и чтения-записи: password
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d972d62fc0376240330a722fa450cecba502b0e9.png">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/985ac3cde5988de56e3c6ac2e154754dacc13176.png">

3.5. Скачайте и обновите образ Hive OS
Последний стабильный образ Hive OS будет загружен и извлечен по умолчанию.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/e/e633e65418cb2416432ec63daf9f60a19ba7c7c1.png">

3.6. Подождите, пока скрипт завершит установку, а затем подтвердите перезагрузку в окне приглашения, введя "y".

4. Следующие шаги выполняются через веб-интерфейс.
Перейдите по адресу http://<server_ip>/clonedeploy например, если ваш сервер имеет IP-адрес 192.168.1.2, введите в браузере http://192.168.1.2/clonedeploy, и вы увидите экран входа
<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/3/32a0de42f8fcbaa912e36c5ebf59805a59452882_2_444x375.png">

Войдите с учетными данными по умолчанию:

Логин: admin

Пароль: admin

5. Перейдите Admin → PXE и нажмите “Update PXE settings”

<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/831ef78884cc3c2b1d237a6ceb21703b4986a484.png">


<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/1/10c90048b8fb5730db6775aa7791c634838c7555_2_517x231.png">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c87da50269712077fe82e26ac23b7599f8c27081.png">

6. Перейдите Admin → “Boot menu” и нажмите “Create Boot Files”

<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/8f38172d6f16e9419aaaaddbaeb5a1f901157d7a.png">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d26760bdd46211032ba988e4233395d2f045820a.png">

7. Перейдите Groups → deploy → Computer Properties.
Измените следующие поля:

<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/5b2b0719d7e2b8816c6541eb51844110fcb7c3e4.png">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/f/f167942d86049e860c4de7801c9f4a0a240e191c.png"> <img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fba425df09795b391c701a76f25c67e383fd4b3c.png">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/529f1f5f58fc221b878286fa0dd71054172640ef.png">

1. Custom Attribute 2 - NETWORK. Введите вашу сеть с маской сети, например, '192.168.1.0/24'
2. Custom Attribute 3 - GATEWAY. Введите шлюз, например '192.168.1.1'
3. Custom Attribute 4 - HIVEOS_API. Введите hiveos-api url, например 'http://api.hiveos.farm'
4. Custom Attribute 5 - FARM_HASH. Введите Ваш Farm hash, например '0a188b553e98efba264e7bc61dee'

Примечание: Убедитесь, что флажки рядом с этими полями отмечены.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/e/e7c39f756392be548ae2cb793bcf1533c22af14f.png">

и нажмите кнопку “Update Properties”
<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/9566ee2525b1f086ae985e4b038fc9673d78bd3c.png">

На этом установка серверной части завершена.

#### Проверка установки
Сервер развертывания содержит несколько пакетов, включая dhcp proxy, apache2, mysql, tftpd-hpa.
Apache2 и MySQL - используется для веб-интерфейса, tftpd-hpa используется для TFTP сервера. Поэтому, если вы хотите проверить установку и убедиться, что эти службы работают правильно, используйте следующие команды:

for DHCP Proxy: `service cd_proxy status`

for Apache2: `service apache2 status`

for MySQL server: `service mysql status`

for TFTP server: `service tftpd-hpa status`

### Развертывание ригов
#### Подготовка к развертыванию
Вы можете организовать свою сеть в соответствии с определенными правилами.
1. Связать имя рига с MAC адресом
2. Связать имя рига с MAC адресом и IP адресом

Вы можете импортировать подготовленный список установок (см. Примеры в папке examples/clientlists)

Идем в “Computers”
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d9da23421b2deba27adc3dea1e8933a5bc852724.png">

Жмем “Import” и потом “Обзор”, указываем файл для импорта
<img src="https://forum.hiveos.farm/uploads/default/original/2X/7/7f7403e376f90869ab7ae3c65e956b99b6487c2f.png">

и нажать кнопку “Upload”
<img src="https://forum.hiveos.farm/uploads/default/original/2X/4/4802ecf0e60ac6621d7dd4222b5d265b79035153.png">

Формат файла (смотрите примеры в examples/clientlists) для привязки MAC+IP: rig-001	08:00:27:4A:29:BB	     192.168.1.19

Проверьте импортированные риги
<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/5/5c84be051b534751325b734d0225de39325b09e7_2_690x136.png">

#### Процесс развертывания
Нажмите “Task”
<img src="https://forum.hiveos.farm/uploads/default/original/2X/1/1274e00eff02e38e5662744a1ad2a34bb9a447d5.png">

потом “Click Computer Task” -> Start Computer Task -> выбрать риги для развертывания
<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c85a4496aaba2c7cf40514f583ec52fad44ba838.png">

и нажмите “Deploy Selected”.

Процесс развертывания на риге
<img src="https://forum.hiveos.farm/uploads/default/original/2X/a/a347dd139b206507452b7b5ed95b1a57564acc3e.png">

За прогрессом можно следить через браузер
<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c0c4b3960fa4f97391258d582c8e42cc30bc34ec.png">

После загрузки необходимых файлов Hive OS Deploy PXE запишет образ Hive на носитель
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/db5f35e1e311ace3ea82b3c78ffe17677c5a3a18.png">

После процесса перепрошивки, риг будет автоматически перезагружен, после чего при загрузке появится меню с целью по умолчанию «Boot To Local Machine», которая загрузит ваш риг после 5-секундной задержки.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/dbc4b559b3800af167b664b9c163ded17ab45ad1.png">

Когда процесс загрузки будет завершен, мы сможем увидеть наш риг в веб интерфейсе Hive.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/927242a593fae6d2743febcdd156509a6c6294dd.png">

### Приложение
- `install-ubuntu.sh` - скрипт для сценария установки Hive OS Deploy PXE
<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/8b755459accceb0687b5abf3a59c79ba7a17290b.png">

- `download.sh` - скрипт для загрузки образов на сервер Hive OS Deploy PXE
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d800f1615dc923d7f1feac51e79a093190026fe9.png">


- [Hive OS Deploy PXE репозиторий](https://git.tor.ph/hivedeploy/cd_package)
