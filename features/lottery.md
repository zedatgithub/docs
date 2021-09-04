# 🤑 Lottery

## **Specifics** <a id="specifics"></a>

* Lottery Ticket price will be **2 USD** worth of TKENB, \(the necessary amount will be adjusted every 24 hours - once a day - in concordance with TKENB price\)
* Single User Lottery Entry Limit: No overall limit, but only 50 tickets can be bought at once through the UI
* Paying for one ticket will give users a **random combination of 4 numbers** with each number being between 1-14 \(e.g. **"**1-9-13-2"\). A number can appear multiple times, so 1-1-1-1 is a valid ticket.

## **How to win** <a id="how-to-win"></a>

To win the lottery jackpot \(**40%** of the entire lottery pool\), a user needs to match all 4 numbers on their ticket in the **exact same order** as the 4 winning numbers.

Additionally to the jackpot, users that match 2 or 3 numbers in the correct order, will also be eligible to win a prize.

## **Winning Ratio** <a id="winning-ratio"></a>

* Match 4 numbers in the exact order = win or split\* **40%** of the pot
* Match 3 numbers in the exact order = win or split\* **25%** of the pot
* Match 2 numbers in the exact order = win or split\* **15%** of the pot
* [🔥BURN🔥](https://testnet.bscscan.com/token/0x8a5a76401ada8998603d982d8343752fec75972b?a=0x000000000000000000000000000000000000dEaD) the remaining **20%** of the pot

_\* the pot is split when there are more winners_

{% hint style="warning" %}
If there are no winners in a category, the pot allocated to the respective category will be [  
🔥BURNED🔥](https://testnet.bscscan.com/token/0x8a5a76401ada8998603d982d8343752fec75972b?a=0x000000000000000000000000000000000000dEaD)
{% endhint %}

## Examples of tickets

If the winning numbers are "1-9-13-2**"**

* "2-13-9-1" = no matches
* **"1-9-13-2" = match all 4**
* "**1**-**9**-2-**2**" = 3 numbers matched
* "2-3-**13**-**2**" = 2 numbers matched
* "**1**-2-1-**2**" = 2 numbers matched

## **Lottery phases** <a id="lottery-phases"></a>

Lottery first draw is on [Sunday, September 19th, 12:00 GMT](https://www.timeanddate.com/countdown/generic?iso=2021-09-19T12:00:00Z&font=sanserif&p0=1440&csz=1&msg=Lottery%20first%20draw).

There will be 1 \(one\) draw per day, once every 24 hours, at specific 12:00 GMT.

An example of a lottery session:

**Phase 1 - Buy Tickets \(12 GMT to 12 GMT of the next day\)**

* Lottery Pot keeps growing \(10% of the emission rates goes to the lottery\)
* You have 24 hours to buy tickets
* The lottery jackpot will increase with each bought ticket
* Users will receive a ticket \(comprised of 4 digits\) for every Lottery Ticket

**Phase 2 - Lottery Draw \(12 GMT\)**

* The 4 winning lottery numbers are drawn and will appear on the page
* Each participant’s winnings will be automatically calculated based on their ticket numbers and shown on the page
* Users can claim winnings if they have any
* Users will also be able to see the lottery results: how many users matched all 4 numbers, 3 numbers, and 2 numbers and how many tokens will be burned

## **How are ticket numbers drawn** <a id="how-are-ticket-numbers-drawn"></a>

The lottery aims to be completely random. Even though the ticket numbers given out are determined by a front-end logic, there is an extremely low chance that anyone is able to determine the 4 winning numbers ahead of time.

* The 1st lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the number of participating users at the entry deadline.
* The 2nd lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the total pooled NATIVE Token balance at the entry deadline.
* The 3rd lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the timestamp of the last lottery participant at the entry deadline.
* The 4th lottery number will be determined based on the %10 remainders of a hash encoded by the blockhash and the block difficulty at the entry deadline.

