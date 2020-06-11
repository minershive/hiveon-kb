---
title: NiceHash
category: Guides
---

<img src="https://lbd.hiveos.farm/kbase/images/forum/1fs7ux2lalf8.png">

One of the most popular questions we get from new users is if Hive OS supports NiceHash, and how to set it up.
If in short, yes, Hive OS works with this service perfectly.
And regarding the setting-up process, we will explain the details further.

First of all, you should know that using the NiceHash service, you do not mine cryptocurrency in the usual sense of mining. This service buys your power and pays you a reward in Bitcoins.

In turn, Hive OS includes all the programs essential for working with this service on both AMD and Nvidia cards.

This service can make payments to both external and internal wallet. In most cases, payment to an internal wallet is more convenient, so we will focus on it in our guide.

In the rig's menu, there are ready-to-use templates for NiceHash:
<img src="https://lbd.hiveos.farm/kbase/images/forum/iq1dhcc4nq6u.png">

After you click the template, you just have to replace the wallet address with your own:

<img src="https://lbd.hiveos.farm/kbase/images/forum/6n0vbcqy513e.png" />

Where to get this address? In your NiceHash account, in the “Wallets” menu.

The second thing you need to know is the address and port for a specific algorithm.
Where to get them? Go to [this page](https://www.nicehash.com/stratum-generator) and select algorithm and location:

<img src="https://lbd.hiveos.farm/kbase/images/nice/Screenshot_15.png" />

And here you go:

<img src="https://lbd.hiveos.farm/kbase/images/nice/Screenshot_16.png" />

The NiceHash service supports separation by rigs so you can specify the address in the following format:

**YourNiceHashBTCaddress.Worker**

- YourNiceHashBTCaddress - the address of your Bitcoin wallet on the service
- Worker - the name of a rig (of a worker)

In Hive OS you can use macro substitutions for convenience:
- %EWAL% - for miners Claymore Dual, Etherminer (algorithm DaggerHashimoto)
- %ZWAL% - for miners Claymore ZCash, ewbf, dstm (algorithm Equihash)
- %DWAL% - for all other miners and algorithms
- %WORKER_NAME% - the name of a rig (of a worker)
