title: Getting Started with Hive OS — Adding A Custom Miner

## Getting Started with Hive OS — Adding A Custom Miner
<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/header.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/header.png"
  />

Hive OS supports several popular miner algorithms, but not every single one. For this purpose we added a new feature called Custom Miner Integration that allows users to add a miner that’s not “baked” into the distribution image of the OS. You have the option to either install a pre-created package or create one yourself. But in this guide we’ll mostly cover the steps required to install a pre-created package.

### Installing A Custom Miner
Start by going to the <a href="http://download.hiveos.farm/custom/">custom miner download</a> page and simply copy the URL to the file.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/custom_miners.png?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/custom_miners.png"
  />

_Custom miner repository_

To install a custom archive manually on the rig you can download it and unpack it to `/hive/custom` folder. Note that even though you did copy it locally you will still need the URL for the Flight Sheet to work.

## Setting Up The Flight Sheet
We covered the process of creating a Flight Sheets and Wallets, which you will also require, in one of our [previous articles](getting_started/start_dashboard_setup.md), so we won’t go into the details, assuming you already know how to do it.

Got to the **Flight Sheets** tab in your farm’s Dashboard. In the **Add New Flight Sheet** section, start filling in the following fields:

* __Flight Sheet Name__ — use a name that will describe the Flight Sheet’s purpose best. For example, _ETH on nanopool using claymore_; _flypool zcash on dstm_; etc.
* __Coin__ — this works like a filter, you can see only wallets, pools and miners only for the chosen coin. For example, if you choose ETH the filter will hide all your pre-created wallets and pools that don’t support or aren’t associated with that coin.
* __Wallet__ — choose a wallet for this Flight Sheet. These are the wallets you created in the Wallets tab.
* __Pool__ — select **Configure in miner** for the **Custom** miner option in the **Miner** field to show-up.
* __Miner__ — select **Custom** and then click the **Setup Miner Config** for miner specific settings then fill in the necessary fields. Note, each miner can have a different set of parameters and required fields.

Because we’re setting up a Custom miner we need to manually configure these settings via the **Setup Miner Config** window. Click **Setup Miner Config** button in **Miner** and fill in the following fields:

* __Miner name__ — use the same name as the package. For example: if the package name is `phoenixminer-3.5_c.tar.gz`, then the miner name **must be** `phoenixminer`.
* __Installation URL__ — the direct URL to the miner package.
* __Hash algorithm__ — choose the hash algorithm for the miner.
* __Wallet and worker template__ — this will depend on your miner specific configuration
* __Pool URL__ — the pool’s address and also the pool specific settings like passwords, wallets, and ports. Note, we recommend typing the values in the following format: `WALLET: %WAL%, WORKER:%WORKER_NAME%`. Also all values should be separated by a comma.
* __Pass__ — `x` a default setting, usually left as is.
* __Extra config arguments__ — these are miner specific and are optional. Note, these may be important in certain cases, so we recommend reading your miner’s documentation for additional details.
* Click **Apply Changes** and you’re all done

Once you’re done click the **Create Flight Sheet** button. You can now apply the Flight Sheet you’ve created.

### Example: Adding and Setting-up Phoenix Miner
Now that we showed you how to setup a custom miner, let’s put it to practice by setting-up Phoenix Miner 3.5c on <a href="https://www.hiveon.net/">Hiveon Pool</a> using the ethash miner algorithm as an example.

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/custom_fs.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/custom_fs.gif"
  />

_Custom miner Flight Sheet_

In the **Add New Flight Sheet** section, start filling in the following fields:

* __Coin__ — _ETH_
* __Wallet__ — _Example ETH_ wallet we created.
* __Pool__ — select **Configure in miner** for the **Custom** miner option in the **Miner** field to show-up.
* __Miner__ — select **Custom** and then click the **Setup Miner Config** for miner specific settings then fill in the necessary fields. Note, each miner can have a different set of parameters and required fields.
* __Flight Sheet Name__ — _Phoenix on Hiveon_

<img
  src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/custom_conf.gif?sanitize=true" data-canonical-src="https://github.com/minershive/hiveon-kb/raw/master/images/start_custom_miner/custom_conf.gif"
  />

_Custom miner configuration_

Now we need to configure the miner. Click **Setup Miner Config** button in **Miner** and fill in the following fields:

* __Miner name__ — we’ll call it `phoenixminer`
* __Installation URL__ — adding the URL of the package `http://download.hiveos.farm/custom/phoenixminer-3.5_c.tar.gz`
* __Hash algorithm__ — select `ethash` from the dropdown list.
* __Wallet and worker template__ — type `null`, as we’re using an ETH wallet we already have.
* __Pool URL__ — we’ll be using <a href="https://www.hiveon.net/">Hiveon pool</a>:

`POOL: eu-eth.hiveon.net:4444, WALLET: %WAL%, WORKER:%WORKER_NAME%`

`POOL: eu-eth.hiveon.net:14444, WALLET: %WAL%, WORKER:%WORKER_NAME%`

* __Pass__ — set to `x`
* __Extra config arguments__ — in our case we leave this field blank.
* Click **Apply Changes** and you’re all done.

### How to build your own package?
Hive 2.0 supports custom miners that you can “cook” yourself and you’ll need to implement using several easy scripts in order to get your miner to work and send stats to Hive. Please take existing integrations as a starting point.


The integration doc is <a href="https://github.com/minershive/hiveos-linux/blob/master/hive/miners/custom/README.md">here</a>. To install custom archive manually you can just unpack it to /hive/miners/custom.

To install it from URL run `/hive/miners/custom/custom-get url-to-your-superminer`. Use “-f” argument at the end to reinstall it: `/hive/miners/custom/custom-get url-to-your-superminer -f`. Since v0.6 for updating Custom miner, it is just enough to change URL in your Flight Sheet for the new one.

Additionally, you can refer to the <a href="https://github.com/minershive/hiveos-linux/tree/master/hive/custom">custom miner integration Readme on GitHub</a> for script templates and examples on how to create and integrate your own miner.
