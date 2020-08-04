---
title: Autotune
path: /hiveon-asic-firmware-general-autotune
parent_category: Hiveon ASIC Firmware
category: General
---

The main task of autotune is to make the hashrate higher and the energy consumption - lower (the autotune keeps the consumption indicated in the profile).

Autotune lowers or increases the voltage on the boards, if necessary. Controls the frequency of all chips, and, separately, weak chips. If the chips are not tuned, then the problematic chips will have a hashrate decrease, while they will consume as much as other chips. It also helps to overclock ASICs.

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
- Send the following command to the ASIC: `asic-oc factory`
- Reboot the ASIC
- ASIC will boot with factory data
- Autotune will not start until someone applies an overclocking profile manually

#### How to re-tune the current profile (like after hashboard swap)?
- Send the following command to the ASIC: `asic-oc re-tune`
- Autotune will re-tune current profile from scratch
