---
title: Version Downgrade
---

## Version Downgrade
Sometimes after update something is not working for you and you’d like to go back to the previous version. Though it can’t be done via web panel, you can do it manually either from SSH shell or “Linux Command Execute” on the web.

Starting from version 0.5-67 you can just run `selfupgrade 0.5-67`.
***Note:*** this method will not work on the versions lower than 0.5-67.

### Manual Downgrade
Go to the following address and you’ll see the list of available versions: http://download.hiveos.farm/repo/binary/.

OK, you found the version you want, let’s say package “hive_0.5-07_all.deb”. What you want is to see the version, it is “0.5-07” in this example.
The following command will install selected version: `apt-get install -y --allow-downgrades hive=0.5-07`.

***NOTE:*** Version downgrade may lead to some bug as setup scripts are not intended for this. But if you don’t rollback between major versions, like from 0.5 to 0.4. then it will work for 99%.

If the above command replies that there is no such version, try to do the following:
`apt-get update -o Dir::Etc::sourcelist="sources.list.d/hiverepo.list" -o Dir::Etc::sourceparts="-" -o`

`APT::Get::List-Cleanup="0"`

If for some reason the above method does not work, then there is another option to download the package itself and install manually from the file.
Something like this:

`cd /tmp`

`wget http://download.hiveos.farm/repo/binary/hive_0.5-07_all.deb`

`dpkg -i hive_0.5-07_all.deb`
