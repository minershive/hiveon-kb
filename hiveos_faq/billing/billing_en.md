<span kb-breadcrumbs>[Root](/knowledge-base)</span>
<span kb-breadcrumbs> / </span>
<span kb-breadcrumbs>[Hiveos FAQ](/hiveos_faq-hiveos_faq)</span>
____

# How does Hive's billing system work?
Hive OS is a prepaid system. You need to do a deposit to have more than 3 free workers in your farm. Deposit can be as small as you wish. There's no need to prepay for the whole month, you can pay $1, for example, just to give Hive OS a try. Workers are billed daily, not monthly.

Only active rigs in the past 24h will be billed. If the worker was online and we see it in our stats, the billing will occur. If it was offline then it’s won't be billed. No need to deactivate it in the system in order to stop the billing.

Charging balance is done after the end of the day. Here's and example: -0.4$ charged from your balance at 02:15 AM on 4th of June for 4 rigs online from 02:15 AM 3rd of June to 02:15 AM 4th of June.

# Are there free workers and farms?
3 rigs are free to use until you have more. If you add the 4th rig your farm will be charged for 4. We consider 3 rigs to be home mining and having more is a business and we charge all the workers.

You can have multiple farms, if total number of workers stays within 3 rigs it would be free. For example you have the 1st farm with 1 rig and the 2nd farm with two rigs and this would be free. If you have 4 farms with 1 worker in each then all 4 will be billed.

# How is the monthly fee charged?
The subscription system will charge once a day based on the number of paid workers in your account.

# Can I get a discount?
Yes, all discount plans can be viewed on the <a href="https://hiveos.farm/pricing/">pricing page</a>.

Discounts apply for the total number of workers in the farms you own. For example, **Farm1** has 40 and **Farm2** has 20 workers, the discount will be calculated based on the total of 60 workers.

ASICs have a different base price and are cheaper than rigs because there are not as many functions compared to rigs. Workers with <a href="https://hiveos.farm/asic">Hiveon ASIC Firmware</a> are not charged and can use Hive OS for free.

# Ho do I deposit funds?
Hive accepts cryptos only. Our payment provider is <a href="https://www.coinpayments.net/">CoinPayments</a>.

Refunds or withdrawals are not available. You can transfer funds only between users and farms, but there is no withdrawal option.

If you have referral earnings you can deposit them to a Hive account. Referral rewards are payed out once a month to your address if you have one specified.

# Can I pay using a different payment system like PayPal instead of paying with cryptocurrency?
Not at the moment. Payment is currently done only using cryptocurrency through the <a href="https://www.coinpayments.net/">CoinPayments</a> service.

# Can I pay Hive directly and not via CoinPayments?
No. The billing system was not designed to work that way.

# How quickly after payment, does the money appear in an account?
It all depends on the processing speed of CoinPayments service. We have no control over the transaction period.

# What is CoinPayments?
It's an integrated payment system for cryptocurrencies that can be used to pay for our services. More detail are available <a href="https://www.coinpayments.net/">here</a>.

# I dislike the CoinPayments service, can I pay using a different payment method?
Currently payments can only be done using cryptocurrency and only through <a href="https://www.coinpayments.net/">CoinPayments</a> service.

# Are there Transaction Fees?
_**Important!** Check that you have covered the Transaction Fee before paying!._

Yes, there are Transaction Fees. This is one of the most common problems that users have. The fees depend on your exchange or wallet software, but  make sure that your payment is the amount specified in the bill + TX fee or your payment won't come through.

# I payed my monthly subscription, but received a message "Waiting for confirms… (0.00241/0.00253 received with 1 confirms)" in my payment status, what did I do wrong?
You have payed without including a fee. You'll see the following message in **Your Funds** section:

`Waiting for confirms… (0.00241/0.00253 received with 1 confirms)`

There are 2 ways to deal with this:

1. You leave this payment as is, the money will be returned within 24 hours from the time the transaction was made. You can create another payment bill, but this time including the tax fee.
2. You can make another transaction to cover missing the missing amount (0.00253 - 0.00241). But you could have minimal withdraw restrictions on your exchange. You should refer to your payment system documentation for more details.

# I have paid more than the subscription bill, can I receive the rest of the funds on my Hive OS account?
This is not possible. You are not paying to Hive account directly but to CoinPayments instead. For example, if you had issued the bill for $15, but sent more than that, then only $15 will be transferred as payment to your Hive account. The rest of the funds will return. If you don't receive the rest of your funds back, you should contact CoinPayments. But we suggest waiting at least 24 hours for your refund first, before contacting CoinPayments support.

# My rigs weren't working the whole day, can I expect a discount proportionate to all that time?
The billing system charges per day of use, regardless of hours. If your worker was not online during the day, the payment will not be charged.

# What happens when there's zero credits on my account? Will mining stop?
No, your workers will continue mining for some time, but the ability to monitor your stats through Hive OS server will be unavailable.

# How do I pay?
Find the <a href="https://the.hiveos.farm/funds">Pay</a> button in your account. After paying please check the status in the **CoinPayments Deposits** section.
You will receive am email from Coinpayments with the link to their bill and additional instructions.

# How do I pay via an Exchange or Online Wallets?
Exchanges like <a href="https://bittrex.com/">Bittrex</a>, <a href="https://poloniex.com/">Poloniex</a>, <a href="https://yobit.net/">YoBit</a> and others have high **Withdrawal Fees** and can have a minimal withdrawal amount. Bitcoin BTC has very high TX Fee also. So it’s not reasonable to to pay $5 form an exchange with BTC (in the worst case).

What is advised is to have your own wallet like <a href="https://jaxx.io/">Jaxx</a> or <a href="https://www.exodus.io/">Exodus</a> and top up it's balance. From there you can easily exchange assets like, BTC->ETC, ETH->LTC, for example. You'll pay cents for transactions instead of dollars. ETC, BCH, LTC have very low fees.

# How does the Credit work?
Credit can be given for up to 5 days. When your farm's balance reaches 0 (zero), it will have a negative balance, but your workers will still work. After 5 days the farm will be locked. A negative balance will be covered automatically after you make a new deposit.

# User and Farm balance
For more convenient money management, farms have their own balances. You can make a direct deposit to your account and then refill the farms you own. If a farm balance is 0 (zero) then the user’s balance will be charged. This way you don't need to refilling your farm's balance directly.

# Can I make other users as Payers?
You can set other users to be responsible for depositing to the farms you own. This user can be your financial manager and requires only the **Monitor** access level to your farms.

# What are the Payed Features?
There is a button in your billing page where you can enable Payed Features. The full list of features is available <a href="https://hiveos.farm/pricing/">here</a>. There are SSL worker connections, monthly stats, etc. This list is subject to changed and is growing with more features being implemented.

As a free user (1-3 rigs) you can support out project and get the benefit of using the Payed Features.

If you create a second farm Payed Features will be enabled and all your farms will be billed even if they have no more than 3 workers. You will be able to disable the billing on a farm if you leave only 1 active farm.

# Can I transfer the responsibility of farm billing?
By default owner of the farm is responsible for billing. When the the farm’s balance is low the funds will be deducted from user’s balance. Optionally the owner can transfer billing rights to other users, let’s say an accountant. Other users will need to confirm that they accept the billing responsibility upon transfer. The common case of using this feature would be to set one of your organization members to be responsible for topping-up the balances of farms and not giving them any other extra management rights. You will remain as the owner.
