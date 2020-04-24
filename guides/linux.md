---
title: Linux Commands for Beginners
category: Guides
---

## Linux Commands for Beginners

### Simple Commands
`agent-screen` — show Hive client agent (you can exit from it with Ctrl+A, D)

`firstrun -f` — ask for rig ID and password again

`mc` — file manager like Norton Commander but for Linux

`selfupgrade` — upgrade from console, same as hitting a button on the web

`sreboot` — do a hard reboot

`sreboot shutdown` — hard shutdown

#### Miners
`miner` — show running miner screen (you can exit from it with Ctrl+A, D)

`miner start, miner stop` — start or stop currently configured miner obviously

`miner log, miner config` — selfexplaining

#### System Logs
`dmesg` — to see system messages, mainly to see boot log

`tail -n 100 /var/log/syslog` — to show last 100 lines from system log

#### Network
`ifconfig` — show network interfaces

`iwconfig` — show wireless adapters

### Keyboard Shortcuts
`Ctrl+C` — stop any running command

Switch miners screens, detach from terminal:

`Ctrl+A, D` — detach from screen (miner or agent) to leave it working

`Ctrl+A, Space or Ctrl+A, 1,2,3` — switch between screens if you have second miner running and so on

### Advanced Commands
#### Status / Diagnose
`agent-screen log` — show logs of various parts (you can try log1 and log2) of the Hive agent

`hello` — say hello to server: to refresh IP addresses, configs etc (normally it’s run at startup)

`net-test` — check and diagnose your network connection

`timedatectl` — show time and date synchronization settings

`top -b -n 1` — show list of all processes

`wd status` — show hashrate watchdog status and log

#### AMD
`amd-info` — show current frequencies for AMD cards

`amdcovc` — show current frequencies for AMD cards

`amdmeminfo` — show extended AMD cards info

`wolfamdctrl -i 0 --show-voltage` — show voltage table for AMD GPU #0

#### Nvidia
`journalctl -p err | grep NVRM` — show recent Nvidia GPU errors, if any

`nvidia-info` — show extended Nvidia cards info

`nvidia-driver-update 430` — download and install latest driver from series 430.*

`nvidia-driver-update --nvs` — reinstall nvidia-settings only

`nvidia-smi` — show Nvidia cards info

`nvtool --clocks` — show core/mem clocks for all the Nvidia GPUs

#### Hardware
`gpu-fans-find` — spin GPU fans from the first GPU to the last, make it easier to find the required GPU

`sensors` — show voltage/temperature readings of the motherboard and CPU

`sreboot wakealarm 120` — shutdown PSU and boot in 120 seconds

`/hive/opt/opendev/watchdog-opendev power` — send a power command to OpenDev watchdog

`/hive/opt/opendev/watchdog-opendev reset` — send a reset command to OpenDev watchdog

#### Upgrade / Install
`disk-expand -s` — expand a Linux partition to fill remaining drive space

`hpkg list miners` — list all installed miners

`hpkg remove miners` — uninstall all miners

`nvidia-driver-update` --remove — remove all downloaded Nvidia driver packages except currently installed

`selfupgrade --force` — force upgrade; it can help in situations when selfupgrade says Hive is up to date but actually it isn’t

#### Logs
`journalctl -u hive --no-pager` — show Hive service boot log

`journalctl -u hivex --no-pager` — show log of X server (graphical user interface)

`logs-on` — write all logs to disk, they will remain after reboots

`logs-off` — write all logs to RAM to reduсe USB flash drive wear (default)

`log='/var/log/syslog'; gzip -c9 "$log" | base64 -w 0 | message file "$(basename "$log")" payload` — send /var/log/syslog file to dashboard
