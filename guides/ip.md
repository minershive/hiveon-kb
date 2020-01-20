---
title: Static IP
---

## Static IP
This is very simple.

All network configs are here linked here:

/hive-config/network/20-ethernet.network

/hive-config/network/30-wireless.network

They are visible from Windows so you can edit them before you boot.

Sample config for static IP is like this:
<pre><code>
[Network]
DHCP=no
Address=192.168.0.189/24
Gateway=192.168.0.1
DNS=192.168.0.1
</code></pre>

In rare cases different MTU is required. Default is 1500. To change it add the following:
<pre><code>
[Link]
MTUBytes=1400
</code></pre>
