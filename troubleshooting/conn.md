---
title: Connection problems
---

The common question is: my rig is mining, but it’s offline in Hive.

A bit of explanation. There is an agent on a rig that sends stats every 10 seconds to server. It starts as soon as the system boots. So your rig may be running but the agent fails to reach server for some reason. Or the common problem is a dead filesystem and agent just can’t save temp files to construct its package.

For network diagnosis there is test script, just run `net-test`. It will quickly ping and try to reach server. Take manual actions if you need more information.

### Manual checking instructions
First in all ensure your network connection:
- Check if LEDs are blinking on the network card
- Check if you have internet on the other devices in this net like you phone or laptop
- Try to open some site from the rig with the browser
- Check your connection by pinging some server, you should run `ping google.com` for instance

These are very basic actions you may take.

The following is what we actually do on the particular rig when it has such problem:
- `ping hiveos.farm` to check if Hive server is reachable
- `mtr hiveos.farm` to check if the network has any packet loss
- `time curl http://hiveos.farm` to check if HTTP ports are open and there is no significant lag

But the really-really first thing we recommend you to do is opening `agent-screen`. It will show you what it tries to send and gives you some hint what’s wrong. Like here:
<img src="https://lbd.hiveos.farm/kbase/images/forum/nvxqh2a34xub.jpg">

There is obviously some problem with server connection, to investigate this you might do all the upper stuff.

Here is how the very bad situation with your internet looking. Very high packet loss:
<img src="https://lbd.hiveos.farm/kbase/images/forum/iod0sqwp8nhm.jpg">

This is a good command to test real times of opening the website. So you can see how much does it take to connect to server. If the value is high, like several seconds, then you have a bad connection:

`for i in {1..10}; do time curl -s https://hiveos.farm > /dev/null; done`

To inspect the mirrors please try to “curl” api urls like:

`curl  http://api.hiveos.farm`

`curl  https://api.hiveos.farm`

`curl  http://amster.hiveos.farm`

`curl <...other urls listed in rig mirror selection>`
