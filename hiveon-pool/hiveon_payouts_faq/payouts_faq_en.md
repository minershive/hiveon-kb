---
title: Payouts FAQ
---

### What is Hiveon.net's payout type?
The pool has a PPS+ payout model. This means that payment is made for each decision (share) sent, regardless of how long you have joined the pool.

### What commission does the pool hold?
Currently, the pool doesn't hold any commission. Besides, we completely cover the transactions.

### How are payments made and in what amount?
Payments are made daily at 07:33 GMT, provided that the balance is at least 0.1 ETH at the time of payment.
You can check the local time for your time zone, for example, <a href="https://time100.ru/GMT">here</a>.

### Can I change the payout amount?
Since the transactions are covered by pool, at the moment it is impossible for users to change the payout thresholds.

### Are there payouts for stale shares?
Yes, payment for stale shares is made, but using the coefficient of 0.6-0.8, depending on network delays.


> __*Dear Miners*__
>
> _Starting from today, we are changing the rules for stale shares payouts. For **up to 6%** of stale shares, the conditions are the same. Starting **from 6% and above**, the pool freezes the payouts, meaning you won't get paid for your stale shares. If the problem of high stales persists for 48 hours, the wallet is blacklisted and payouts are frozen until further notice._
>
> _Such radical measures are related to the fact that fraudulent miners abuse our stale shares payout system. Thank you for understanding and thank you for using our ecosystem._

### How to reduce stale shares?
It should be noted that the number of Stale Shares mainly depends on the quality of connection between your miners and the pool servers. Also to a large extent it depends on the quality of work of network equipment between the network nodes. Please make sure your stale shares stay below 5%. The payout coefficient for the stale shares will be 0.6-0.8 of the price for an accepted share.

Unfortunately, the pool's technical staff is not able to affect the quality of your provider's equipment and the routing of network packets from you to the pool and back. If you are absolutely confident in the quality of your own network equipment and if you are an honest miner, but regularly get blocked payouts, in this case - we are very sorry, but there's nothing we can do. It should also be noted that if you work through a mobile operator (3G / 4G modems or Wi-Fi routers), then the probability of a large number of stale shares is high due to the peculiarities of the mobile connectivity.

### Why is a large amount of stale shares bad?
For regular pools, where stales are not paid for, only the miner himself is at a loss if there's a large number of stales, because he simply loses income. Stale shares are lost profit. In the case when stale shares are paid out (as is the case on our pool), it lowers the pool's luck, because stales don't participate in finding a block, thus they'll have to be paid out at the expense of internal means of the Hive ecosystem.

### I didn't receive the amount I mined despite the fact that at the time of payment it was sufficient. Why?
Probably the system put your address on the blacklist due to suspected fraud.

One of the criteria sufficient to block addresses by the anti-hacking system is a high percentage (5% or more) of the stale share.

### How does a payout blocking system work?
The payout blocking system works as follows: if the percentage of stale shares exceeds the threshold value, which is 5% at the moment, the system will automatically put your address on the blacklist. If within 48 hours the percentage of stale shares is reduced below the set threshold, the system will automatically unlock the address. If the unlocking has not occurred, the withdrawal of funds can be done manually. Read below how to do this.

### So what should I do now? How can I withdraw the funds?
In this case, you need to publish your **dashboard url** `https://hiveon.net/eth/?miner=0xВстАВЬтесюдаАдрЕСВашЕгоКошЕлЬка` with a brief comment on what happened. Chat administrators will pass all the necessary information to the pool technical support for verification. If the suspicions are not confirmed, your account will be unblocked, and your funds will be withdrawn.

### I don't plan to continue mining on your pool. How can I withdraw my balance, which is less than the payout threshold?
Remaining balances less than 0.1 ETH are no longer paid. In order to withdraw funds to your wallet, you need to mine the minimum withdrawal amount.
