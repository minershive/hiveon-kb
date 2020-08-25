---
title: GPU FAQ
category: Guides
---

### The farm is constantly rebooting. If I turn logs-on via Hive Shell, what should I pay attention to?
Pay attention to the log lines that appear right before the rig goes offline. Apart from this, you can launch this command via Hive Shell:
`tail -f /var/log/syslog` (you can interrupt the command by pressing the keys Ctrl-C).

When the rig goes offline, Hive Shell will disconnect, and you will see the required lines on the screen.

### How to reduce the GPU power consumption?
To reduce the consumption of your GPUs (when using Hive OS), you can specify the parameters of the core voltage and memory individually for each card.

To do this, go to the **Overclocking** section on your worker and specify the necessary values in the overclocking profile. Please note that in the **Memory Status** column you can indicate both the status index 0, 1, or 2, and the voltage in mW.

Also, to reduce power consumption, you can use the aggressive undervolting mode:

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu1.png">

### How to check internet on GPU rig?
In order to check the availability of the Internet on your rig, you need a screen and a keyboard for a physical connection to the rig. After the Hive OS loading is complete, enter the command `net-test`. After you apply it, you will see the availability status of Hive OS servers.

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu2.png">

### What is error 511?
In most cases, this error occurs due to the malfunctioning of the video card's riser. Please check the power connector on the riser for a burnt wire, and replace the riser.

### What is DPM on AMD video cards?
DPM is a table of core frequencies and the corresponding voltages of these frequencies. This information can be checked with the `amd-info` command. The video card changes the core frequencies in steps according to this table.

The manufacturer with a large margin sets the voltages for each stage of the core frequency. Our task is to select the lowest voltage value for the selected core frequency specified in DPM, but at the same time to ensure that the card continues to mine steadily. In this way we get reduced consumption without losing performance. This is downvolt. Here are the examples:

- DPM 3 825
- DPM 4 875
- DPM 5 925

By default, Hive OS uses the value DPM 5. The factory value on Windows is DPM 7 Windows. Specifying core frequency works, but not on all the cards. But using the DPM value definitely works on all video cards.

### How can rigs be merged /moved to another farm?
Go to the rig's **Settings**:

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu3eng.png">

Scroll down and click the **Advanced settings** button:

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu4eng.png">

Select the desired farm from the drop-down list and click the **Transfer** button.:

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu5eng.png">

### How to launch mc on the rig
To start the mc editor, launch Hive Shell on your worker. Then enter the `mc` command.

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu6.png">

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu7.png">

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu8.png">

### How can I check if the rig is really frozen using Hive-Shell?
Using Hive Shell, enter the **working rig located in the same local network as the frozen one**.

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu9.png">

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu10.png">

Enter this command: `ssh user@”Ip_address_of_the_frozen_rig”`:

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu11.png">

Then enter your password for this rig. The latest IP address of the rig can be checked in the Hive OS dashboard . Now you can check if the rig has really frozen or turned off, or if it is a glitch of the web-server.

The `exit` command will every time bring you back in the chain.

### What is LA (Load Average)?
LA is the number of processor cores required to perform all current tasks. If you have Celeron G3930 with two cores, then LA 2 indicates 100% system load. For Ethash, this is very abnormal, but for modern algorithms — it is okay.

The maximum value of LA can be anything. This is the length of the queue to the processor, expressed in the number of cores of this processor. LA has always been counted as the number of computing devices required to complete the entire current task queue.

When mining Beam and Cuckoo on weak processors, LA can reach up to 3-4. If you don't like the red color of the indicator, you can always set the threshold value here:

<img src="https://lbd.hiveos.farm/kbase/images/gpu/gpu12eng.png">

Three values: LA now / average LA per 5 minutes / average LA per 15 minutes .
