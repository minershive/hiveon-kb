---
title: OpenVPN
parent_category: Гайды
path: /guides-openvpn_ru
lang: ru
parent_category_path: /guides_ru
order: 1
meta_description: Узнайте, как установить и настроить OpenVPN.
---

### Руководство №1
Вот как проверить статус сервиса клиента на риге, когда вы загружаете конфигурацию, а она не работает:
<pre><code>
systemctl status openvpn@client
journalctl -u openvpn@client -e --no-pager -n 100
</code></pre>

Вот пример работающей конфигурации:
`/etc/openvpn/server.conf`
<pre><code>
port 1194
proto udp
dev tun
ca ca.crt
cert myservername.crt
key myservername.key
dh dh2048.pem
topology subnet
server 10.4.0.0 255.255.255.0
ifconfig-pool-persist ipp.txt
client-config-dir ccd
client-to-client
keepalive 10 120
comp-lzo
persist-key
persist-tun
status openvpn-status.log
log            openvpn.log
verb 3
</code></pre>
И самое важное - client.conf. Там должны быть файлы сертификатов.
<pre><code>
client
dev tun
proto udp
remote mysupermegaserver.com 1194
resolv-retry infinite
nobind
persist-key
persist-tun
ca ca.crt
cert client.crt
key client.key
remote-cert-tls server
comp-lzo
verb 3
</code></pre>
Обратите внимание, что в конфигурации сертификаты должны быть названы как в примере:

ca ca.crt

cert client.crt

key client.key

Вы можете загружать файлы с любыми именами, но тогда они будут переименованы в to ca.crt, client.crt, client.key. Таким образом, у вас будет одна конфигурация для всех ригов.

Также вы можете встроить свои сертификаты в один файл в client.conf, чтобы ваш файл выглядел так:

<pre><code>
client
dev tun
proto udp
remote mysupermegaserver.com 1194
resolv-retry infinite
nobind
persist-key
persist-tun
remote-cert-tls server
comp-lzo
verb 3

#No need for file names, comment or delete them
#ca ca.crt
#cert client.crt
#key client.key

<ca>
-----BEGIN CERTIFICATE-----
***Paste CA Cert Text Here***

-----END CERTIFICATE-----
</ca>

<cert>
-----BEGIN CERTIFICATE-----
***Paste Your Cert Text Here***

-----END CERTIFICATE-----
</cert>

<key>
-----BEGIN PRIVATE KEY-----
***Paste Your Cert Private Key Here***

-----END PRIVATE KEY-----
</key>
</code></pre>
Также, если вам нужен TLS Auth, вы можете встроить ключ таким образом:
<pre><code>
key-direction 1

<tls-auth>
-----BEGIN OpenVPN Static key V1-----
...tls key...
-----END OpenVPN Static key V1-----
</tls-auth>
</code></pre>
`auth-user-pass` сейчас также поддерживается. Так что просто установите эту опцию в конфигурации клиента и загрузите ее, указав логин и пароль в диалоге загрузки.

### Руководство №2
Прежде всего, вам нужен ПК или сервер, которому требуется фиксированный IP-адрес во внутренней сети (сети, в которой вы размещаете VPN-сервер). Помните, что весь VPN-трафик пойдет на компьютер с VPN-сервером, поступая от каждого VPN-клиента (от каждого из ваших ригов и от вашего персонального компьютера).

Мы предполагаем, что вы уже установили программное обеспечение VPN-сервера на ваш Windows или Linux. Обратите внимание, что установщики OpenVPN 2.4 не будут работать на Windows XP.


Если вы используете, к примеру, Debian, для установки OpenVPN достаточно напечатать: `apt-get install openvpn`.
Так вы получите пакет Debian OpenVPN, который вы будете использовать для настройки OpenVPN-сервера и генерирования ключей сервера и клиента.

Ссылки для скачивания OpenVPN и его ручной установки (на момент написания руководства):

