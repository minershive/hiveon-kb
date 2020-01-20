---
title: Security
---

## Security
To change system password for user (for SSH and VNC also) please use the following command: `hive-passwd yournewsecurepass`.

Usually you rig is connected to the internet through the router. In this case you just relax and enjoy. If your rig is exposed to outer world or even a large internal network then you should bother about security. Or you will find you rig mining to other wallet or some hidden CPU or even GPU miner.

Change SSH password. This is easy. Being in terminal windows type: `passwd user`.

It will ask you for a new password. You change password for user as you can’t login as root by default using SSH. If you forward your SSH 22 port to through router, it is recommended to use another external port, like 2222. Because 22 port is scanned a lot.

Another open service is VNC. You should edit `/hive-config/vnc-password.txt` to change default password. You can set your own or delete default first line then VNC will be inaccessible at all.

***ShellInABox.*** It should be disabled also if you have default passwords.

`systemctl stop shellinabox`

`systemctl disable shellinabox`
