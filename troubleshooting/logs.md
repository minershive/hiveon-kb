---
title: Logs
---

## Logs

### Miner logs
The simple way: click the **Log** button under the Miner selection:

<img src="http://forum.hiveos.farm/uploads/editor/yr/nilcobp2yg17.png" >

You will get a response with the current screen of the miner. Click the **chat** icon near the **miner log** balloon:

<img src="http://forum.hiveos.farm/uploads/editor/t1/j1eymexf8r2o.jpg">

Actually this not a real log, it’s just a miner's screen. The real files are stored in /var/log/miner/xxxx/*.log.

So you open **mc** on the rig and go to **/var/log/miner/claymore** and find **lastrun_noappend.log** there.
<img src="http://forum.hiveos.farm/uploads/editor/r4/0z64iupn4v06.jpg">

You can have a look at the last 100 lines of it with a command like this:

`tail -n 100 /var/log/miner/claymore/lastrun_noappend.log.`

Logs are rotating with each miner restart, so there are lastrun_noappend.1.log, lastrun_noappend.2.log,...

### System logs
The main system log containing all the messages: `less /var/log/syslog`.

Hive starting logs from all boots: `journalctl -u hive`.

Hive X server (graphical interface) starting log. “-b0” is the option to show only the current boot. May be helpful inspecting X server problems. VNC server log is also there and you can inspect VNC access and logins: `journalctl -u hivex -b0`.

To show booting messages and current kernel or driver errors: `dmesg`.

Authentication logs. This command will show who had logged in via SSH: `cat /var/log/auth.log | grep "Accepted"`.

And sure there is Hive agent log, all communication with the server is there: `less /var/log/hive-agent.log`.
