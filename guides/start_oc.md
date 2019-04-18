# Getting Started with Hive OS — Overclocking Profiles Basics

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/header.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/header.png"
  />

The previous article covered the basics of creating Fight Sheets for your workers, in this article we’ll dive deeper into fine-tuning your worker with Overclocking Profiles.

>_Disclaimer: Any settings that deviate from factory values may cause your system to become unstable. Use at your own risk._

# What Is An Overclocking Profile
In general terms, overclocking is pushing your hardware beyond it’s factory specs thus possibly improving its performance. An Overclocking Profile can also be used for other purposes, like downvolting — reducing your hardware’s power consumption. There are many applications for overclocking and we’ll try to cover some of them in this article.

Overclocking is a process of trial and error and requires patience to achieve the desired results. You should always let your hardware run with each set of new Overclocking Profiles for some time to see if those specific parameters will stay stable. Hardware can behave differently sometime yelding unpredictable results. One way to see if your overclocking changes were successful is whether or not you start getting rejected shares.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/rejects.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/rejects.png"
  />

_Rejected shares_

Rejected shares — shares that your miner worked but they were either not submitted in time to be included in the block or they had an error. The most common reason for a large amount of rejected shares is due to overclocking the GPU too much to the point where it produces faulty shares. The smaller the rate of rejected shares to accepted, the higher the efficiency of your GPU’s Overclocking Profile.

This said, most users leave their hardware at default settings as overclocking results may vary for each user. It also greatly depends on the actual components a manufacturer uses as some components are capable of being overclocked beyond spec and some simply don’t perform so great.

# Creating An Overclocking Profile
All Overclocking Profiles are created individually for each farm and can’t be shared across farms. You can either create a farm-wide profile or a worker specific profile. The worker specific settings will always override any farm-wide settings. For example, this way you can set the optimal desired settings for the whole farm and then fine-tune each rig individually.

To add a new profile, go to your farm’s Overclocking Profiles tab and click the **Add OC Profile** button. In the **Save Overclocking as Template** window give your profile a name and click **Save**.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/new_oc.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/new_oc.gif"
  />

_Creating a new OC template_

You’ve created a template that will later be used by specific workers or across your entire farm. This template can then be copied and modified for different miner or algorithm combinations.

The template we created will be used by all your GPUs, but the settings are different for Nvidia and AMD. You can have separate sets of settings for both GPU types within the same profile in case your rig is running both Nvidia and AMD GPUs and they will apply to each GPU type individually.

To edit your overclocking profile click the plus icon next to your the profile’s name and follow the instructions below depending on your GPU type.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/add_oc.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/add_oc.png"
  />

_Editing the OC template_

## Overclocking Nvidia GPUs
Before changing any settings you can run the nvidia-smi command to find out your current GPU settings. To do this remotely from your dashboard, go to your worker and click the **Run Command** button in the toolbar at the top of the screen.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/toolbar.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/toolbar.png"
  />

_Toolbar_

You can specify one value for all cards or list of values for each card separated by a space. For example:

150 — one value for all GPUs.

0 100 0 0 0 140 — means GPU0 = none, GPU1 = 100, etc.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/nvidia_oc.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/nvidia_oc.png"
  />

_Nvidia OC window_

The **Algo** field is used to specify overclock settings for a specific algorithm. You can create a separate set of overclock setting for each algorithm individually or choose the **Default Config** that will apply to all algorithms, but can be overwritten by the algorithm settings themselves.

