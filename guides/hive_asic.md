---
title: Hive OS for ASICs
category: Guides
---

### Available software for ASICs from Hive
**1. [Hive OS Client](https://github.com/minershive/hiveos-asic/blob/master/README.md)**

It's a lightweight application running on the stock (or custom firmware of your choice) ASIC firmware.

- Allows you to see the miner in Hive, to control Wallets, Pools, restart and reboot the miner.
- Supports a broad range of ASIC models: Antminer, Innosilicon, Zig and even some FPGA miners.

Supported ASICs:
- **Antminer:**
	- A3
	- B3
	- D3, D3 (Blissz)
	- DR3
	- E3
	- L3+, L3++
	- S7
	- S9, S9i, S9j, S9k, S9SE, S9-Hydro, S9 (VNISH), S9 (MSKMINER)
	- S10 (S9 Dual MSKMINER)
	- S11
	- S15
	- S17, S17+, S17E, S17 Pro
	- T9, T9+
	- T15
	- T17, T17+, T17E
	- X3
	- Z9, Z9-Mini
	- Z11
- **Innosilicon:**
	- A5/A8 (need test)
	- A9 ZMaster
	- D9 DecredMaster
	- S11 SiaMaster
	- T3 BTCMiner
	- T3H+, T3+, T2Th+, T2Thf+, T2Thl+, T2Th, T2Tz-30T, T2Thm, T2Thf, T2T+ (32T), T2Ts-26T, T2Ti-25T, T2T-24T
- **Todek:**
	- Toddminer C1, C1 PRO
- **HashAltCoin:**
	- Blackminer F1, F1+, F1-MINI
	- Blackminer F1-Ultra, F1-MINI+
- **Zig:**
	- Z1, Z1+

Actual list can be always found on <a href="https://github.com/minershive/hiveos-asic">GitHub</a>.

**All the instructions on Hive OS Client installation can be found [here](https://hiveos.farm/guides-add-asic-to-hiveos).**

**2. [Hiveon ASIC Firmware](https://hiveos.farm/asic/)**

It's a custom firmware that replaces the stock one. Supports only selected models: Antminer S17, S17+, S17E, S17 Pro, S9, S9i, S9j, S10, L3+, L3++, T9+, T17, T17+, T17E.

- **S17:** up to 72 Th/s with air cooling
- **S17 Pro:** up to 80.1 Th/s with standard PSU, up to 85 Th/s with liquid cooling
- **S9, S9i, S9j:** up to 16.8 Th/s with standard PSU, up to 19.1 Th/s with the custom one
- **S10:** up to 21.5 Th/s with standard PSU, up to 23.5 Th/s with the custom one
- **T9+:** up to 13.6 Th/s with standard PSU

>Hiveon Firmware for other ASIC models are coming soon, so stay tuned!

Hiveon ASIC Firmware features:

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

**All the instructions on firmware installation can be found [here](https://hiveos.farm/hiveon-asic-firmware).**

### Hive OS Client and Hiveon ASIC Firmware comparison

>Hive OS Client and Hiveon ASIC Firmware **are not the same products**.

|Model / Feature |	See miner in Hive OS |Control wallets & pools |	Restart miner	| Reboot miner	| Anti-virus (Hiveon FW only) |	Over clocking (Hiveon FW only) |	Under volting (Hiveon FW only) | Voltage adjustment (Hiveon FW only) |	Auto-tuning (Hiveon FW only)|
|----|----|-----|-----|-----|----|----|----|----|----|
|**Antminer**||||||||||
|A3|*|*|*|*|
|B3|*|*|*|*|
|D3, D3 (Blissz)|*|*|*|*|
|DR3|*|*|*|*|
|E3|*|*|*|*|
|L3+, L3++|*|*|*|*|*|*|*|*|*|*|
|S7|*|*|*|*|
|S9, S9i, S9j|*|*|*|*|*|*|*|*|*|*|
|S9k, S9SE, S9-Hydro|*|*|*|*|soon|soon|soon|soon|soon|
|S10 (MSKMINER)|*|*|*|*|*|*|*|*|*|*|
|S11|*|*|*|*|
|S15|*|*|*|*|
|S17, S17+, S17E, S17 Pro|*|*|*|*|*|*|*|*|*|*|
|T9|*|*|*|*|
|T9+|*|*|*|*|*|*|*|*|*|*|
|T15|*|*|*|*|
|T17, T17+, T17E|*|*|*|*|*|*|*|*|*|*|
|X3|*|*|*|*|
|Z9, Z9-Mini|*|*|*|*|
|Z11|*|*|*|*|
|**Innosilicon**|
|A5/A8 (need test)|*|*|*|*|
|A9 ZMaster|*|*|*|*|
|D9 DecredMaster|*|*|*|*|
|S11 SiaMaster|*|*|*|*|
|T3 BTCMiner|*|*|*|*|
|T3H+, T3+, T2Th+, T2Thf+, T2Thl+, T2Th, T2Tz-30T, T2Thm, T2Thf, T2T+ (32T), T2Ts-26T, T2Ti-25T, T2T-24T|*|*|*|*|
|**Todek**|
|Toddminer C1, C1 PRO|*|*|*|*|
|**HashAltCoin**|
|Blackminer F1, F1+, F1-MINI|*|*|*|*|
|Blackminer F1-Ultra, F1-MINI+|*|*|*|*|
|**Zig**|
|Z1, Z1+|*|*|*|*|

For any information you may need about ASICs, please check <a href="https://forum.hiveos.farm/c/asic">our forum</a>, [Github](https://github.com/minershive/hiveos-asic/blob/master/README.md) or our [Knowledge Base](https://hiveos.farm/knowledge-base).
