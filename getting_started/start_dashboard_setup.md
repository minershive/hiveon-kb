---
title: Dashboard Basics & Setup
---

## Getting Started with Hive OS — Dashboard Basics & Setup
<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/header.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/header.png"
  />

In our [previous article](getting_started/start_worker_setup.md) we discussed all the various ways you can setup Hive OS onto your workers and how to add them to your Farm’s dashboard. In this article we’ll continue our introduction to Hive and it’s features and show you how to work with it’s key functions starting with Farms.

### Working With Farms
Farm is a group of workers that you combine together to form a separate project. For example, you can have a separate Farm for all your workers or you can create several Farms for different groups of workers within a location, for example, a data center, like “_1st floor rigs_”, “_2nd floor rigs_”, “_rigs on East str_”, etc. The number of Farms per account is unlimited, both yours and those which access was shared with you by other users. Other users can share access to their Farms or even transfer them wholly between accounts. This way it’s easy to set up an entire farm for a client and then transfer full ownership to his account. You can even organize your own farm setup business, if you desire.

### Creating A Farm
Start by clicking the plus button in the top right corner of your dashboard. A **Create New Farm** window will appear. Give your Farm a name and select a time zone. This should be the time zone in which your workers will be located. This is required for the purpose of displaying the proper log time codes. Once done, click the **Save** button and you will be transferred to your new Farm’s dashboard.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/create_farm.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/create_farm.gif"
  />

_Creating a new Farm_

### Farm Access Levels
There are several access levels to a Farm and you can see them at the bottom of the each Farm in the dashboard.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/farms_access.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/farms_access.png"
  />

_List of Farms, both yours and those with shared access_

You can give access to your Farm to other users. For example, you could give Full Access privileges to your admins in order for them to manage everything in your stead. Or you can give the read-only Monitor access privileges to your technical staff that do simple maintenance and monitoring and nothing more.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/add_user.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/add_user.gif"
  />

_Sharing access to your Farm with another user_

Each next level includes permissions from the previous one.

* __Monitor__ — Monitor and Stats, Rig details. Tags can be assigned to limit rigs visibility for trusted account.
* __Tech__ — Overclock, Reboot and Shutdown, Upgrade.
* __Rocket__ — Apply miner and wallet to worker. Create and delete workers.
* __Advanced__ — Execute commands, VPN, Wallets, Tuning.
* __Full Access__ — Password, 2FA, Notifications, Payments, Ownership.

You can give access to your Farm to another user by going to the **Farm** tab then click the **Access** tab. You’ll see the “_No users found so far. You can create one_” message and click either the **create one** or the **Trust user** button. Enter the user’s login, this should be their Hive account login. Select an access level for them from the drop down menu. If you’ve selected the Monitor level, then an additional field with **Tags** will be available. You can share only the workers with selected tags to limit visibility of your other workers. We’ll write more on tags in our next articles.

### Setting-up Wallets
Now that you’ve got yourself acquainted with Farms, you can start setting up your Wallets. Several wallets can be created for any coin you like. In fact, if you plan on mining multiple coins, we suggest creating different wallets that you can later pair with different miners and different pools. When selecting a coin to mine in Flight Sheets, you’ll see that depending on the coin you choose, the selection of wallets will be limited to that specific coin.

To add a new wallet, go the Wallets tab and click the Add Wallet button. You’ll see a pop-up window with the following fields:

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/new_wallet.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/new_wallet.gif"
  />

_Creating new wallet_

* __Coin__ — choose a coin for this wallet from the drop-down list.
* __Address__ — enter your wallet address.
* __Name__ — use a name that will describe the wallet’s purpose best. For example, _Ethereum on Claymore_, _ZEC on CCminer_, etc.
* Click **Create** to save your new wallet.

Once you’re done creating your wallets, go to the Flight Sheets tab.

### Setting-up Flight Sheets
Flight Sheets are your worker’s configuration files that determine its operating mode. Flight Sheets let you create worker settings presets and switch between them on the fly with a few clicks. You can create several combinations of coins, wallets, pools and miners and switch between them on the fly.

When adding a new flight sheet, note that you can only select a coin first, while the other options are grayed out. This is done for convenience. Once you select a coin, you’ll be able to pick a wallet from the list of your pre-created wallets which we added earlier. The selection of wallets will also be limited to those that are associated with the previously selected coin. Same for pools and miners, you can only see those that are associated with that specific coin.

### Creating A Flight Sheet

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/new_fs.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/new_fs.gif"
  />

_Setting up a new Flight Sheet_

In the **Add New Flight Sheet** section, start filling in the following fields:

* __Flight Sheet Name__ — use a name that will describe the Flight Sheet’s purpose best. For example, _ETH on nanopool using claymore_; _flypool zcash on dstm_; etc.
* __Coin__ — this works like a filter, you can see only wallets, pools and miners only for the chosen coin. For example, if you choose ETH the filter will hide all your pre-created wallets and pools that don’t support or aren’t associated with that coin.
* __Wallet__ — choose a wallet for this Flight Sheet. These are the wallets you created in the Wallets tab.
Pool — a pool on which you’ll be mining. Choose a pool from the drop down list. A pop-up window will show up with settings. Additionally, you can change these settings later by clicking **Configure Pool**.
Select Pool Server — a list of available pool servers.
* __Email__ — your pool account email. This option is available on some pools that authenticate users via email, others might not have this setting.
* __Miner__ — choose which miner will be used with this Flight Sheet. Click the **Setup Miner Config** for miner specific settings. You should consult your miner’s documentation for additional details.

Once you’re done click the **Create Flight Sheet button**.