Linux:
https://swupdate.openvpn.org/community/releases/openvpn-2.4.5.tar.gz

Windows:
https://swupdate.openvpn.org/community/releases/openvpn-install-2.4.5-I601.exe

### Настройка

Сначала нам нужно создать сертификат CA. Для этого используйте следующие команды:

Если вы используете Linux, BSD или операционную систему, подобную Unix, откройте командную оболочку и запустите команду `cd`, чтобы перейти в подкаталог easy-rsa. Если вы установили OpenVPN из RPM или DEB файла, подкаталог easy-rsa обычно можно найти в **/usr/share/doc/packages/openvpn** или **/usr/share/doc/openvpn**. Лучше всего скопировать этот подкаталог (например, в **/etc/openvpn**) ещё до изменений. Таким образом будущие обновления пакета OpenVPN не перепишут ваши модификации.
Если вы устанавливали из файла **.tar.gz**, подкаталог easy-rsa будет находиться в каталоге верхнего уровня развернутого исходного дерева..

В Debian, если вы выполнили `apt-get install openvpn`, запустите следующие команды:
<pre><code>
1:	make-cadir my_ca
2:	cd my_ca
3:	pico vars
</code></pre>
Если вы используете Windows, откройте окно командной строки и запустите команду `cd`, чтобы перейти в **\Program Files\OpenVPN\easy-rsa**. Запустите следующий пакетный файл, чтобы скопировать файлы конфигурации на место (это перезапишет все существующие файлы vars.bat и openssl.cnf): `init-config`.

Теперь отредактируйте файл vars (vars.bat в Windows / в Linux используйте команду `pico vars`) и настройте параметры KEY_COUNTRY, KEY_PROVINCE, KEY_CITY, KEY_ORG, и KEY_EMAIL. Не оставляйте пустым ни один из этих параметров:

`Set KEY_SIZE to “4096”`

Выйдите и сохраните файл vars.

В Debian, если вы выполнили `apt-get install openvpn`, запустите эту команду: `cp openssl-1.0.0.cnf openssl.cnf`.

Затем инициализируйте PKI.

На Linux/BSD/Unix:
<pre><code>
source ./vars
./clean-all
./build-ca
</code></pre>
На Windows:
<pre><code>
vars
clean-all
build-ca
</code></pre>
Далее, сгенерируем сертификат и приватный ключ для сервера.

На Linux/BSD/Unix: `./build-key-server server`.

На Windows: `build-key-server server`.

Как и на предыдущем шаге, большинство параметров могут быть по умолчанию. Когда запрашивается Common Name, введите «server». Два других запроса требуют положительных ответов ("y"): "Sign the certificate? [y/n]" и “1 out of 1 certificate requests certified, commit? [y/n]”.

Сгенерируйте сертификаты и ключи для 3 клиентов. Генерирование сертификатов клиента очень похоже на предыдущий шаг.

На Linux/BSD/Unix:
<pre><code>
./build-key client1
./build-key client2
./build-key client3
</code></pre>

На Windows:
<pre><code>
build-key client1
build-key client2
build-key client3
</code></pre>

Помните, что для каждого клиента обязательно нужно ввести соответствующее Common Name при появлении запроса, то есть "client1", "client2" или "client3". Всегда используйте уникальное общее имя для каждого клиента.

### Сгенерируйте параметры Diffie Hellman

Параметры Diffie Hellman должны быть сгенерированы для OpenVPN сервера.

На Linux/BSD/Unix: `./build-dh`

На Windows: `build-dh`

### Ключевые файлы

Теперь находим только что сгенерированные ключи и сертификаты в подкаталоге keys (my_ca/keys). Вот объяснение соответствующих файлов:

<img src="https://lbd.hiveos.farm/kbase/images/forum/jkzm45hrojam.jpg">

Финальный шаг в процессе генерации ключей - это копирование всех файлов на машины, которые в них нуждаются. Позаботьтесь о том, чтобы скопировать секретные файлы по безопасному каналу.

