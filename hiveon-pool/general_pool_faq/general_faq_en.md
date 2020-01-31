---
title: General FAQ
category: General pool FAQ
---
## General FAQ
### What is a mining pool?
A mining pool is the grouping of resources by miners, who share their processing power, hashrate, over a network, to split the reward equally, according to the amount of work they contributed to the probability of finding a block. A "share" is awarded to members of the mining pool who present a valid partial proof-of-work.

### What is a Share?
A share is a hash smaller than the target for difficulty that's usually lower than the network difficulty. Every hash generated has a chance of being a valid share. Miners have no control over when they will generate a share as they occur randomly. When one miner in the pool finds the solution hash, the rewards can then be split by number of shares submitted by each miner. There are multiple reward methods, PPLNS, PPS, PPS+, etc. These reward types calculate the "fair share" of the reward, but all pools use a share as a "proxy" for work completed by each miner. A share has no actual value. The only hash worth something is the one that solves a block. A share is just a method to divide any rewards earned by the pool.

### What is Hashrate?
A hashrate (or hash rate) is the measure of a miner’s performance. It is the speed at which a miner solves a task. Hash per second represents SHA-256 algorithms that are used per second, known as hash rate. The hash per second, H/s, is the measure of the efficiency of the miner. Higher hash rate means increased chances of receiving a block reward.

### What is Reported Hashrate?
Reported Hashrate is used by mining software to determine the submitted computed hashrate of the hardware to the pool. The reported hashrate is essentially used for comparing it to your calculated hashrate shown by the pool. Reported hashrate is generally inaccurate and that's why there's always a small difference when comparing it to the calculated hashrate. It is a value only displayed by your workers' mining software.

### What is Mean or Calculated Hashrate?
Mean or Calculated hashrate is calculated from the accepted hashes that your hardware has submitted to the pool. This value can fluctuate above or below your reported hashrate. The rate is impacted by such things as stale shares, invalid shares, changing hash difficulty and pool's luck. Your worker may submit more or less shares during a given period of time that are accepted by the pool.

### What is Average Hashrate?
Average is exactly what it's called – an average. This is the average effective hashrate over a specified period of time. The higher the better.

### How to reduce the hashrate gap?
Usually there is a somewhat significant difference between reported hashrate and average hashrate. This is considered normal, so don't worry about the reported hashrate too much. The higher the reported rate, the better is the average hashrate. But keep in mind, if you push your workers too hard then the calculated hashrate will take a plunge creating a gap between reported and calculated. That will affect your payouts.

* Calculated hashrate is the most important statistic. Higher is better. Use reasonable overclocks to achieve this.

* Keep a small gap between reported and mean (calculated) hashrates.

* If your mean hashrate is much lower then your reported hashrate, your worker is most likely overclocked too high and it's not effectively hashing. Your hashrate may be bigger, but you’re generating more rejected or invalid hashes. Miner's logs can confirm this in most cases.

* Large amounts of stale shares can affect your effective hashrate. Check your internet connection. Wi-Fi will cause more stales.

* Fluctuations in mean hashrate are normal.

* Higher average hashrates are better for your performance. Remember, this is not a race, but a marathon.

### What type of mining rewards are there?
Each pool operates on a different set of rules for their payouts, but here are a few of the most popular ones:

**Pay-per-share (PPS)**, is a reward system where the miner will receive a reward (get paid) for each valid contributed share. PPS pools are considered to be the best reward types if you want a steady 100% (minus the pool fee) income. PPS pools pay for literally every valid share you submit. Meaning, every time your mining software “accepts” a transaction, you get rewarded with a small amount regardless of whether the pool has found a block or not. The pool operator is virtually hiring your hash power.

**Pay Per Last N Shares (PPLNS)** is a payout type in which the miner takes the risk of variance upon himself. PPLNS pools were designed to stop "pool hoppers" as they don’t technically pay out the current block, but instead they pay out based on an average of the shares that were submitted over the last x number of blocks. So, when first starting to mine on a PPLNS pool, one will notice that they'll hardly get paid anything until a few hours later. This will ramp up over time and once one stops mining, they'll still get paid for a few hours, due to the “buffer effect” of PPLNS.

**PPS+ (Pay per Share Plus)** is a combination of the PPS and PPLNS payout methods. Just like with PPS, miners are paid for each share that they submit, giving them a predictable payment method. Unlike PPS, which only awards block rewards and does not cut tax fees, PPS+ distributes all bonuses to miners and splits all rewards above the block. While the fluctuating rewards like in the PPLNS are avoided as a whole.

### What is Pool Luck?
It's a metric that shows how many shares the pool needed in order to find a block relative to the average number of shares needed for finding a block. If the luck is above 100% then the pool needs less shares then expected for a given difficulty. If the luck is below 100%, then more shares were needed. Luck only shows the history of the pool and cannot be used to predict future blocks. Finding a block is completely random, so joining a pool when there is high luck and then leaving when the luck is low, won't make any sense.
