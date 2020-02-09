---
title: Watchdogs
category: Guides
---

## Watchdogs

### Videos
- <a href="https://www.youtube.com/watch?v=6wPnq1Is6mA">Hashrate Watchdog in Hive OS</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=6wPnq1Is6mA
" target="_blank"><img src="http://img.youtube.com/vi/6wPnq1Is6mA/0.jpg"
alt="Hashrate Watchdog in Hive OS"></a>

### SimpleRigResetter SRRv2 Watchdog
https://shop.simplemining.net/ssrv2.html?___SID=U

https://bitcointalk.org/index.php?topic=1695298.0

You need to create a file on the rig:
`/hive-config/watchdog_srrv2.txt`
<pre><code>
ENABLE=1

# Device serial number
SERIAL_NUMBER=1234

# The slot where this rig is connected, 1-8
SLOT_NUMBER=1

# Extension board serial if you have one
EB_SERIAL=

</code></pre>
After reboot please turn off windows client as it will send pings also.

### Chinese Watchdogs
The are a lot on Chinese watchdogs on the market. You can find them on Aliexpress or Ebay. They can come in different shapes and flavors but based on the same chip.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/9bfddcddf808f2d89c34ce558beaec77255c723c.jpeg">

<img src="https://forum.hiveos.farm/uploads/default/original/2X/b/b9e6090c9f33833ca3e4e3a3561590f9832a8071.jpeg">

To test reset you can run the following command after connecting it to your system: `hive/opt/qinheng/hl340 reset`

Run this command to check device ID: `lsusb`

Supported chips are:

- 1a86:7523
- 5131:2007
- 0471:2379

There is another kind of watchdog with the same ID but on Arduino Nano. It can’t be detected. To use it you need to run `/hive/opt/qinheng/wd-nano on`.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/6/60d77df72b177f246c71d5d7bdf8ef65ae170192.jpeg">

### OpenDev Watchdog
Supported watchdog https://open-dev.ru/watchdog.
You may just plug it in and that’s it. No configuration required.

You can check if it’s detected with the following command:

`$ journalctl -u hive -b0`

`Oct 28 23:37:55 worker hive[861]: > Detecting watchdogs`

`Oct 28 23:37:55 worker hive[861]: Watchdogs InUa found: 0`

`Oct 28 23:37:55 worker hive[861]: Watchdogs OpenDev found: 1`

**How to really test it:**

Disconnect wires from watchodog (or do not if you dare) and do the following: `/hive/opt/opendev/watchdog-opendev reset`.

Running this will send reset command: `/hive/opt/opendev/watchdog-opendev power`.

Pro version will consume this command also.
You should see LED blinking.
