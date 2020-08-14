---
title: Useful commands for ASICs on Hiveon firmware
path: /hiveon-asic-firmware-general-commands
parent_category: Hiveon ASIC Firmware
category: General
meta_description: Manage your devices nice and easy.
---

`selfupgrade master` - Hive OS Client for ASICs update (please do not confuse with ASIC firmware).

`miner log all` - shows all the available logs combined and sorted by date and time.

`miner log watchdog` - shows the watchdog log.

`asic-oc retune` - re-runs the autotune of the current OC profile (overclocking profile).

`asic-oc status` - lists actual OC profile (and cached too).

`asic-oc clear-cache` - erases all OC profiles (you have to start the autotune again).

`ntpdate pool.ntp.org` - date & time synchronization.

`have-passwd NEW_PASSWORD --web` - change of the password of the web interface (replace **NEW_PASSWORD** with your password)

`asic-find 5` - blinking LEDs for 5 minutes to search for ASIC.

P.S. Almost all the utilities can be run with the `--help` key to see their capabilities:

`selfupgrade --help`

`miner --help`

`hive-passwd --help`

`asic-oc --help`
