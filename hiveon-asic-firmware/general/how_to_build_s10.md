---
title: How to get Antminer S10 from two Antminers S9
path: /hiveon-asic-firmware-general-how-to-build-s10
parent_category: Hiveon ASIC Firmware
category: General
meta_description: Are you going to build up an Antminer S10 from two Antminers S9? This instruction is here to help.
---

Antminer S10 is a combination of two Antminers S9 connected to the same power supply unit. To turn your Antminers S9 into Antminer S10, follow these steps:

1. Get **4.7 K Ohm SMD** resistors (9 items) and **18 pin connectors** (3 units). Please note that the smaller the resistors are, the easier it will be for you to install them.

2. Solder 3 pin connectors “into” the yellow squares:

<img src="https://lbd.hiveos.farm/kb/images/buildings10image1.png" alt="buildings10">

After the solder process is over, you should get something like this:

<img src="https://lbd.hiveos.farm/kb/images/buildings10image2.png" alt="buildings10">

3. Now take a look at this picture again:

<img src="https://lbd.hiveos.farm/kb/images/buildings10image1.png" alt="buildings10">

Next to every pin connector, you should install 3 resistors. We marked their locations with red squares.

4. After everything is done, you can flash your ASIC with the Hiveon ASIC S10 firmware. You can download it [here](https://hiveos.farm/asic/). Both firmware options, improved and standard, are already available. To learn the difference between improved and standard firmware, check [this article](https://hiveos.farm/hiveon-asic-firmware-general-standard_improved_firmware/).

If you have a standard PSU, we recommend to choose the overclocking profiles up to 1600 W. In case you want higher rates (over 21.5 TH/s), you will need a more powerful PSU.
