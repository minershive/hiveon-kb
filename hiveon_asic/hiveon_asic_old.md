# Hiveon ASIC — Existing User’s Upgrade and Setup Manual

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/header.jpeg?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/header.jpeg"
  />

In our previous article we explained what is Hiveon ASIC firmware and how it works. We also explained how to install this firmware if you’re a new user. In this article we’ll continue the topic and show you how to easily update your existing ASICs.

In this part two we’ll discuss the options for:

* __Updating existing ASICs via Hive OS’s web interface__ — suitable for those who’re already using Hive with their ASICs;
* __Bulk updating existing ASICs__ — suitable for updating entire farms in a few clicks.

If you’re a new user, here’s what [part one](guides/hiveon_asic.md) covered:

* __Installing using ASICs via web interface__ — suitable for installing on a handful of machines for users who haven’t used Hive OS before;
* __Bulk installation__ — suitable for installing unto entire farms.

# Updating using Hive OS’s web interface
Assuming you’re already using Hive OS with your ASICs, you’ll need to update them to the compatible firmware first. If your ASIC model is compatible, you’ll see a yellow **Switch** text near the OS version at the bottom of your worker **Overview** page.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/switch.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/switch.png"
  />

Click it and a new **Change ASIC Firmwares** context window will pop-up. Then click the **Select firmware** dropdown list and choose the appropriate firmware version. In this example it’ll be the _**Antminer-S9-all-Hiveon**_. Click **Apply**.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveos_firmware.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveos_firmware.png"
  />

The ASIC will go **offline** and **reboot**, then it will re-appear as **online** shortly and it’s model name will change from **Antminer S9** to **Antminer S9 Hiveon**. The firmware version will also change.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveon_asic.jpeg?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveon_asic.jpeg"
  />

You’re done, now you can configure your ASIC using the auto tuner.

_For more details regarding other ASIC installation options, please refer to this [GitHub page](https://github.com/minershive/hiveos-asic)._

# Hive OS web UI auto tuner configuration
Once your ASIC is back online, you can now go into the Overclocking tab to use our pre-created auto tuning profiles.

_**Attention! In order to use most of these options, you need to have a custom power supply connected to your ASIC. The factory PSU is not powerful enough to handle the load and your ASIC will turn off.**_

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/profiles.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/profiles.png"
  />

In the **Overclock profiles** section, choose the profile you want to autotune your ASIC. A small disclaimer first: **We don’t recommend choosing Manual mode unless you have sufficient skills in manually fine tuning an ASIC.** We won’t be covering the manual procedure in any of our articles as this profile is too difficult to explain in a short comprehensive form.

Then click the **Apply Changes** button at the bottom of the page and wait for the algorithm to finish auto tuning the ASIC. This may take up to an hour depending on the selected profile. Your hasrates may wildly fluctuate during the process — this is normal.

And you’re done! Happy mining!

# Bulk Update
Assuming you’re already using Hive OS with your ASICs, you’ll need to update them to the compatible firmware first. The Hiveon ASIC firmware is available currently only for **Antminer S9, S9i** and **S9j** with other models coming soon.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_list.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_list.png"
  />

In the **Workers** tab, select the workers you want to update. You’ll see several actions appear in the top right corner of the screen.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_update.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_update.png"
  />

Click the **ASIC Firmware** button and a new **Change ASIC Firmwares** context window will pop-up. Then click the **Select firmware** dropdown list and choose the appropriate firmware version. In this example it’ll be the _**Antminer-S9-all-Hiveon**_. Click **Apply**.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveos_firmware.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveos_firmware.png"
  />

The ASICs will go **offline** and **reboot**, then they will re-appear as **online** shortly and their model names will change from **Antminer S9** to **Antminer S9 Hiveon**. The firmware version will also change.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveon_asic.jpeg?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/hiveon_asic.jpeg"
  />

You’re done, now you can configure your ASIC using the auto tuner.

_For more details regarding other ASIC installation options, please refer to this [GitHub page](https://github.com/minershive/hiveos-asic)._

# Hive OS web UI auto tuner configuration
Once your ASICs were successfully flashed, you can then set our pre-created auto tuning profiles. There you can choose the Profile that suits your needs best. A small disclaimer first: **We don’t recommend choosing Manual mode unless you have sufficient skills in manually fine tuning an ASIC.** We won’t be covering the manual procedure in any of our articles as this profile is too difficult to explain in a short comprehensive form.

_**Attention! In order to use most of these options, you need to have a custom power supply connected to your ASIC. The factory PSU is not powerful enough to handle the load and your ASIC will turn off.**_

In the **Worker** tab, select the workers you want to run the auto tuning script on.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_list.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_list.png"
  />

You’ll see several actions appear in the top right corner of the screen. Click the **Overclocking** button and a new context window will appear.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_oc.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_oc.png"
  />

Select the profile you want then click the **Apply Changes** button at the bottom of the window and wait for the algorithm to finish auto tuning the ASIC. This may take up to an hour depending on the selected profile. Your hasrates may wildly fluctuate during the process — this is normal.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_profiles.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/hiveon_asic_old/asic_profiles.png"
  />

And you’re all done! Congratulations and happy mining!