* __+Core Clock (Mhz)__ — increases the GPU’s core clock speed in Mhz. The minimum and maximum values for your GPU can be found in the Nvidia X Server Settings tool by going to the PowerMizer tab on your rig. 0 will always be the GPU’s default (factory) value.
* __Memory (Mhz)__ — increases the GPU’s memory speed in Mhz. Usually this value is double from what you see in AfterBurner. For example, if in Windows it’s +800Mhz, then the value here should be 1600. The minimum and maximum values for your GPU can be found in the Nvidia X Server Settings tool by going to the PowerMizer tab.
* __Fan (%)__ — controls the speed of your GPU fan/fans. 0 will always be the GPU’s default (factory) value. Your GPU’s BIOS will determine the default speed of the fan, not the miner.
* __Power Limit (W)__ — controls the power consumption. These values must be absolute, unlike in AfterBurner, where the values are percentile. You can check your power limit values in your GPU list of the rig. For example, Power Limit 60.00 W, 120.00 W, 140.00 W means that the first value, 60.00 W — the minimum, 120.00 W — the default, and 140.00 W — the maximum. The setting won’t apply if your values are less or greater than the min/max values of your specific GPU.
* __Turn Off LEDs__ — this turns off the LED lights on your GPU, if there are any. This option may not work on some GPUs.
* __OhGodAnETHlargementPill__ — works only with Nvidia GTX 1080 series. Provided by OhGodACompany. Check their [GitHub](https://github.com/OhGodACompany/OhGodAnETHlargementPill) page for details.
* Click **Save** and you’re done.

## Example: Nvidia GTX 1060 Overclocking
Here’s an example of an Overclocking Profile for an Nvidia GTX 1060 GPU.

_Note, these values are for example purposes. Use at your own risk._

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/nv_oc_eg.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/nv_oc_eg.gif"
  />

_Nvidia OC example settings_

* __Algo__ — we set it to the **Default Config** as we want it to apply to all algorithms
* __+Core Clock (Mhz)__ — 130
* __Memory (Mhz)__ — 2000
* __Fan (%)__ — left empty for default values
* __Power Limit (W)__ — 120
* __Turn Off LEDs__ — our GPU doesn’t have LEDs, so we skipped this setting
* __OhGodAnETHlargementPill__ — this is available only for the 1080 series GPUs, so we skipped this setting
* Click __Save__ and you’re done.

# Overclocking AMD GPUs
Before changing any settings you can run the `amd-info` command to find out your current GPU settings. To do this remotely from your dashboard, go to your worker and click the **Run Command** button in the toolbar at the top of the screen.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/toolbar.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/toolbar.png"
  />

_Toolbar_

You can specify one value for all cards or list of values for each card separated by a space. For example:

150 — one value for all GPUs.

0 100 0 0 0 140 — means GPU0 = none, GPU1 = 100, etc.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/amd_oc.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/amd_oc.png"
  />

_AMD OC window_

The **Algo** field is used to specify overclock settings for a specific algorithm. You can create a separate set of overclock setting for each algorithm individually or choose the **Default Config** that will apply to all algorithms, but can be overwritten by the algorithm settings themselves.

* __Core Clock (Mhz)__ — sets the core clock. A good value would be around 1100. If **Core State** is unset, then the default 5 state will be used to set the clock. All values must be absolute.
* __Core State (Index)__ — required if you try to undervolt you card. You should use this parameter in conjunction with **Core Clock** and **Core Voltage** settings. This is called a DPM (Dynamic Power Management) or “Power Level” of a GPU core. For RX GPUs it’s a value from 1 to 7. The default is 5. Decrease the value to downvolt. If you decide to set one of the default states then you don’t need to set any values in **Core Clock** and **Core Voltage**.
* __Core Voltage (mV)__ — required if you try to undervolt your GPU. And you must set Core State or default 5 state will be used to set the voltage. You can set values like 900 meaning mV or values like 65284 from VBIOS table.
* __Memory Clock (Mhz)__ — sets the memory clock speed All values are absolute.
* __Mem State (Index)__ — a very advanced parameter. Change this if there are issues with undervolting. If everything works within spec — don’t change this value. RX cards are known to have 1 or 2 memory states (3 including 0 — idle state). By default the highest state will be selected. But some rare cards are known to fail to undervolt on the highest state and are required to select a lower one. For example, the highest is 2 and for undervolting you would want to set the state to 1. You should use this parameter with **Memory Clock** setting.
* __Fan (%)__ — for setting the fan speed. Keep in mind, miners like claymore will still control the fan speed. You must disable fan control in miner configuration for this to work. We advise leaving this field empty if you have AutoFan turned on. We will write more on AutoFan in our future articles.
* __Aggressive undervolting__ — chooses a set overclocked parameter for each DPM state.
* Click __Save__ and you’re done.

## Example: AMD RX 580 Overclocking

Here’s an example of an Overclocking Profile for an AMD RX 580 GPU.

_Note, these values are for example purposes. Use at your own risk._

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/amd_oc_eg.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/amd_oc_eg.gif"
  />

_AMD OC example settings_

* __Algo__ — we set it to the **Default Config** as we want it to apply to all algorithms
* __Core Clock (Mhz)__ — 1150
* __Core State (Index)__ — 3
* __Core Voltage (mV)__ — 875
* __Memory Clock (Mhz)__ — 2200
* __Mem State (Index)__ — left empty, as our GPU didn’t have an issue undervolting
* __Fan (%)__ — left empty for default values
* __Aggressive undervolting__ — set to active
* Click __Save__ and you’re done.

# Applying An Overclocking Profile

You can now apply the Overclocking Profile you’ve created by going to the Workers tab, then clicking the checkboxes on the left side of the workers to which you want to apply the Overclocking Profile. You should see a speedometer icon appear in the menu bar in the top right corner.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/apply_oc.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/apply_oc.png"
  />

_Applying the OC profile_

Click it, and you should see a window with the number of workers you chose and a list of all your Flight Sheets.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/oc_list.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_oc/oc_list.png"
  />

_List of OC profiles to apply to workers_

Choose the Overclocking Profile you want to apply and click the **Apply** button. You should see a message telling you that the Overclocking command was sent to the worker. In a few seconds your workers should apply the changes.
