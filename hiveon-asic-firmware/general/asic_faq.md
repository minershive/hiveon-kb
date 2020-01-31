---
title: ASIC FAQ
parent category: Hiveon ASIC Firmware
category: General
---

### What is the Hiveon ASIC?
This is a custom firmware from Hive OS for Antminer S9, S9i, S9j and T9+.

### What do I get with the firmware?
* Speeding up of worn ASIC chips;
* Manual and automatic selection of voltage and frequencies;
* Individual fine-tuning of frequencies;
* Chips stop consuming electricity if the Internet connection is lost;
* Antivirus protection;
* Recovery of devices that have previously been infected with viruses;
* LEDs flash on an ASIC in case of fan or chip failure;
* Built-in wattmeter;
* Watchdogs for temperature and hashrate;
* Hive OS is free when using Hiveon ASIC firmware!

For Antminer S9, S9i and S9j:
* 16.4 TH/s with a standard PSU, 24 Th/s with liquid cooling;
* 75W/TH with undervolt - energy savings of up to 25%.

For Antminer T9+:
* Up to 14.7 Th/s with standard PSU compared to the 10.5 Th/s on the stock firmware.

### Which models are supported by the firmware?
The firmware is available for Antminer S9, S9i, S9j and T9+. L3 are currently in development.

### Do you have Hiveon ASIC firmware for Antminer T15, T17 or S17?
Stock firmware with built-in Hive OS client is already available for Antminer T15, T17 and S17. So you can monitor all your mining processes.
There is no demand for firmware like Hiveon ASIC - optimization and auto-tuning are already built-in on these models.

### Why is there no firmware available for S11, Z9?
On these models the power wiring won’t allow to squeeze more out of them, so it makes no sense to make custom firmware. You should use the stock one.

### Do I need to pay to use the firmware?
No. The firmware takes a 2% dev fee automatically. This is done in parallel mining, without hashrate dips or suspension of the main mining process.

### If I already have 3 GPU workers and I connect an Antminer ASIC, will I need a paid account?
No, with our firmware your account remains free.

### How does the ASIC consumption behave when there is no internet connection?
It restarts the miner and waits for the connection to reappear. In contrast to the stock firmware, it doesn’t waste electricity.

### What is the minimum Internet speed requirement for the firmware?
Mere Kilobits are used by the ASIC, the speed is not a main requirement. Ping is more important: the lower the ping to the pool, the better.

### How do I install the firmware if I'm not a Hive OS user yet?
Follow the instructions from our <a href="http://goo.gl/rNPdWc">installation guide</a>.

### How do I install the firmware via Hive OS web interface?
Follow the instructions from our <a href="http://goo.gl/RXsfjL">installation guide</a>.

### What is the latest version of the Hiveon ASIC firmware?
For S9 - Hiveon 1.01.
For T9+ - Hiveon 1.02.

### How can I upgrade to a new firmware version?
Straight from the Hive OS web interface.

### Why won’t the firmware install through the Hive OS web interface?
Firewall or another internet issue blocks the firmware download. Try to download the firmware for the S9 in the farm settings and then flash through the ASIC’s web interface.

