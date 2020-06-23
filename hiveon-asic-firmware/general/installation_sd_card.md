---
title: Firmware installation guide (via SD-card, series S17 and T17)
parent_category: Hiveon ASIC Firmware
category: General
---

### Follow these steps:

**Step 1:** Download the recovery archive suitable for your model:

S17/S17Pro: http://download.hiveos.farm/asic/s17/SD-S17-S17pro-Hiveon-latest.zip

S17+:  http://download.hiveos.farm/asic/S17%2B/SD-S17%2B-Hiveon-latest.zip

S17E: http://download.hiveos.farm/asic/S17E/SD-S17E-Hiveon-latest.zip

T17: http://download.hiveos.farm/asic/T17/SD-T17-Hiveon-latest.zip

T17+: http://download.hiveos.farm/asic/T17%2B/SD-T17%2B-Hiveon-latest.zip

T17E: http://download.hiveos.farm/asic/T17E/SD-T17E-Hiveon-latest.zip

**Step 2:** Insert the MicroSD card in the computer and format in FAT32.
- Emulation of usb or usb-hdd is mandatory (uzb-zip or usb-fdd are not allowed)
- Only FAT32
- No loaders, mbr, or extra sections

**Step 3:** Unzip the downloaded file and copy its content to the MicroSD card. There are files in the root folder. Fill them, and ASIC will connect to Hive OS after flashing:
- FARM\_HASH - in this file, insert FARM\_HASH from the farm settings
- HIVE\_HOST\_URL - insert the API server, if it is essential to replace it. If the file is empty, the standard server is used (api.hiveos.farm)

**Step 4:** Remove the MicroSD card from the computer and insert it into the card slot on the control board.

**Step:** Turn on the control board. Wait about 30 seconds for the files to load automatically. After loading, the red and green indicators on the control board will be flashing (for different models, it may take different time to complete this process).

**Step 6:** Turn off the miner and remove the MicroSD card. Turn on the ASIC, it is already flashed with Hiveon firmware.

**Step 7:** If you haven't filled the file with FARM\_HASH during the Step 3, you can connect ASIC to Hive OS via the ASIC's web-interface (in the **FarmConfig** tab). You can also do bulk connection, via the flashing function in BTC Tools (with the file, generated with this link: http://download.hiveos.farm/asic/repo/farm_hash_hiveon_17/).

### Possible solutions to fix a firmware error:

1. Reformat the microSD and make sure you copied the right firmware.

2. Softly press the microSD to make sure it is firmly attached.

3. Clean the MicroSD.

4. Try with different, popular MicroSD. We don't recommend the SDXC type.

5. Try MicroSD with a smaller volume.

### Useful utilities
[Win32DiskImager](http://download.hiveos.farm/asic/utility/Win32DiskImager-1.0.0-binary.zip) - formats an SD-card and transfers the image to it.
