---
title: Know your IP
---

## Know Your IP
In web panel there are 2 IPs at least listed once you connect your rig.

1st is you internal IP. In your internal network, you can access it only from your local network.
2nd is your external IP how the server is seeing a client. All your rigs will have the same external IP if they are behind the same router.

Other IPs like IPv6 or VPN will be also listed on the web panel.

When you boot you can spot assigned IP address to your rig. Later when you boot it’s also shown when you login.

To inspect you network interface you could run `ifconfig` and have a result like this:
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
In this way you could check DHCP assigned address.
