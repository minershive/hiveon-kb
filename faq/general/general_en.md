---
title: General Hive OS FAQ
path: /faq-general-general
parent_category: FAQ
category: General
meta_description: Here you will find answers to the basic questions about Hive OS.
---

### What is Hive OS?
Hive OS is an operating system based on the Linux distribution of Ubuntu 16.04 LTS, which main task is to provide the user with a convenient interface for mining crypto-currency on GPU rigs and ASIC miners while managing them by using a web interface.

### Is Hive OS free?
It is a conditionally free operating system. If you use up to 4 workers — it is free. Find the details <a href="https://hiveos.farm/faq-billing_in_hive_os-billing">here</a>.

ASICs using <a href="https://hiveos.farm/asic">Hiveon ASIC Firmware</a> are not charged by our billing system and can use Hive OS for free.

### What is a worker?
A worker is a term used to describe both types of mining hardware that is supported by Hive OS: a rig — a computer built with GPUs; and ASIC — an Application-Specific Integrated Circuit (ASIC) customized for cryptocurrency mining.

### What is a watchdog?
It is a special program integrated in Hive OS. There are two types of watchdogs: one of them watches the miner’s hashrate, the other monitors the temperature. If the hashrate drops, the watchdog will restart the miner. If restarting does not help, then it will reboot the rig. The temperature watchdog reboots the system or stops mining if the equipment reaches a critical temperature.

### Do you have a referral program?
Yes, we have a referral program. Create a referral link with your account ID and share it with others. New users that sign-up using your referral link will be marked as your referrals. You can also create promo codes. Find out more <a href="https://hiveos.farm/pricing/">here</a>.

### How to block an account by IP?
For account blocking issues, please contact the official support email - bee@hiveos.farm.

### How to protect Hive OS account from hacking?
You can protect your account from hacking with 2FA authentication.
To do this, you need to install the Google Authenticator or Authy application on your phone. After this, go to your account settings and turn the 2FA on.

To reset the 2FA password, send an email to bee@hiveos.farm. In the letter, indicate the following information:

- your login, name and email account in Hive OS
- the number of workers and their names
- wallet address from the "Wallets" section (the primary one, if you have several wallets)
- the last IP address from which the account was logged in and the time of successful login

All fields are required.

If you do not know your external IP address, you can find it out at https://hiveos.farm/myip.

Apart from this, you can revoke unknown tokens in the "Authentication tokens" section (https://the.hiveos.farm/account). One more way to protect your account is removing unknown persons from the Access tab of your farm.

### What is the difference between a regular Hive OS update and a forced one?
With a forced update, the repositories are cleaned, updated, and their installation is repeated. To do this, send the following commands (one by one) to your worker:

`apt update`

`selfupgrade`

### How to downgrade the Hive OS version?
If you want to downgrade to the previous version of Hive OS, you need to click the arrow icon on the toolbar:

<img src="https://lbd.hiveos.farm/kbase/images/faqgeneral/eng1.png" />

Then select the version you want to return to, and click "Downgrade":

<img src="https://lbd.hiveos.farm/kbase/images/faqgeneral/eng2.png" />
