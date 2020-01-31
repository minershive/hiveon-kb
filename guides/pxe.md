---
title: Hive OS Deploy PXE - Deploy Hundreds of Rigs
category: Guides
---

## Hive OS Deploy PXE - Deploy Hundreds of Rigs

### Introduction
If you own a large farm with hundreds or thousands of GPU rigs and you are planning to migrate to HiveOS, Hive OS Deploy PXE can significantly reduce migration time and gain complete control over the deployment process.
Hive OS Deploy uses PXE Network Boot technology to deploy HiveOS to your rigs.

System and hardware requirements:
- Any computer running Ubuntu 16.04 (tested)
- Dual-core processor</li>
- Static IP address over cable Ethernet
- At least 4 Gb of RAM
- At least 6 Gb of free disk space

You must set up a DHCP server by adding `next-server` option to CLONEDEPLOY_SERVER_IP (static IP address of host where you install Hive OS Deploy PXE). Read more in “Network infrastructure configuration” section.

### Network infrastructure configuration
Depending on the configuration of your local network, the clients in your network receive IP addresses and other necessary information either dynamically using DHCP or configured statically on each client.

#### LAN with dynamic IP addresses
This is the default case or when you plan to setup a DHCP server anywhere in your network.
Please note you should provide a set of dhcp-options:

- dhcp-server ip address. Example: 192.168.1.1
- dhcp network address. Example: 192.168.1.0
- dhcp addresses range OR network mask. Example: 192.168.1.10-192.168.1.200 OR 192.168.1.0/24 (NOTE: different tools and hardware (routers) has it own syntax)
- dhcp broadcast address. Example: 192.168.1.255
- gateway (also known as router in dnsmasq). Example: 192.168.1.1
- tftp-root (your tftp folder for storing kernels, initrds, pxe configs and binaries). Example: /tftp
- dhcp-boot (PXE binary file PATH relative to tftp-root). Must be `,,CLONEDEPLOY_SERVER_IP`
- dns-server
- next-server (dhcp option 66)

NOTE: you must specify `next-server` with your CloneDeployServer IP address. It’s the only option that you must define if you have a DHCP-server already running.
By default, most routers have predefined dhcp options and the ability to change them, so you must specify next-server option only.

#### LAN with static IP addresses
In case of STATIC network: you must configure dhcp-server and tftp-server anywhere in your network to use PXE technology. For example, you could use dnsmasq - lightweight DNS, DHCP and TFTP server.

#### DHCP configuration examples
See examples of configuration files in the examples/ folder
- dnsmasq: example/dnsmasq.conf
- dnsmasq : examples/same-server.dnsmasq.conf - all-in-one config example dhcp и deploy server on the same computer


### Installation of deploy server
#### Installation procedure
All installation commands and scripts in shell must be executed with root credentials by using `sudo` command.

1. Download the installation package
<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/52e02a72d9b8d5babff66da3b112baae0b79ee13.png" alt="download the installation package"/>

2. Run the installation script
`./install-ubuntu.sh -f`

It will start the installation procedure by downloading and installing the necessary packages.
During the installation, you should answer some questions. Follow these steps:

3.1. Enter the Deploy server’s IP address in prompt window
<img src="https://forum.hiveos.farm/uploads/default/original/2X/6/6730de53d8ea8cde0c403457b3299f6ae6b7a65a.png" alt="3.1"/>

Let’s assume that our host has IP address 192.168.1.2 then you will see:
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d75b793a77119422ff452fe7b6629c08705f7719.png" alt="enter server ip"/>

<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/deeac25b5f9f1c44dfec0d8c9867298bbd767994.png" alt="enabling site clonedeploy"/>

3.2. Prompt default DB connection string with pressing “Enter”
<img src="https://forum.hiveos.farm/uploads/default/original/2X/e/e83165987e6f851d3fc79bdd2b85aca37997aa7c.png" alt="3.2"/>

Default settings will be used if no custom DB is given.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fb5ba087742d5fff6b9ec34d3e92fe2fbe9e7cd6.png" alt="default settings"/>

3.3. Wait until mysql-server sets up, then prompt default root password by empty string (Press Enter).
<img src="https://forum.hiveos.farm/uploads/default/original/2X/7/7546ec0f54e9b5dfb6fabab3c5048de23381d6a5.png" alt="3.3"/>
This screen can appear several times during this step.

3.4. Enter SMB passwords for read-only and read-write roles: password
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d972d62fc0376240330a722fa450cecba502b0e9.png" alt="ro password"/>

<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/985ac3cde5988de56e3c6ac2e154754dacc13176.png" alt="rw password"/>

3.5. Download and update HiveOS image
The latest stable HiveOS image will be downloaded and extracted by default.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/e/e633e65418cb2416432ec63daf9f60a19ba7c7c1.png" alt="3.5"/>

3.6. Wait until the installation finishes the setup and then confirm reboot in the prompt window by entering “y”.

4. The following steps are done through the web interface.

Browse to http://<server_ip>/clonedeploy for example if your server has ip address 192.168.1.2 then type in browser with http://192.168.1.2/clonedeploy
and you will see the login screen:
<img src="https://forum.hiveos.farm/uploads/default/original/2X/3/32a0de42f8fcbaa912e36c5ebf59805a59452882.png" alt="login screen"/>

Login with default credentials:

Login: admin

Password: admin

5. Go to Admin → PXE and press Update PXE settings
<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/831ef78884cc3c2b1d237a6ceb21703b4986a484.png" alt="settings"/>

<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/1/10c90048b8fb5730db6775aa7791c634838c7555_2_775x346.png" alt="PXE"/>

