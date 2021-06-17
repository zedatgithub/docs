# 🤑 Lottery

## **Specifics** <a id="specifics"></a>

* Lottery Ticket price will always be **2 USD** worth of PANCAKE \(the necessary PANCAKE amount will be adjusted after every draw in concordance with PANCAKE's price\)
* Single User Lottery Entry Limit: No overall limit, but only 50 tickets can be bought at once through the UI
* Paying for one ticket will give users a random **4 digit combination** with each digit being between 1-9, e.g. **"**1-9-3-2" \(a digit can appear multiple times, so 1-1-1-1 is a valid ticket\)

## **How to win** <a id="how-to-win"></a>

To win the lottery jackpot \(**40%** of the entire lottery pool\), a user needs to match all 4 numbers on their ticket in the **exact same order** as the 4 winning numbers.

Additionally to the jackpot, users that match 2 or 3 numbers in the correct order, will also be eligible to win a prize.

## **Winning Ratio** <a id="winning-ratio"></a>

* Match 4 numbers in the exact order = win or split\* **40%** of the pot
* Match 3 numbers in the exact order = win or split\* **25%** of the pot
* Match 2 numbers in the exact order = win or split\* **15%** of the pot
* [🔥BURN🔥](https://testnet.bscscan.com/token/0xfcf5c003e9c4ab9231b333133611f1b3055c7973?a=0x000000000000000000000000000000000000dEaD) the remaining **20%** of the pot

\( \* the pot is split when there are more winners \)

{% hint style="warning" %}
If there are no winners in a category, the pot allocated to the respective category will also be  
[🔥BURNED🔥](https://testnet.bscscan.com/token/0xfcf5c003e9c4ab9231b333133611f1b3055c7973?a=0x000000000000000000000000000000000000dEaD)
{% endhint %}

## Examples of tickets

If the winning numbers are "1-9-3-2**"**

* "2-3-9-1" = no matches
* **"1-9-3-2" = match all 4**
* "**1**-**9**-2-**2**" = 3 numbers matched
* "2-3-**3**-**2**" = 2 numbers matched
* "**1**-2-1-**2**" = 2 numbers matched

## **Lottery phases** <a id="lottery-phases"></a>

There are 3 draws per day, once every 8 hours, with at specific UTC time:

* 0 AM
* 8 AM
* 4 PM

An example of a lottery session starting at 8 AM \(UTC\) is as below:

**Phase 1 - Buy Tickets \(8 AM to 4 PM\)**

* Lottery Pot will be deposited from the [Fee/Tax Distribution](deposit-fee-redistribution.md) collected in the previous 8 hours
* You have 8 hour to buy tickets
* The lottery jackpot will accumulate with each ticket bought
* Users will receive a ticket \(comprised of 4 digits\) for every Lottery Ticket

**Phase 2 - Lottery Draw \(4 PM\)**

* The 4 winning lottery numbers are drawn and will appear on the page
* Each participant’s winnings will be automatically calculated based on their ticket numbers and shown on the page
* Users can claim winnings if they have any
* Users will also be able to see the lottery results: how many users matched all 4 numbers, 3 numbers, and 2 numbers and how many tokens will be burned

## **How are ticket numbers drawn** <a id="how-are-ticket-numbers-drawn"></a>

The lottery aims to be completely random. Even though the ticket numbers given out are determined by a front-end logic, there is an extremely low chance that anyone is able to determine the 4 winning numbers ahead of time.

* The 1st lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the number of participating users at the entry deadline.
* The 2nd lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the total pooled PANCAKE balance at the entry deadline.
* The 3rd lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the timestamp of the last lottery participant at the entry deadline.
* The 4th lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the block difficulty at the entry deadline.