### Selecting Pool Servers
One thing to note about the pools is the order in which you choose the servers. Let’s use **dwarfpool** as an example and say you choose the EU server. The next servers you pick are the next servers your worker will connect to, in case it loses a connection to the EU one, in the order you picked them. For Example, the first server you chose was the EU, then Russia and then China. This will be the exact priority order in which your worker connects to that pool.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/pool_conf.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/pool_conf.gif"
  />

_Selecting pool servers_

### Setup Miner Config
The miner config window will vary depending on the miner you choose. As mentioned before, the selection of miners is limited by the coin chosen. Miners will have Nvidia, AMD or CPU text indicating its compatibility with specific hardware types. This means, if a miner has only Nvidia next to it, then it will work only on Nvidia GPUs, same with AMD and vice versa. CPU indicates that a miner can be run on CPUs.

These parameters can be left alone and the miner will work in its default settings. You may want to change them if, for example, pool servers weren’t selected in the Pool tab, then these settings can be set in the miner config. These are custom settings fields that you can use to override specific parameters, like forks, pool address, wallet strings or hardware config override parameters. We suggest referring to your miner’s documentation for further details.

Once you’re done click the Create Flight Sheet button. Remember, you can have any number of Flight Sheets in your Farm.

### Example: Setting-up Monero on Nicehash
Now that we showed you how to set up your worker, let’s put it to practice by setting-up Monero (XMR) on Nicehash using the CryptoNoghtv7 miner algorithm as an example.

Go to your **Wallets** and click the **Add Wallet** button. In the **New Wallet** window start by typing nicehash into the Coin field, and you should see an entire list of various Nicehash supported algorithms. They are not listed by default in the dropdown list as they’re not actual coins per se. Choose the _Nicehash-CryptoNightV7_ protocol, then enter your Nicehash wallet address. Note, that if you want to see your stats in the <a href="https://www.nicehash.com/dashboard">Nicehash Dashboard</a> you should use the generated wallet address provided when <a href="https://www.nicehash.com/register">registering</a>. You can name your new wallet optionally, then click **Create**.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/wallet_nh.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/wallet_nh.gif"
  />

Continue by setting-up a Flight Sheet in the **Flight Sheets** tab. Choose the now available _Nicehash-CryptoNight_ from the **Coin** dropdown list, then choose the wallet you just created and select a pool. Keep in mind that you can either choose the default pool servers, or select the **Configure in miner** option to input these settings manually. Select your preferred miner or if you clicked the _Configure in miner_ option, then setup that miner manually by clicking the **Setup Miner Config** button.

Below is an example of how we setup our second miner for CPU mining on a rig. Your settings may vary depending on the miner you choose, servers, algorithms, coins, etc. But for the sake of this example we opted to mine Monero (XMR) using our rig’s CPU. We already have a GPU miner, so we needed to add our CPU miner to the same Flight Sheet. We did this only on one of our worker, thus creating a rig specific config.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/nh_monero_fs.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/nh_monero_fs.gif"
  />

_Adding a second miner_

To add a second miner to a specific worker, go to that worker and click the Flight Sheet tab then select your current Flight Sheet and click the triple dot button and then **Edit**. Click **Add Miner** and start filling in the fields:

* __Coin__ — Nicehash-CryptoNightV7
* __Wallet__ — the wallet we created using our Nicehash deposit address
* __Pool__ — Configure in miner
* __Miner__ — we chose the `cpuminer-opt`

Because we decided to choose our server and miner settings manually, we need to configure these setting via the **Setup Miner Config** window. Click **Setup Miner Config** button in **Miner** and fill in the following fields:

* __Hash algorithm__ — choose `cryptonightv7 — Monero (XMR)` from the dropdown list
* __Wallet and worker template__ — `%WAL%.%WORKER_NAME%:x` these template parameters will automatically substitute, so we leave them as they are
* __Pool URL__ — `stratum+tcp://cryptonight.eu.nicehash.com:3355` our server of choice
* __Pass__ — `x` a default setting, left as is
* __Config override__ — `“threads”: 4 “cpu-affinity”: 0`

Note that the threads number will vary depending on the number of cores your CPU has. In our case it’s 4. Generally **Config override** can be left blank in most cases

* Click __Apply Changes__ and you’re all done

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/miner_conf.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/miner_conf.gif"
  />

_Miner Config settings_

For more details regarding Nicehash and it’s fine tuning, please refer to their <a href="https://www.nicehash.com/help">Help</a> section.

Continue following the instructions below to apply your newly created Flight Sheet to your worker.

### Start Mining
You can now apply the Flight Sheet you’ve created. You have two options of applying the Flight Sheet to your worker. First, by going to your **Workers** tab then choosing a specific worker and going to the Flight Sheet tab in a worker’s menu and clicking the rocket button on the right side of the specific Flight Sheet you want to apply.

The second way is by going to the **Workers** tab, then clicking the checkboxes on the left side of the workers to which you want to apply the Flight Sheet. You should see a rocket icon appear in the menu bar in the top right corner.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/cp.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/cp.png"
  />

_Control panel_

Click it, and you should see a window with the number of workers you chose and a list of all your Flight Sheets.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/launch_fs.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/launch_fs.png"
  />

_List of selected workers and available Flight Sheets_

Choose the Flight Sheet you want to apply and click the **Apply** button. You should see a message telling you that the Flight Sheet command was sent to the worker. In a few seconds your workers should apply the changes and you should see a `Config applied` message in the activity logs in the farm’s Overview tab.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/activity_log.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_dashboard_setup/activity_log.png"
  />

_Farm’s activity logs_

You’re all done! Your rig should start mining, sending data to your dashboard and you should now see its metrics in real-time.
