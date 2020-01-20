---
title: Custom miner
---

## Custom Miner

### How to use custom miners
***Updated for HiveOS Linux client v0.6 series***

Hive supports other miners which are not listed on the web. Hive enthusiasts have created custom packages which can be used with Hive. To use it you need to select “Custom miner” when you create Flight Sheet and paste miner’s URL where to download it.

The list of known and available packages is here:
http://download.hiveos.farm/custom/

### How to build your own package
Hive supports custom miners which you can cook yourself. You will need to implement several easy scripts to get your superminer to work and send stats to Hive. Please take existing integrations as a starting point.

Here is a doc covering <a href="https://github.com/minershive/hiveos-linux/blob/master/hive/miners/custom/README.md">custom miner integration in Hive OS</a>.

To install custom archive manually you can just unpack it to /hive/miners/custom.

To install it from URL run:

`/hive/miners/custom/custom-get url-to-your-superminer`

Use “-f” argument at the end to reinstall it:

`/hive/miners/custom/custom-get url-to-your-superminer -f`

Since v0.6 for updating Custom miner is it just enough to change URL in your Flight Sheet for the new one.
