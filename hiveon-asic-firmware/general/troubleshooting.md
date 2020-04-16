---
title: ASIC Statuses Troubleshooting
parent_category: Hiveon ASIC Firmware
category: General
---

## ASIC Statuses Troubleshooting
**SUSPENDED** - reboot is required. Alternatively, you can enable the hashrate-watchdog for automatic reboot.

**Tuning** - tuning is in progress, hashrate decrease and software restart are possible.

**ERROR_TEMP_TOO_LOW** - too low temperature. Such an error can occur on the Bitmain firmware, and as a result, ASIC stops mining. If you want, you can disable the temperature test on the Hiveon firmware, and continue the mining process.

**ERROR_FAN_LOST** - loss of a fan, it is essential to check it. Probably, it is out of order, or there are problems with the sensor.

**ERROR_POWER_LOST** - error in setting voltage, error in determining the type of PSU. This could happen due to the following reasons:
1. Power supply failure.
2. Excessive decrease in the network - the unit cannot cope with it.
3. Problems with wiring from the power supply to controller
4. The new ASIC series can determine the PSU model. If the PSU is worn out, the model may not be identified, and, therefore, the ASIC generates this error.

**ERROR_SOC_INIT** - error during the driver initialization. This could happen due to several reasons:
1. The firmware was installed incorrectly, or the kernel does not match. In this case, you can try to re-flash, install the SD-image, or roll back to another version of the firmware, and then back.
2. The firmware does not match the model.
3. Problems with the hardware.

**ERROR_EEPROM_INFO** - error when reading the content of EEPROM (wrong format). It is necessary to flash EEPROM.

**ERROR_TEMP_LOST** - temperature sensor was lost two or more times. This can happen in case of fail of the chips on which the temperature sensors are located. For example, the 17th model has 4 such chips on every board, and if 2 or more chips fail, it is difficult to determine the temperature, and the mining process stops. To solve the problem, you need to replace the chips.
