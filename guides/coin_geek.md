---
title: How to mine GeekCash with Hive OS
category: Guides
---

<img src="https://lbd.hiveos.farm/kbase/images/DQmdua5LfZqEeuho8faPdsh2qt5WtzR57Yr9EXLnAY9L8bo.png">

To mine GeekCash with Hive OS you need to do the following:
1. Add the address of your GeekCash wallet, where the mined coins will be sent:
<img src="https://lbd.hiveos.farm/kbase/images/DQmZworYwjUqAuhXi9pTqV5aiuZLxK2Cho5jMjdjagwvn9L.png">

2. Create a Flight Sheet, choose there a coin and a wallet, and select "Custom miner" as a miner. Click **Setup Miner Config**:
<img src="https://lbd.hiveos.farm/kbase/images/DQmV2xvAt1FkDAGa5gG86aNU4Eit4JD5z8y3qYAwQ5Qvi7U.png">

3. For Nvidia cards, specify the following in the miner configuration:
<img src="https://lbd.hiveos.farm/kbase/images/DQmae8Gsror11SpLWAxPjdFcbMnJTxmE3bkE82HNZHFd3e6.png">

- Miner name: geekminer
- Installation URL: http://files.miner.ninja/geekminer.tar.gz
- Hash algorithm: geek
- Wallet and worker template: %WAL%
- Pool URL: stratum+tcp://geek.miner.ninja:5555
- Pass: x
- Extra config arguments: -i 21

Save the miner configuration and create a Flight Sheet: **Create Flight Sheet**.

***Important:*** when launching the GeekCash miner, wait until the miner is downloaded (2-3 minutes, everything depends on your Internet speed).

4. For AMD cards, specify the following in the miner configuration:
<img src="https://lbd.hiveos.farm/kbase/images/DQmTnMKg6E3TToA3cdsNPTX5DcbWoU33eygUkogBRqqcE3n.png">

- Miner name: sgminer_geek
- Installation URL: http://files.miner.ninja/sgminer_geek.tar.gz
- Hash algorithm: geek
- Wallet and worker template: %WAL%
- Pool URL: stratum+tcp://geek.miner.ninja:5555
- Pass: x
- Extra config arguments: -g 2

Save the miner configuration and create a Flight Sheet: **Create Flight Sheet**.

***Important:*** when launching the GeekCash miner, wait until the miner is downloaded (2-3 minutes, everything depends on your Internet speed).

### A recommended pool for mining GeekCash - Geek.Miner.Ninja
- Only 0.5% pool fee
- A pre-configured .BAT-file with GPU and CPU miner
- To increase stability, the miner automatically reboots every 30 minutes.

***Discord:*** https://discord.gg/cguh8pz

***GeekCash Discord:*** https://discord.gg/XwkgTxr

***Website:*** https://geekcash.org

***Wallet:*** https://geekcash.org/#wallets

***Nvidia GPU miner with .BAT-file:*** http://files.miner.ninja/geekminer.zip.

***CPU miner:*** http://files.miner.ninja/cpuminer.zip.

***Command line for Nvidia GPU miner:*** `geekminer.exe -a geek -o stratum + tcp: //geek.miner.ninja: 5555 -u {WALLET-ADDRESS}`

***Command line for CPU miner:***
`cpuminer.exe -a geek -o stratum + tcp: //geek.miner.ninja: 3333 -u {WALLET-ADDRESS}`
