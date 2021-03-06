---
title: Ваш IP
parent_category: Гайды
path: /guides-yourip_ru
lang: ru
parent_category_path: /guides_ru
order: 1
meta_description: Узнайте больше о внутренних и внешних IP-адресах.
---

После подключения рига в веб-панели будут указаны как минимум два IP-адреса.
Первый - это ваш внутренний IP. В вашей внутренней сети вы можете получить к нему доступ только через локальную сеть. Второй - это внешний IP (как именно сервер видит клиента). Если все ваши риги подключены к одному и тому же роутеру, у них будет одинаковый внешний IP.

Другие IP-адреса, такие как IPv6 или VPN, также будут перечислены на веб-панели.

При загрузке вы можете определить назначенный вашему ригу IP-адрес. Позже, при загрузке, он также будет отображаться при входе в систему.

Чтобы проверить интерфейс вашей сети, запустите команду `ifconfig`. Результат будет таким:

<pre><code>
root@worker:~# ifconfig
eth0      Link encap:Ethernet  HWaddr 88:d7:f6:c7:51:db  
          inet addr:192.168.0.188  Bcast:192.168.0.255  Mask:255.255.255.0
          inet6 addr: fe80::8ad7:f6ff:fec7:51db/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:209463 errors:0 dropped:18 overruns:0 frame:0
          TX packets:186047 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:56751586 (56.7 MB)  TX bytes:27763156 (27.7 MB)
</code></pre>

Таким образом, вы можете проверить назначенный адрес DHCP.