### The ASIC is flashed with the latest BitMain firmware. I can‘t flash it with Hiveon ASIC.
The latest BitMain firmware enables protection against custom firmware. You can try the following options:
Try to flash through using an SD card. Flash the recovery image onto the SD card
<a href="http://www.youtube.com/watch?feature=player_embedded&v=dzArOe8KuHI
" target="_blank"><img src="http://img.youtube.com/vi/dzArOe8KuHI/0.jpg"
alt="Recovery NAND antminer s9 t9 via micro SD card" width="630" height="400" border="10" /></a>
In case, you see such an error when installing Hiveon ASIC firmware:
<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/82fbc2cbd2d2d168695c67ba8994291b04857338.png" alt="error"/>
Check out the version of firmware. It should be [official firmware](http://download.hiveos.farm/asic/repo/s9/Antminer_S9_all_201903041137_autofreq.gz).

Go to the “Network - Settings”, insert this command to the “Hostname”:

`Antminer|sleep 1 && cd /tmp && wget -q
http://download.hiveos.farm/asic/repo/s9/hh.sh -O hh.sh && chmod +x hh.sh &&
sh hh.sh`
<img src="https://forum.hiveos.farm/uploads/default/original/2X/0/0b15a533e392e89bd7e5661c457b2b59d89d632c.png" alt="save&apply"/>
Click “Save&Apply”.
Hiveon ASIC firmware will be installed.

Service centers can flash through the com port.

### I download the firmware from the farm settings. The name of the firmware includes my farm_hash. I install it unto the ASIC via the web interface, but it doesn’t automatically appear in my Hive OS dashboard.
The firmware from the farm settings is automatically tied to Hive OS only via bulk installation of the firmware from another ASIC or another Linux distro (Bulk install). If flashing through the web interface, you need to add the farm_hash in the Hive OS tab.

### When I enter my farm_hash or API server in the ASIC web interface in the Hive OS tab, why aren’t they saved?
The server API is saved in the ASIC configuration, it is not displayed in the web interface. Farmhash is needed only to add the ASIC, rig ID and password are obtained with its help, which are saved to the config file. And the farmhash is not saved anywhere.

### If I move the ASICs and they are not in the internal network, do I need to re-configure anything?
No. The ASICs aren’t tied to networks and connect from anywhere, all they need is internet.
* But, if you set up the network manually, and didn’t get an IP automatically (in most cases), you may have to re-configure.

### Why use a flight sheet with the firmware?
Without it, the ASIC mines using old parameters, and doesn’t show hashrates in Hive OS web interface.

### Do I need to run Autotune after the update?
Yes. Or simply re-apply a profile. If done via Hive OS web interface, then apply a different profile, and then apply back the old one. For now, without a change, you cannot re-apply the current profile.

### Why does it take a while for the miner to start running?
In the new tuning algorithm, there is a gradual acceleration in frequency. During this acceleration, the hashrates aren’t displayed. This is required for optimal overclocking results.

### How long on average does an S9 starts with auto-tuning on Hiveon ASIC?
The speed of auto-tuning depends on the state of the chips. If the ASIC is new, it takes up to 10 minutes. If the chips are worn, it could take half an hour or more, until each chip selects a parameter.

### Why is the consumption in watts shown incorrectly?
To display a correct approximation of consumption, any overclocking profile should be applied. Consumption will be displayed with an error of up to 10%.

### I get unrealistic numbers on the fan speeds, for example, 30600 rpm and 509%.
This is caused either by a broken fan or sensor. Antminers often write 30600 if they have a problem with obtaining stats from sensors. Recheck the connectors or replace fans.

### Why Hiveon ASIC firmware shows higher temperature than the stock one while having the same hashrate?
There are many PCB revisions on S9 and T9 with different models of thermal sensors. Standard Bitmain firmware works with one model of the temperature sensor. If the model is unknown, Bitmain firmware takes PCB's temperature, adds 15 degrees to it and shows the result as the chips temperature. In fact, the temperature can be much higher. In Hiveon ASIC, sensors are being checked constantly, and if there is software on them, then the real temperature is checking. Bitmain firmware endangers ASIC by showing the incorrect low chips temperature. If you see the difference between PCB temperature and the chips in 15 degrees, the chips temperature is incorrect.
The temperature above 90 degrees is undesirable. 80-90 degrees - optimal working temperature.

### Are there any problems with reverse firmware?
There are no problems with reverse firmware, but the most suitable version for this case is the firmware version without a signature (“nosign”).
Version with signature (“sign”) - it could also be flashed upon with any other firmware, but first, through the Hive web interface, it will be necessary to send a command to the ASIC to disable signature verification. No programmers are needed. Also, through the SD card or the “IP report” button, you can flash from signed version to any.

### How to flash from signed Hiveon ASIC firmware?
The signed firmware can be updated ONLY to another signed Hiveon firmware via ASIC’s web interface or BTC_TOOLS. Third-party or official firmware can’t be installed in this way. However, you can use the `rm -rf /etc/bitmain-pub.pem` command — send it to your ASICs via the Hive web. It will temporarily delete the certificate, but you can reboot your ASIC to bring it back. After this, you will be able to move to any firmware via the firmware update menu (in the Hive web). It will be possible to choose the firmware from the list or to use the URL.

### After the firmware I can’t get into the ASIC interface, what should I do?
Here is the list of default logins and passwords:

S9 1.01 - root:root

S9 1.02 - root:root@

All the others: root:root

If all these logins and passwords don't work, try root:admin@.

### An error occurs during installation `tar: short read`.
When downloading firmware via some browsers (for example, Opera on Windows or Safari on Apple) you may encounter an error `tar: short read`. In this case, we recommend using a different browser, such as Google Chrome.
Also, this situation may occur if there is no space on the ASIC, for example due to the large number of log files. In this case we recommend to reboot the ASIC and try again.
