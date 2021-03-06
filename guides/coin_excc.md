---
title: How to mine EXCC with Hive OS
category: Guides
meta_description: Learn how to mine the EXCC coin with Hive OS - it is very easy.
---

Mining EXCC with Hive OS is very easy and it can be done with only a few clicks.

***Step 1.*** Log in to your farm. The first thing you need to do is adding a new Wallet:
<img src="https://lbd.hiveos.farm/kbase/images/support/hive1.png">

Please mind that you will have to create ExchangeCoin coin as there is no EXCC built in Hive OS (yet). Just start typing ExchangeCoin in the **Coin** field and the system will let you save a new coin. The address is your EXCC address where you want your mined coins to be sent. We strongly recommend using Exilibrium software for this purpose.

***Step 2.*** Once you've created a Wallet and new coin, the next step is to create a new Flight Sheet. Click on the Flight Sheets from Hive OS menu and fill it as on the below example:
- Coin - pick ExchangeCoin (if it's not there it means you didn't create it properly during the Step 1)
- Wallet - pick the Wallet you've just created recently
- Pool - pick **Configure In Miner**
- Miner - select lolMiner and click **Setup Miner Config**

<img src="https://lbd.hiveos.farm/kbase/images/support/mceclip0.png">

***Step 3.*** Now you will see lolMiner configuration window, just fill it as on the below example:
- Wallet and worker template - %WAL%.%WORKER_NAME%
- Coin - EXCC
- Pool server: 35.176.212.123
- Port: 3052
- Pass: x
- Extra config arguments: You can leave it blank but going with lolMiner's author recommendation you could use: --devices AUTO
- Version: The latest

<img src="https://lbd.hiveos.farm/kbase/images/support/mceclip2.png">

***Step 4.*** Once you are done, just go back to your Workers list, check your workers, click Rocket icon from the top and choose your freshly made Flight Sheet.

<img src="https://lbd.hiveos.farm/kbase/images/support/mceclip3.png">

Happy mining!
