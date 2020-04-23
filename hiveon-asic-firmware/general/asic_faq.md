---
title: ASICs and Hiveon ASIC Firmware FAQ
parent_category: Hiveon ASIC Firmware
category: General
---
## General questions
#### What is the Hiveon ASIC?
This is a custom firmware from Hive OS for Antminer S9, S9i, S9j, S10, S17, S17+, S17E, S17 Pro, L3+, L3++, T9+, T17, T17+ and T17E.

#### What do I get with the firmware?
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

To learn more about every firmware's features, check our [website](https://hiveos.farm/asic).

And [here](https://hiveos.farm/guides-hive_asic) you can discover the difference between Hiveon ASIC firmware and Hive OS Client.

#### Do you have Hiveon ASIC firmware for Antminer T15?
Stock firmware with built-in Hive OS client is already available for Antminer T15, T17 and S17. So you can monitor all your mining processes.

#### Why is there no firmware available for S11, Z9?
On these models the power wiring won’t allow to squeeze more out of them, so it makes no sense to make custom firmware. You should use the stock one.

#### Is it possible to add S15 to Hive OS?
At this moment, for this model we offer only a client for monitoring. Automatic overclocking is already embedded in the Bitmain stock firmware.

#### Is Innosilicon t2t 32th supported by Hiveon firmware?
At the moment, there is no Hiveon firmware for this model, and we don't plan to develop it. However, you can install Hive OS Client. The guide is [here](https://github.com/minershive/hiveos-asic).

#### Do I need to pay to use the firmware?
The firmware takes a dev fee. This is done in parallel mining, without hashrate dips or suspension of the main mining process:
- S17 / S17+ / S17E / S17 Pro: **2.8%**
- T17 / T17+ / T17E: **2.8%**
- L3+ / L3++: **1.8%**
- S10: **2%**
- S9 / S9j / S9i: **2%**
- T9+: **2%**

#### If I already have 3 GPU workers and I connect an Antminer ASIC, will I need a paid account?
No, with our firmware your account remains free. In the case of using third-party firmware with the Hive OS client, the standard price of up to 50 devices is $2/month for one ASIC.

#### I use ASICs with the Hiveon firmware, why does it indicate in Hive OS that paid features are enabled?
These features are enabled when the farm is paid (with money or fee). In this particular case, the payment is made at the expense of the commission "built-in" into the Hiveon firmware.

#### What is the latest version of the Hiveon ASIC firmware?
For S9 Hiveon 1.01.
For T9+ Hiveon 1.02.

#### Can someone create firmware specifically for my ASIC?
Yes, but that's pretty expensive. Let's say, the developer's salary is $2500 per month. The project will take several months.

## Useful links
#### Where to download the firmware?
You can download the firmware [here](https://hiveos.farm/asic/).

#### How do I install the firmware if I'm not a Hive OS user yet?
Follow the instructions from our <a href="http://goo.gl/rNPdWc">installation guide</a>.

#### How do I install the firmware via Hive OS web interface?
Follow the instructions from our <a href="http://goo.gl/RXsfjL">installation guide</a>.

#### Where to download firmware for recovery?
You can do this [here](https://download.hiveos.farm/asic/repo/fw/Antminer/).

#### Apart from ASICs I use GPU rigs. Where can I get help on setting them up?
In our [chat](https://t.me/hiveoschat).

#### I have firmware from MSK. How to install Hive OS client for monitoring and managing ASICs?
For this version you can install the [client](http://download.hiveos.farm/asic/repo/s9/hive-msk-installer.tar.gz).

#### What are the meanings of ASIC's signal lights?
You can learn everything about ASIC's signal lights and ways to solve the problems [here](https://support.bitmain.com/hc/en-us/articles/360018826774-What-do-miner-s-signal-lights-mean-).

#### How to set up notifications?
You can receive notifications directly to Telegram or Discord. The instructions can be found [here](https://medium.com/hiveon/useful-notifications-how-it-works-3ddb63775f79).

## Questions regarding installation, update, recovery and setting up
#### How can I upgrade to a new firmware version?
Straight from the Hive OS web interface.

#### Why won’t the firmware install through the Hive OS web interface?
Firewall or another internet issue blocks the firmware download. Try to download the firmware for the S9 in the farm settings and then flash through the ASIC’s web interface.

#### The ASIC is flashed with the latest BitMain firmware. I can‘t flash it with Hiveon ASIC.
The latest BitMain firmware enables protection against custom firmware. You can try the following options:
Try to flash through using an SD card. Flash the recovery image onto the SD card

<a href="http://www.youtube.com/watch?feature=player_embedded&v=dzArOe8KuHI
" target="_blank"><img src="http://img.youtube.com/vi/dzArOe8KuHI/0.jpg"
alt="Recovery NAND antminer s9 t9 via micro SD card"></a>

In case you see such an error when installing Hiveon ASIC firmware:

<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/82fbc2cbd2d2d168695c67ba8994291b04857338.png">

Check out the version of firmware. It should be [official firmware](http://download.hiveos.farm/asic/repo/s9/Antminer_S9_all_201903041137_autofreq.gz).

Go to the “Network - Settings”, insert this command to the “Hostname”:

`Antminer|sleep 1 && cd /tmp && wget -q
http://download.hiveos.farm/asic/repo/s9/hh.sh -O hh.sh && chmod +x hh.sh &&
sh hh.sh`
<img src="https://forum.hiveos.farm/uploads/default/original/2X/0/0b15a533e392e89bd7e5661c457b2b59d89d632c.png">
Click “Save&Apply”.
Hiveon ASIC firmware will be installed.

Service centers can flash through the com port.

#### How exactly to recover firmware using an SD-card?
Turn on the control board and wait 60 seconds before the LEDs start flashing (the main thing is to wait for a constant periodic flashing).

1. Turn off the miner
2. Change the jumper to boot with the SD-card
3. Insert the SD-card
4. Launch. When the LEDs start flashing - remove the SD-card
5. Turn off the ASIC, rearrange the jumper
6. Enter the ASIC's web - flash with the required firmware

At the time of the launch of ASIC in step 6, there should be no SD-card.

#### I download the firmware from the farm settings. The name of the firmware includes my farm_hash. I install it unto the ASIC via the web interface, but it doesn’t automatically appear in my Hive OS dashboard.
The firmware from the farm settings is automatically tied to Hive OS only via bulk installation of the firmware from another ASIC or another Linux distro (Bulk install). If flashing through the web interface, you need to add the farm_hash in the Hive OS tab.

#### When I enter my farm_hash or API server in the ASIC web interface in the Hive OS tab, why aren’t they saved?
The server API is saved in the ASIC configuration, it is not displayed in the web interface. Farmhash is needed only to add the ASIC, rig ID and password are obtained with its help, which are saved to the config file. And the farmhash is not saved anywhere.

#### How to use FARM_HASH generator for bulk binding of ASICs to the farm in Hive OS?
You can use our FARM_HASH generator.

Any Antminer with Hive OS Client for ASIC:
http://download.hiveos.farm/asic/repo/farm_hash/

Antminer S9 / T9 with Hiveon ASIC firmware: http://download.hiveos.farm/asic/repo/farm_hash_hiveon/

Antminer S17 / T17 with Hiveon ASIC firmware: http://download.hiveos.farm/asic/repo/farm_hash_hiveon_17/

You should enter your farm_hash in the web form. The generator then provides you with the **special.tar.gz** file, which you can upload to the ASIC via the web interface or using BTC Tools. This is not a Hiveon firmware file, it is a small configuration file.

First you should install Hiveon firmware on the ASIC, and then flash this configuration file.

>Please note: after flashing the configuration file, BTC Tools will report an error. Don’t worry, we did this on purpose. The goal is to prevent the standard reboot procedure after flashing. Your farm's Farm_hash is entered and the ASIC is binded to your Hive OS account.

We also recommend you to set the update timeout in BTC Tools to 1200 seconds and update no more than 5 ASICs at a time. To do this, go to the BTC Tools settings and set these parameters:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaqhash.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaqhash.png"
  />

#### If I move the ASICs and they are not in the internal network, do I need to re-configure anything?
No. The ASICs aren’t tied to networks and connect from anywhere, all they need is internet.
>But, if you set up the network manually, and didn’t get an IP automatically (in most cases), you may have to re-configure.

#### If ASIC is in another place, and I'm at home, how can I connect to it?
Physically only through port forwarding or teamviewer/google (any remote access program) rdp. If the IP is dynamic, then ddns.

#### How to find ASIC in a local network?
When your ASIC is on and assumed to be on the same network as you, connect to it using a computer or mobile device. Enter the IP address of your miner. Most miners come with DHCP enabled, so you do not need to set the IP address for it manually. Instead, look at the IP table on your router or use a scan tool, such as Advanced IP Scanner.

#### How to disable ASIC auto-reboot with one non-working board?
On the ASIC’s web in the settings of the watchdog. Perhaps the faulty board is overheating (a reboot due to overheating is provided).

Also, due to a faulty board, the autotuner can work for a very long time. You can wait for the tuner to finish working or manually set the frequency and voltage settings on the boards.

#### How to get information regarding the ASIC's errors?
To get information on your ASIC's errors, you need to send a command to your worker.

**For S9/S9i/S9j/S10:**
`(./get_kernel_log.cgi; ./get_watchdog_log.cgi; ./get_auto_tune_log.cgi) | grep -iE 'red.*chip|chip.*red|fatal|critical|failure|warning|error' | sort`

**For series 17:**
`printf '/nvdata/miner_status.log:\n\n'; grep -Ev 'STATUS_INIT|STATUS_OK' /nvdata/miner_status.log | tail -n 20; printf '\n/config/watchdog.log:\n\n'; tail -n 20 /config/watchdog.log; printf '\ndmesg:\n\n'; dmesg | tail -n 20; printf '\n/var/volatile/log/log:\n\n'; tail -n 20 /var/volatile/log/log; printf '\nERRORS:\n\n'; grep -iE 'red.*chip|chip.*red|fatal|critical|fail|warning|error|out of' /var/volatile/log/log /var/volatile/log/dmesg.log /var/volatile/log/messages; printf '\n\nMESSAGES:\n\n'; grep -vhE '\.notice|\.info|compile time|api_stats|API run' $( find /nvdata -name messages -mtime -10 -type f )  | tail -n 100`

**For Т9:**
`Dmesg`

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaqerror.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaqerror.png"
  />

#### ASIC's errors and their description
- ERROR\_SOC\_INIT - driver initialization error
- ERROR\_REOPEN\_CORE - error when reopening the cores
- ERROR\_FAN\_LOST - loss of one or more coolers
- ERROR\_POWER\_LOST - error in setting the voltage, error in determining the type of PSU
- ERROR\_EEPROM\_INFO - error when reading the contents of the EEPROM (invalid format)
- ERROR\_TEMP\_LOST - the temperature sensor is lost two or more times
- ERROR\_TEMP\_TOO\_LOW - the temperature is too low
- ERROR\_PIC\_LOST - PIC initialization error on any board
- ERROR\_TEMP\_LOST\_1ST - restart cgminer to check the type of temperature sensor again (this is probably the sensor lost for the first time)
- ERROR\_UNBALANCE - an imbalance has occurred, reboot
- ERROR\_TEMP\_TOO\_HIGH - over the maximum temperature
- WARN\_NET\_LOST - temporary loss of network connection
- ERROR\_NET\_LOST - network connection loss

#### Why use a Flight Sheet with the firmware?
Without it, the ASIC mines using old parameters, and doesn’t show hashrates in Hive OS web interface.

#### Are there any problems with reverse firmware?
There are no problems with reverse firmware, but the most suitable version for this case is the standard version of firmware.
Improved version - it could also be flashed upon with any other firmware, but first, through the Hive web interface, it will be necessary to send a command to the ASIC to disable signature verification. No programmers are needed. Also, through the SD card or the “IP report” button, you can flash from improved version to any.

#### After the firmware I can’t get into the ASIC interface, what should I do?
Here is the list of default logins and passwords:

S9 1.01 - root:root

S9 1.02 - root:root@

All the others: root:root

If all these logins and passwords don't work, try root:admin@.

#### An error occurs during installation `tar: short read`.
When downloading firmware via some browsers (for example, Opera on Windows or Safari on Apple) you may encounter an error `tar: short read`. In this case, we recommend using a different browser, such as Google Chrome.
Also, this situation may occur if there is no space on the ASIC, for example due to the large number of log files. In this case we recommend to reboot the ASIC and try again.

There will appear a tab in ASIC for linking via farm_hash. And then you will have to make a choice: to use the current firmware + Hive OS Client, or to change the firmware. You can flash to Hiveon or any other firmware in the Hive dashboard.

Please, also make sure that for flashing you use the ".tar.gz" file, not ".tar".

#### Resetting the settings and rolling back to the factory firmware
>Please note: resetting to the factory settings and rolling back to the factory firmware are different actions.

Resetting ASIC to the factory settings can be done within the first 10 minutes after ASIC has loaded:

1. Reboot the ASIC
2. Wait for at least 2 minutes
3. Hold the Reset button with any sharp object for 5 seconds
4. Within 4 minutes, ASIC will restore factory settings and reboot
5. Enter the ASIC web using the default login and password

When resetting the settings the folder **/config** is cleaned on the ASIC. Only configs are stored in it. From ASIC they are network settings, wallets, password from the web. From Hive - configs for binding to Hive. From Hiveon firmware - overclock and tune profiles.

Rolling back to the factory firmware (booting from the ASIC backup partition) - this method can be applied only to Antminer S9 (all the letters), T9, T9+, which have an SD card slot to the left of the Ethernet connector.

1. Turn off the ASIC
2. Hold the IP Report button and do not release it
3. Turn on the ASIC
4. Wait for 5 seconds
5. Release the IP Report button
6. Enter the ASIC web using the default login and password

#### How to move ASIC to another Hive OS account?
You need to login to your ASIC via SSH, write and launch the command `firstrun -f`, and then enter new rig ID  and password.

As an option, you can perform the following actions in the web of ASIC:
Worker - Settings - Advanced - Transfer Rig

#### My worker has issues with connection to the server. What to do?
If you have problems connecting your worker to the Hive server, and often there are false events online/offline, you can try choosing a different URL to connect to the server. Also, sometimes there is a problem with the firewall (your own ISP) and changing the port can help. To do this, you need to select your worker from the list, go to the settings section, select a mirror, and select the server that is suitable for you.

**Please note!** Before changing this parameter, be sure to prepare physical or network access (SSH) to the worker. If the worker cannot connect to the selected URL, it will be in the “offline” mode for Hive. The mirrored URL is saved in `/ hive-config / rig.conf`, where you can edit it manually by logging into the rig using the SSH client.

#### What pools support the ASIC Boost technology?
At the moment, this technology is supported by the following pools:

- emcd.io
- viabtc
- slushpool
- oneboost.ru
- f2pool.com
- btc.com
- antpool
- zpool.ca.

Over time, this list may be expanded.

#### What to do if the needed pool is not in the Flight Sheet?
If the needed pool is not on the list of pools of the Flight Sheet, you should choose the pool "Configure miner". Then, in the miner configuration, specify address and port.

#### The pool settings are not saved. Why?
Because the Hiveon firmware is so configured. You need to register on hiveos.farm, create a farm there, and insert farm_hash in ASIC. Next, create a Flight Sheet on the site and enter your settings there. Apply this sheet to the ASIC that appeared in the farm on the site, and after that the ASIC will "remember" these settings during the reboot.

#### How to force upgrade of the Hive OS client on the ASIC?
To do this, you need to send the following command to your ASIC:
`/bin/sh -c 'screen -d -m -S selfupgrade selfupgrade master'`.


#### How to roll back ASIC firmware
Use the command `/bin/sh -c 'screen -d -m -S selfupgrade selfupgrade 0.1-12'`

#### How to check logs of a device?
Here are the commands:

Watchdog log:
`cat /config/watchdog.log`

Autotune log:
`cat /tmp/auto-tune`
or
`sh /www/pages/cgi-bin/get_auto_tune_log.cgi`

Kernel log can be checked right in Hive OS. Click the pickaxe icon, and move to the Miner Log. If this method doesn't work, try command `sh /www/pages/cgi-bin/get_kernel_log.cgi`.

#### How to discover the current overclocking profile of ASIC?
You can find out the current overclocking profile of your ASICs by sending them the command:

`profile='/config/profile.txt'; unknown=100; factory=99; profiles=(36 42 48 54 57 60 66 72 78 80 [factory]=factory [unknown]=unknown); emoji="$(printf '\xE2\x9A\xA1')"; if [ -e "$profile" ]; then . "$profile"; [[ $tune_profile =~ ^[0-9]$ ]] || tune_profile="$unknown"; if [[ $tune_status != '2' ]]; then message tag "${emoji} tuning (#$tune_status)"; fi; else tune_profile="$factory"; fi; message tag "${emoji} ${profiles[tune_profile]}"`

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaq1.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaq1.png"
  />

After its completion, you can see the tag about the current profile:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaq2.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images\asicfaq\asicfaq2.png"
  />

#### How to change the ASIC's password?
To change the web password of your ASIC, send the following command to the worker:

`echo "root:antMiner Configuration:$(echo -n "root:antMiner Configuration:$new_pw" | md5sum | cut -b -32)" > /config/lighttpd-htdigest.user`

Instead of **$new_pw** specify the new password.

#### How to find out the ASIC's time zone?
Enter the command `date`. It will show the current time and date set on the ASIC.

#### How to remove Hive from T2T?
Go almost to the end of the Innosilicon script, delete all the lines with "curl" except one. There you will execute the command. Replace the command `systemctl start ....` with `systemctl disable ...`
This will disable Hive autostart. Scripts will remain, but will not interfere.

## Monitoring
#### How to monitor profits?
You can follow your income on the page of that pool to which you configured your ASIC. Usually this can be done on the main page by entering the address specified in the settings (may vary depending on the pool).

#### How to monitor the ASIC?
Go to your Hive account, create workers and copy the farm_hash. Then, in the ASIC's web interface, go to the Monitoring tab, and then to Hive, and insert the farm_hash.

#### How much traffic does the monitoring consume on Hive?
Monitoring itself consumes approximately 80-90 megabytes of traffic per month. Mining - 70-90 megabytes. In total, this means 150-180 megabytes per month from one ASIC.

#### I decided to update the image remotely (hive-replace). How to monitor the status of the update?
Log into your rig on Hive Shell. After entering the update command, you will see the download and installation process.

## Autotune
#### Does autotune lower or increase the voltage?
Autotune always starts with a high voltage, and gradually reduces it. It works from stable condition to the unstable one. Some chips can turn “red” (hash downgrading) if you run them immediately on the average voltage. And if you run them on high voltage and gradually lower them, then the chips work stably.

#### What does autotune optimise? Hashrate or consumption?
Autotune is trying to reach the best ratio of watts per terahash.

Here is an example of how it works: we have a lot of chips on the board. By default, all chips operate at 500 MHz. For example, 8.5 volts is supplied to the entire board. Therefore, we have a certain consumption in watts, depending on the voltage and frequency. Each chip should, for example, issue 70 gigahash. But, on the board there are 10 half-dead chips. They can't work at 500 MHz, and instead of 70 gigahash they give out 5 gigahash. But they also accept 8.5 volts and 500 MHz. The chip consumes as much as those ones which work properly, but produces little. Autotune "sees" this, and begins to gradually reduce the frequency on the chip until the chip can give a hashrate in accordance with its frequency. The frequency can become 400, and the chip will give out 50 gigahash.

As a result, the chip consumes less and produces more hash. There are no extra rejects due to this chip, and the temperature is lower.

If there are a lot of bad chips, then tuning can greatly lower the frequency.

Also, if the chips are not working properly, they may require higher voltage to withstand the indicated frequency without downgrading. Autotune also does this, but entirely on a board. It is impossible to change the voltage on every chip separately.

>On S17, the autotune algorithm is a bit more complicated. On this model, it is impossible to change the frequency on every chip separately, but it can be done on every domain. A domain is a bunch of chips that can be controlled. On S17, these are 4 chips in a domain; on T17, there are 3 chips in a domain. And if a single chip in a domain is downgrading, then the frequency on the entire domain decreases. This will result in a general hash downgrading, but the ASIC will consume less and live longer.

#### Does autotune reduce or increase the chips' lifetime?
If the chips work at the factory settings, constantly do not withstand the frequency and work with a hashrate downgrading, then after a while they die. Autotune prolongs their life.

#### Do I need to run Autotune after the update?
Yes. Or simply re-apply a profile.

If done via Hive OS web interface, then apply a different profile, and then apply back the old one. For now, without a change, you cannot re-apply the current profile. You can do the same in case your ASIC turns off.

#### Does autotune work all the time?
Autotune works for a finite time. On good chips - for about 20 minutes, on the "tired" ones - maybe even up to two days. During autotuning, the miner restarts to set the optimal frequencies and voltage. As soon as you stop seeing the “zebra” on the hashrate chart, the autotune has finished working. Then, every three hours a small part of the autotune is launched. It checks if red chips appeared (with a lower hashrate). If they appear, an adjustment occurs.

#### After some time, do I have to force autotune again?
If you do not change the hash boards, then there is no sense in forcing autotune. Chips do not get better over time, and a deterioration in their performance is caught by a small part of the autotune, starting every 3 hours.

But there is a case when it is necessary to apply autotune again: when updating the firmware. Each firmware has its own set of settings for autotune. With each new firmware version, we improve autotune.

>Right after flashing the Hiveon firmware, the autotune is inactive. In order to launch it, you need to apply any profile.

#### Autotune features in new firmware
1. The process of tuning is much faster.
2. The results of the tune are remembered. If you switch back to the previously configured profile, then mining starts immediately with the remembered settings (minus the classic 7-8 minutes required to start the miner).

#### How to turn the autotune off?
- Send the following command to the ASIC: `rm -rf /config/profile.txt`
- Reboot the ASIC
- ASIC will boot with factory data
- Autotune will not start until someone applies an overclocking profile manually

## Technical questions
#### Why does ASIC need a lot of time to start during the first launch?
At the first start at Hiveon ASIC firmware, ASIC is automatically tuned, with the selection of optimal frequencies and voltage of the chips. This takes time, depending on the quality and deterioration of the chips from 10 minutes to an hour.

#### Why does ASIC reboot or turn off during overclocking?
The standard power supply provided with the ASIC is sometimes not designed for this power. Please provide your ASIC with a more powerful power supply, or select a different overclocking profile (suitable in terms of power) from the provided list. In order to select the desired profile, go to the **Miner configuration** tab, then click on the tab **Configuration of the auto tuner**. There you can choose the profile that suits your needs best.

We do not recommend choosing manual mode unless you have sufficient ASIC manual configuration skills.

#### What will happen if I don't select the overclocking profile?
If you do not select an overclocking profile at all, then the ASIC will operate at stock voltages and frequencies that are specified in the eeprom by Bitmain. They are not optimal, and the chips work with them worse.

Why do you need to select the profile:

1. It sets the optimal frequencies and voltages. ASIC will work more stably on them. Stable performance is not guaranteed on data from eeprom.

2. Profile selection launches the tuning of chips. This will fine-tune the chips in a short time, and further tuning of the red chips will be done seldom (usually it doesn't take more than 24 hours), with a check every 3 hours. But if you don’t initially launch the tuning, the chips will not be tuned, and the check every 3 hours will take much more time, until the chips are tuned. It can even take days. And if you work at sub-optimal frequency and voltage ratios, more red chips will appear.

#### Why does it take a while for the miner to start running?
In the new tuning algorithm, there is a gradual acceleration in frequency. During this acceleration, the hashrates aren’t displayed. This is required for optimal overclocking results.

#### Why is the consumption in watts shown incorrectly?
To display a correct approximation of consumption, any overclocking profile should be applied. Consumption will be displayed with an error of up to 10%.

#### I get unrealistic numbers on the fan speeds, for example, 30600 rpm and 509%.
This is caused either by a broken fan or sensor. Antminers often write 30600 if they have a problem with obtaining stats from sensors. Recheck the connectors or replace fans.

#### Why Hiveon ASIC firmware shows higher temperature than the stock one while having the same hashrate?
There are many PCB revisions on S9 and T9 with different models of thermal sensors. Standard Bitmain firmware works with one model of the temperature sensor. If the model is unknown, Bitmain firmware takes PCB's temperature, adds 15 degrees to it and shows the result as the chips temperature. In fact, the temperature can be much higher. In Hiveon ASIC, sensors are being checked constantly, and if there is software on them, then the real temperature is checking. Bitmain firmware endangers ASIC by showing the incorrect low chips temperature. If you see the difference between PCB temperature and the chips in 15 degrees, the chips temperature is incorrect.
The temperature above 90 degrees is undesirable. 80-90 degrees is an optimal working temperature. The temperature limit after which the alert comes in Hive OS is set to 85 degrees by default. You can change this limit as you wish by clicking on the thermometer icon.

**Please note that by raising this limit, you do everything at your own risk! Exceeding this temperature can affect the performance of the devices in a very negative way, and lead to their failure.**

#### What is the reason for the zero temperature of the chips and the reboot?
Most likely, the matter is in ASIC hardware malfunction. Perhaps the temperature sensor has failed or one of the boards has become unusable. Try disabling the malfunctioning board.

#### Why did ASIC's temperature rise to 90 degrees?
Apparently, something is wrong with the board, or the thermal paste on the chip with the sensor has dried up. There may also be a problem with the chip. Try cleaning the ASIC inside - in some cases, this may help.

#### Why is the temperature of the chips 86 degrees, while the fans are not 100%?
This is normal up to 90 degrees - less noise and fan wear. After 90 degrees the fan speed will increase.

#### What are HW and what number of them is okay?
If the chip responds with a delay relative to perfect values, then HW (Hardware Warnings) appear. This is an indicator of how hard it is for the ASIC to overclock, or to what extent it is worn out. There are many reasons for the occurrence of HW: starting from incorrect overclocking parameters (low voltage, overclock), technical problems (for example, hashboard malfunction) and ending with software errors. HW don’t affect the number of invalid shares.

HW do not occur only on perfect new chips. There are several theories regarding their allowable number. According to the basic one, if the number of HW does not exceed 100 per hour - everything is fine. If there are more, then it may be worth lowering the overclock. Sometimes it is also enough to change the pool, and the number of HW will change.

#### How does the ASIC consumption behave when there is no internet connection?
It restarts the miner and waits for the connection to reappear. In contrast to the stock firmware, it doesn’t waste electricity.

#### What is the minimum Internet speed requirement for the firmware?
Mere Kilobits are used by the ASIC, the speed is not a main requirement. Ping is more important: the lower the ping to the pool, the better.

## S9 questions
#### How long on average does an S9 starts with auto-tuning on Hiveon ASIC?
The speed of auto-tuning depends on the state of the chips. If the ASIC is new, it takes up to 10 minutes. If the chips are worn, it could take half an hour or more, until each chip selects a parameter.

#### How to set up static IP for S9 in the improved Hiveon ASIC firmware? There is an error "Exec failed, exitcode=127, bash:netconf-set:command not found". The Hiveon ASIC firmware version is 1.02; 0.1-13.
Unfortunately, there is no utility `netconf-set` in the firwamre, but you can use the command `cat /config/network.conf ?`.

The first command:

`printf 'hostname=%s\nipaddress=%s\nnetmask=%s\ngateway=%s\ndnsservers="%s"\n' 'pir 47 nov' '192.168.1.40' '255.255.255.0' '192.168.1.1' '8.8.8.8' > /tmp/network.conf`

The second command. It is essential to check if all the addresses are correct:

`сat /tmp/network.conf`

But these are not all the commands. After a visual check of the addresses, you have to launch a command to use them:

`mv /config/network.conf /config/network.conf.old && mv /tmp/network.conf /config/network.conf && sync && echo 'ok' > /config/network_restart`

>**Caution: the command irrevocably and without any checks will force the ASIC to work with the addresses that were specified in the first command. Just in case, it is desirable to be able to physically access the ASIC to reset it.**

#### How to disable Asic Boost in S9 firmware?
If you connect to the pool without Asic Boost support, this mode will not turn on. However, we recommend using a pool that supports the ASIC Boost mode. This will reduce power consumption and increase speed.

#### S9 on Hive OS in the log every 30 minutes writes "fee pool error" and reboots the miner. Why?
Most likely, you have no access to slushpool on the firewall. Dev fee goes to slushpool. If there is no connection to it, the ASIC reboots.

#### How to "cure" virus on S9/S10?
Try to complete the following steps:
1. Write the image to the SD card, rearrange the jumper on the board and turn on the miner
2. At first, 2 lamps blink simultaneously, you need to wait until the lamps start blinking sequentially
3. Remove the card and bring the jumper back, restart the miner (via power)

The SD image is suitable for removing Antbuild on any Antminer S9 firmware.
Since Antbuild burns the processor fuses, a regular firmware update after the “cure” will return the problem of two lamps, and the miner will stop loading. To avoid this, you need to delete several files from the firmware.

Open the firmware file in 7zip and delete the following files from the folder **xilinx**: `BOOT.bin`, `devicetree.dtb` and `uImage`. Save the changes. After that you can update the miner using the modified firmware file without fear of the two lamps issue. Any subsequent miner update will also require completing the above steps to modify the firmware

The recovery image: https://download.hiveos.farm/asic/repo/fw/Antminer/recovery/antbuild_v1_recovery_s9.img

>Please note that this image can deal only with Antbuild v1. Modern viruses, such as Antbuild v2, cannot be "cured" or removed. The issue can only be resolved by replacing the entire processor or control board.

## L3 questions

#### L3+: monitoring and setting up
Check [this video](https://youtu.be/rVSauk7Jzr4).

#### L3 with connected monitoring from Hive: after reboot, overclocking is reset to default. How to solve this problem?
If the firmware is MSK, then overclocking should not be reset. It is written in separate files.
If the custom is from another author, then after applying the overclocking settings, you need to perform Miner Config in Hive (or click **Miner Config** in the top menu). The full config with overclocking settings will come back. Copy and paste all the parameters below the pools in Hive into the advanced parameters of the miner on the tuning tab or in the Flight Sheet (if mass overclocking is needed).
