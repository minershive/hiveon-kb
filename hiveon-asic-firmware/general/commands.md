---
title: Useful commands for ASICs on Hiveon firmware
path: /hiveon-asic-firmware-general-commands
parent_category: Hiveon ASIC Firmware
category: General
---

`self upgrade master` - ASIC agent update (internal software, not firmware).

`miner log all` - shows all the available logs combined and sorted by date and time.

`miner log watchdog` - shows the watchdog log.

`asic-oc retune` - runs the auto-tune of the selected ASIC on the current OC profile (overclock profile).

`asic-oc status` - shows completed OC profiles.

`asic-oc clear-cache` - erases all OC profiles (you need to start the auto-tune again).

`ntpdate pool.ntp.org` - time synchronization on ASIC and the server.

`have-passwd new_passwd -w` - change your password in the web interface (replace **new_pass** with your password)

`asic-find 5` - blinking diodes for 5 minutes to search for ASIC.

P.S.: Almost all the utilities can be run with the `--help` key to see their capabilities:

`self upgrade --help`

`miner --help`

`hive-passwd --help`

`asic-oc --help`
