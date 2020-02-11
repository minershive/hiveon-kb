---
title: Статический IP
parent_category: Гайды
path: /guides-ip_ru
lang: ru
parent_category_path: /guides_ru
order: 1
---
## Статический IP
Здесь всё очень просто. Все сетевые настройки привязаны здесь:

/hive-config/network/20-ethernet.network

/hive-config/network/30-wireless.network

Они видны в Windows, так что вы можете редактировать их перед загрузкой.

Вот пример настройки статического IP-адреса:
<pre><code>
[Network]
DHCP=no
Address=192.168.0.189/24
Gateway=192.168.0.1
DNS=192.168.0.1
</code></pre>

В редких случаях может понадобится другой MTU (максимальный уровень передачи данных в сети). По умолчанию - 1500. Чтобы изменить его, добавьте следующее:

<pre><code>
[Link]
MTUBytes=1400
</code></pre>
