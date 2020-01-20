title: Hive Shell

## Hive Shell
<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/8580c113d2e085d26be948283c7922532a00d90f.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="96">

### About Hive Shell
Almost a year ago Hive OS introduced the function of remote access to workers via [Teleconsole](https://forum.hiveos.farm/t/teleconsole/3968). This service immediately became very popular among our users for solving various remote maintenance tasks.
Unfortunately, it has become very difficult to use this service lately because of instability in the service’s work, so the Hive team has begun to look for an alternative solution, which we are very pleased to present to you.

### Introducing Hive Shell
Hive Shell provides remote access to your workers using the Hive OS network infrastructure, and also has its own unique features such as access via an SSH client and console sharing. Let’s take a closer look at Hive Shell.

### How to use Hive Shell
In the web interface in the “Remote Access” there are two items “Hive Shell Start” and “Hive Shell Stop”.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/2/2718fd40aee03d149d85bb58d3bb32d7e71b79d4.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="226" height="238" class="d-lazyload">

After starting the service through the menu item “Hive Shell Start” you will see the result of the command <img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fa02eab197103fe96142da745133262e42ea8844.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="153" height="32">

The result of this command is a clickable link, clicking on which in the browser tab will open the terminal of the worker.
You can also open the result of the command execution to take advantage of additional command features such as sending a web link to a technician or connecting using an SSH client (which will be discussed separately).

<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/5fa0229f1f913ce1f8267534c34a99922af1a5ee.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="128">

***Attention! Send the access link to your worker only to a person you trust.***

So it works:

<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/dc515fb26c34a078bd34436a3415bdf6fe646695.gif" alt="com-gif-maker" width="330" height="229" class="d-lazyload">

### Run from console
Hive Shell can be launched both from the web interface and from the console. From the Hive Shell console, start the hssh command (valid parameters start | stop | restart).

Start service:
`hssh start`

Stop service:
`hssh stop`

Restart service:
`hssh restart`

### Console sharing
A very important feature of Hive Shell is the ability to share the console. You can watch (or even take part) the actions that are performed by the person with whom you have shared access to the worker through Hive Shell.
Using this function is extremely simple - just open the same link that was shared with another person.
This is how it looks (on the left - Hive Shell is launched in the FireFox browser, on the right - via the PuTTY client):

<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/f/f57bd44c479d05d15743b8a57cd92c30a8b83f69_2_690x313.gif" alt="" width="330" height="149" srcset="https://forum.hiveos.farm/uploads/default/optimized/2X/f/f57bd44c479d05d15743b8a57cd92c30a8b83f69_2_690x313.gif, https://forum.hiveos.farm/uploads/default/original/2X/f/f57bd44c479d05d15743b8a57cd92c30a8b83f69.gif 1.5x, https://forum.hiveos.farm/uploads/default/original/2X/f/f57bd44c479d05d15743b8a57cd92c30a8b83f69.gif 2x" data-small-upload="https://forum.hiveos.farm/uploads/default/optimized/2X/f/f57bd44c479d05d15743b8a57cd92c30a8b83f69_2_10x10.png">

All actions performed in one console are also displayed in the other.

### Using SSH client
With Hive Shell, you can connect to your worker using an SSH client such as PuTTY.

#### Private key generation
To do this, you need to perform a one-time procedure - generate your private keys which can be done by using the program that is part of the PuTTY package - PuTTYgen (PuTTY Key Generator).

<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/cd4859a8da5bbf8bf77723734fc1e203f6bbc14e.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="125" height="125">

Start PuTTYgen and click the “Generate” button, randomly move the mouse cursor over the application field until the progress bar reaches the end.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/4/488a4e137f3448711ba495bfcaef8ef8fef01374.gif" alt="" width="330" height="323" class="d-lazyload">

Then click the “Save private key” button, you can ignore the warning about saving without a password by clicking “Yes” and save the key on your computer.

#### Configure SSH Client
Next, you need to configure your SSH client using the generated private key.
Run PuTTY, open the Connection section on the left and the SSH subsection in it and get Auth, on the right there will be a file selection menu where you need to select the private key saved in the previous step.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/7/79ab92e1bf5e4bec5ea1a7b2edfec51f5ff560c5.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="157" class="d-lazyload">

After that go to the Session section and save our profile. To do this, set the Host Name - `shell.hiveos.farm` and the name of the profile, for example - Hive Shell and press the "Save" button to save.

<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c2d497fea2e00d1d5ffd564d7b88c265d15e553e.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="226" class="d-lazyload">

In short, it looks like this:

<img src="https://forum.hiveos.farm/uploads/default/original/2X/3/377272f7d7d5570769117fdcf1377e98697c2848.gif" alt="" width="312" height="307" class="d-lazyload">

#### Launch PuTTY
The next step is very simple.

- start Hive Shell and wait for a successful start <img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fa02eab197103fe96142da745133262e42ea8844.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="153" height="32">
- open the result of the command
<img src="https://forum.hiveos.farm/uploads/default/original/2X/3/315f51cc76b82b56a142c1cb79189e551d2beb4d.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="136">
- copy session name Hive Shell
<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/9fadda648e24a57709fc8aa51d35504385f8caa0.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="140">
- launch PuTTY, open the previously saved Hive Shell profile and, using the right mouse button, insert the saved session name as the user name and hit Enter
<img src="https://forum.hiveos.farm/uploads/default/original/2X/4/40919285c83918465ff126f5a87c0641043c4788.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="53">
- that’s it! Pretty simple, isn’t it?

<img src="https://forum.hiveos.farm/uploads/default/original/2X/0/05a5d4e929357b43263cb5db2f57a0df83ae7a11.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="330" height="208" class="d-lazyload">
