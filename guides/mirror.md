---
title: Hive packages repository mirror setup
path: /guides-mirror
category: Guides
---

If you have local web server on your farm with packages repository you can set its URL in farm settings so the rigs will update from your server. This is useful for faster updates and in order to preserve traffic.

Any rig from your network can be turned into such local server.

First don't forget to run the `disk-expand` command, so that you will have enough space for packages. Several Gb are required.

Then manually install mirror package, it will install web server as well:

`apt install hive-opt-repomirror`

After this the Nginx web server should be running on this machine.

Sync is done once per hour.

You can run it manually with `/hive/opt/repomirror/updaterepo`, also there is log file of cron job here **/var/log/hive-repo-sync.log**.

If you want to use alternate reference server to download from, you can create **/hive-config/repo-sync.url** with URL of that server, like **http://your.another.mirror/repo/binary/**.

In your browser you can check mirror by opening **http://your.rig.ip/repo/binary/**, if it's ok set this URL in farm settings.