Выполните команду `su`, чтобы получить корневой доступ.

Выполните следующую команду, когда вы в каталоге **my_ca/keys**: `cp ca.crt server.key server.crt dh4096.pem /etc/openvpn/server/`.

Ваш файл server.conf будет размещен здесь (в Linux): **/etc/openvpn/server.conf**. Он будет выглядеть примерно так:
<pre><code>
port 1194
proto udp
dev tun
ca server/ca.crt
cert server/server.crt
key server/server.key
dh server/dh4096.pem
topology subnet
server 10.200.200.0 255.255.255.0
ifconfig-pool-persist ipp.txt
client-config-dir ccd
client-to-client
keepalive 10 120
comp-lzo
persist-key
persist-tun
status openvpn-status.log
log openvpn.log
verb 3
</code></pre>
Создайте файл server.conf в **/etc/openvpn/**, используя эту команду: `cat > server.conf`.

Затем скопируйте всю конфигурацию выше, в конце файла нажмите «CTRL-C» и «server.conf» будет создан.
Создайте следующий каталог: **mkdir / etc / openvpn / ccd**.

Запустите сервер OpenVPN в **/etc/openvpn/**:
`openvpn server.conf`

Ваш сервер OpenVPN должен заработать без ошибок.

Если вы использовали установку пакета Debian, OpenVPN сервер должен работать после загрузки и запуска. В других случаях и при ручной установке, вам нужно получить **openvpn server.conf** в initscript.

Для файла client.conf, вам нужно загрузить на сайт Hive OS:
<pre><code>
client
dev tun
proto udp
remote dyndns.name.here.org 1194
resolv-retry infinite
nobind
persist-key
persist-tun
remote-cert-tls server
comp-lzo
verb 3

<ca>
-----BEGIN CERTIFICATE-----
***Paste CA Cert Text Here***

-----END CERTIFICATE-----
</ca>

<cert>
-----BEGIN CERTIFICATE-----
***Paste Your Cert Text Here***

-----END CERTIFICATE-----
</cert>

<key>
-----BEGIN PRIVATE KEY-----
***Paste Your Cert Private Key Here***

-----END PRIVATE KEY-----
</key>
</code></pre>

"ca" это ваше содержимое "ca.crt", "cert" - ваше содержимое "client.crt", а "key" - ваше содержимое "client.key". Вам нужно скопировать и вставить содержимое каждого из этих файлов в те 3 поля.

Здесь, в строке **remote dyndns.name.here.org 1994**, если у вас динамический IP-адрес (лучше, если у вас есть сервис DynDns), получите динамический DNS, например **dyndns.name.here.org**, и установите его на вашем локальном маршрутизаторе в настройках DynDns, чтобы маршрутизатор автоматически обновлял ваш динамический IP-адрес.

Отредактируйте директиву remote, указав имя хоста/IP-адрес и номер порта сервера OpenVPN. Если ваш сервер OpenVPN будет работать на машине с одной сетевой картой за межсетевым экраном/NAT-шлюзом, используйте публичный IP-адрес шлюза, и номер порта, который вы настроили, чтобы шлюз перенаправлял на сервер OpenVPN.

Опять же, вот как проверить статус сервиса клиента на риге, когда вы загружаете конфигурацию, а она не работает:
<pre><code>
systemctl status openvpn@client
journalctl -u openvpn@client -e --no-pager -n 100
</code></pre>

Наконец, теперь вы можете установить и настроить наш клиент OpenVPN на нашем ПК или ноутбуке. Просто установите OpenVPN Client и используйте тот же файл client.conf, но переименуйте его в **hiveosvpn.ovpn**, если вы используете Microsoft Windows. Скопируйте его в установочный каталог OpenVPN в подкаталоге **\config\**, и доставьте его туда. Запустите клиент OpenVPN для Windows, и все готово. Подключитесь к серверу OpenVPN, и вы будете в той же сети, что и ваша удаленный риг.
