---
title: RX Boost - AmdMemTweak
category: Guides
meta_description: Learn how to use the AMDMemoryTweak utility.
---

Thanks to the efforts of the programmer under the nickname Eliovp, the AMDMemoryTweak utility is available on [Bitcointalk](https://bitcointalk.org/index.php?topic=5123724.0) and [Github](https://github.com/Eliovp/amdmemorytweak), which allows you to work with the GDDR5 and HBM2 video memory timings of video cards on the AMD platform on the fly.

AmdMemoryTweak allows you to achieve the best speed when mining on memory-intensive algorithms on AMD video cards. Many people call it an analogue of the program ETHEnlargment Pill, which significantly increases the performance of Nvidia video cards with GDDR5X memory. In fact, this is certainly true, but to achieve the effect, the user’s level of training should be much higher. AmdMemoryTweak is especially useful for video cards of the Vega series with HBM2 memory.

### Common usage
In amdmemorytweak, you can use the following commands:
`--gpu | --i` [comma-separated gpu numbers] - selection of the video cards involved;
`--current` - shows current timings;
`--help` - displays a list of available commands

Read/applying parameter must be done after overclocking (setting memory clock).

###  GDDR5
Let’s look to GDDR5 settings which we can get.
Get current settings:

`amdmemtweak --current`

Results for custom BIOS RX570 equipped Elpida memory:
<pre><code>
GPU 0:  Ellesmere [Radeon RX 470/480/570/570X/580/580X/590]     pci:0000:01:00.0
   Elpida GDDR5
PMG:      CKSRE: 2        CKSRX: 2        CKE_PULSE: 10   CKE: 10         SEQ_IDLE: 7
CAS:      CL: 20          W2R: 15         R2R: 5          CCDL: 2         R2W: 26         NOPR: 0         NOPW: 0
RAS:      RC: 60          RRD: 5          RCDRA: 22       RCDR: 24        RCDWA: 13       RCDW: 12
MISC:     RFC: 97         TRP: 22         RP_RDA: 24      RP_WRA: 44
MISC2:    WDATATR: 0      T32AW: 0        CRCWL: 22       CRCRL: 3        FAW: 0          PA2WDATA: 0     PA2RDATA  : 0
M3(MR4):          RAS: 38
DRAM1:    RASMACTWR: 6    RASMACTRD: 5    ACTWR: 2        ACTRD: 3
DRAM2:    RAS2RAS: 13     RP: 5   WRPLUSRP: 7     BUS_TURN: 3
Refresh:          tREF: 30
</code></pre>
Getting current settings is useful as a reference.

Yes, there are too many settings, and it is difficult to understand for an unprepared user.
Available options for GDDR5 memory are:
<pre><code>
--CKSRE|--cksre [value]
--CKSRX|--cksrx [value]
--CKE_PULSE|--cke_pulse [value]
--CKE|--cke [value]
--SEQ_IDLE|--seq_idle [value]
--CL|--cl [value]
--W2R|--w2r [value]
--R2R|--r2r [value]
--CCDL|--ccdl [value]
--R2W|--r2w [value]
--NOPR|--nopr [value]
--NOPW|--nopw [value]
--RCDW|--rcdw [value]
--RCDWA|--rcdwa [value]
--RCDR|--rcdr [value]
--RCDRA|--rcdra [value]
--RRD|--rrd [value]
--RC|--rc [value]
--RFC|--rfc [value]
--TRP|--trp [value]
--RP_WRA|--rp_wra [value]
--RP_RDA|--rp_rda [value]
--WDATATR|--wdatatr [value]
--T32AW|--t32aw [value]
--CRCWL|--crcwl [value]
--CRCRL|--crcrl [value]
--FAW|--faw [value]
--PA2WDATA|--pa2wdata [value]
--PA2RDATA|--pa2rdata [value]
--RAS|--ras [value]
--ACTRD|--actrd [value]
--ACTWR|--actwr [value]
--RASMACTRD|--rasmactrd [value]
--RASMACWTR|--rasmacwtr [value]
--RAS2RAS|--ras2ras [value]
--RP|--rp [value]
--WRPLUSRP|--wrplusrp [value]
--BUS_TURN|--bus_turn [value]
--REF|--ref [value]
</code></pre>
For users who use cards with custom BIOS and timings settings, as a rule, will not affect the hashrate growth.
However, using the --REF parameter, you can achieve a gain of up to 5% on algorithms dependent on memory performance. Good start for REF parameter is 30.
Command line will look as:

`amdmemtweak --REF 30`

Also interesting may be the parameters `--RC` and `--RFC`.

### HBM2
HBM2 memory used in Vega series cards. For this cards available options is:
<pre><code>
--CL|--cl [value]
 --RAS|--ras [value]
 --RCDRD|--rcdrd [value]
 --RCDWR|--rcdwr [value]
 --RC|--rc [value]
 --RP|--rp [value]
 --RRDS|--rrds [value]
 --RRDL|--rrdl [value]
 --RTP|--rtp [value]
 --FAW|--faw [value]
 --CWL|--cwl [value]
 --WTRS|--wtrs [value]
 --WTRL|--wtrl [value]
 --WR|--wr [value]
 --RREFD|--rrefd [value]
 --RDRDDD|--rdrddd [value]
 --RDRDSD|--rdrdsd [value]
 --RDRDSC|--rdrdsc [value]
 --RDRDSCL|--rdrdscl [value]
 --WRWRDD|--wrwrdd [value]
 --WRWRSD|--wrwrsd [value]
 --WRWRSC|--wrwrsc [value]
 --WRWRSCL|--wrwrscl [value]
 --WRRD|--wrrd [value]
 --RDWR|--rdwr [value]
 --REF|--ref [value]
 --MRD|--mrd [value]
 --MOD|--mod [value]
 --XS|--xs [value]
 --XSMRS|--xsmrs [value]
 --PD|--pd [value]
 --CKSRE|--cksre [value]
 --CKSRX|--cksrx [value]
 --RFCPB|--rfcpb [value]
 --STAG|--stag [value]
 --XP|--xp [value]
 --CPDED|--cpded [value]
 --CKE|--cke [value]
 --RDDATA|--rddata [value]
 --WRLAT|--wrlat [value]
 --RDLAT|--rdlat [value]
 --WRDATA|--wrdata [value]
 --CKESTAG|--ckestag [value]
 --RFC|--rfc [value]
</code></pre>
The selection of good parameters for this type of memory is a more subtle process, but the hashrate gain is more significant with respect to GDDR5.
Example of usage for Vega 56 with custom BIOS:

`amdmemtweak --CL 16 --RAS 30 --RCDRD 12 --RCDWR 5 --RC 44 --RP 10 --RRDS 3 --RRDL 5 --RTP 5 --FAW 20 --CWL 7 --WTRS 4 --WTRL 9 --WR 16 --WRRD 1 --RDWR 19 --REF 17550 --MRD 8 --MOD 15 --PD 8 --CKSRE 10 --CKSRX 10 --RFC 300`

With above settings achieved 50MH/s when mining at ethash algorithm.

### Hive RXboost
The amdmemtweak utility is included in the Hive OS distribution. With Hive update to v0.6-45 new option appears in AMD OC settings. This parameter allows you to apply the so-called rxboost tweak that became known after the appearance in the Claymore’s Dual ETH Miner v14 and can be applied to the RX 4xx/5xx series cards. In other words it’s the same as execution `amdmemtweak` with `--REF parameter`.

<img src="https://lbd.hiveos.farm/kbase/images/forum/dd4564ddc1ebfe5aee3530837c35220d4a099db8.png">

When the field is empty (default value) then Refresh Rate is not applied. To apply the value of all the cards, enter the same value. If you need to apply individual values for different cards, enter values separated by spaces.
Here some short video how to use this feature:
- <a href="https://www.youtube.com/watch?v=0zJsU07Lgvc">RX Boost in Hive OS: get more from your RX cards</a>

<a href="http://www.youtube.com/watch?feature=player_embedded&v=0zJsU07Lgvc
" target="_blank"><img src="http://img.youtube.com/vi/0zJsU07Lgvc/0.jpg"
alt="RX Boost in Hive OS: get more from your RX cards"></a>