<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c87da50269712077fe82e26ac23b7599f8c27081.png" alt="update PXE settings"/>

6. Go to Admin → “Boot menu” and press “Create Boot Files”

<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/8f38172d6f16e9419aaaaddbaeb5a1f901157d7a.png" alt="boot menu"/>

<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d26760bdd46211032ba988e4233395d2f045820a.png" alt="create boot files"/>

7. Go to Groups → deploy → Computer Properties.

Change the following fields:

<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/5b2b0719d7e2b8816c6541eb51844110fcb7c3e4.png" alt="7"/>

<img src="https://forum.hiveos.farm/uploads/default/original/2X/f/f167942d86049e860c4de7801c9f4a0a240e191c.png" alt="view"/> <img src="https://forum.hiveos.farm/uploads/default/original/2X/f/fba425df09795b391c701a76f25c67e383fd4b3c.png" alt="computer properties"/>

<img src="https://forum.hiveos.farm/uploads/default/original/2X/5/529f1f5f58fc221b878286fa0dd71054172640ef.png" alt="attributes"/>

1. Custom Attribute 2 - NETWORK. Enter your network with netmask, for example 192.168.1.0/24
2. Custom Attribute 3 - GATEWAY. Enter the gateway, for example 192.168.1.1
3. Custom Attribute 4 - HIVEOS_API. Enter hiveos-api url, for example http://api.hiveos.farm
4. Custom Attribute 5 - FARM_HASH. Enter your farm hash, for example 0a188b553e98efba264e7bc61dee

Note: Make sure the checkboxes near these fields are enabled.
<img src="https://forum.hiveos.farm/uploads/default/original/2X/e/e7c39f756392be548ae2cb793bcf1533c22af14f.png" alt="attributes"/>

and click on the “Update Properties” button
<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/9566ee2525b1f086ae985e4b038fc9673d78bd3c.png" alt="update properties"/>

Now the server part installation is over.

#### Checking installation and services
Deploy server contains several packages including dhcp proxy, apache2, mysql and tftpd-hpa.
Apache2 and MySQL - used for the web interface and tftpd-hpa used for TFTP server. So if you want to check the installation and make sure these services are running properly, use the following commands:

for DHCP Proxy: `service cd_proxy status`

for Apache2: `service apache2 status`

for MySQL server: `service mysql status`

for TFTP server: `service tftpd-hpa status`

### Deploy Rigs
#### Prepare to Deploy
You can organize your network according to certain rules.

1. Assign rig name with MAC address
2. Assign rig name with MAC address and IP address

You can import a prepared rigs list. Go to “Computers”
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d9da23421b2deba27adc3dea1e8933a5bc852724.png" alt="computers"/>

and then click the “Upload” button
<img src="https://forum.hiveos.farm/uploads/default/original/2X/4/4802ecf0e60ac6621d7dd4222b5d265b79035153.png" alt="upload button"/>

File format is: rig-001	08:00:27:4A:29:BB	192.168.1.19

Check imported rigs
<img src="https://forum.hiveos.farm/uploads/default/optimized/2X/5/5c84be051b534751325b734d0225de39325b09e7_2_1035x204.png" alt="imported rigs"/>

#### Deploy Task
Click “Task”
<img src="https://forum.hiveos.farm/uploads/default/original/2X/1/1274e00eff02e38e5662744a1ad2a34bb9a447d5.png" alt="task"/>

Then “Click Computer Task” -> Start Computer Task -> select workers for Deploy
<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c85a4496aaba2c7cf40514f583ec52fad44ba838.png" alt="deploy"/>

and press “Deploy Selected”.

Deploy process rig side
<img src="https://forum.hiveos.farm/uploads/default/original/2X/a/a347dd139b206507452b7b5ed95b1a57564acc3e.png" alt="deploy process rig side"/>

Progress can be followed through the browser
<img src="https://forum.hiveos.farm/uploads/default/original/2X/c/c0c4b3960fa4f97391258d582c8e42cc30bc34ec.png" alt="progress"/>

After downloading the necessary files, Hive OS Deploy will flash the Hive image to the storage device
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/db5f35e1e311ace3ea82b3c78ffe17677c5a3a18.png" alt="storage device"/>

After the flashing process, the rig will reboot automatically followed by a boot menu with default target “Boot To Local Machine” which will boot your rig after a 5 second delay
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/dbc4b559b3800af167b664b9c163ded17ab45ad1.png" alt="boot to local machine"/>

When the boot process is done, we’ll be able to see our rig on the Hive Dashboard
<img src="https://forum.hiveos.farm/uploads/default/original/2X/9/927242a593fae6d2743febcdd156509a6c6294dd.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="367" height="77"> <img src="https://forum.hiveos.farm/uploads/default/original/2X/f/f8af9292e0ce833c32634cca4e3c32a7510c44ca.png" alt="%D0%B8%D0%B7%D0%BE%D0%B1%D1%80%D0%B0%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5" width="219" height="82">

### Appendix
- `install-ubuntu.sh` - script for install HiveOS Deploy PXE script options
<img src="https://forum.hiveos.farm/uploads/default/original/2X/8/8b755459accceb0687b5abf3a59c79ba7a17290b.png" alt="script for install HiveOS Deploy PXE script options"/>

- `download.sh` - script for upload new images to HiveOS Deploy PXE
<img src="https://forum.hiveos.farm/uploads/default/original/2X/d/d800f1615dc923d7f1feac51e79a093190026fe9.png" alt="script for upload new images to HiveOS Deploy PXE"/>


- [HiveOS Deploy PXE repository](https://git.tor.ph/hivedeploy/cd_package)
