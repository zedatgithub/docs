---
description: preventing Whales from quickly buying/selling large amounts (pump & dump)
---

# 🐋 Anti Whale

Transfers that exceed **0.5%** of the circulating supply will be rejected. 

{% hint style="info" %}
The value of **0.5%** is set in the beginning and as the circulating supply grows this value will be increased.
{% endhint %}

{% hint style="success" %}
Following case are not subjected to this restriction:

* Farm: Deposit
* Farm: Withdraw
* Farm: Compound
* Lottery: Buy tickets
* Lottery: Collecting Prize
{% endhint %}

> The current value can be viewed in the [DEFI](https://testnet.bscscan.com/address/0x8a5a76401ada8998603d982d8343752fec75972b#readContract) token contract.  
> \( scroll down and search for the `maxTransferAmount` function \)

## More Anti Whale Measures

To prevent whales from entering with high volumes, staking, compounding and then quickly unstaking **before** the harvest lockup time ends in order to dump their tokens, the pending amount and the compounded amount will be lost if unstaking before harvest lockup time has not passed \(all this information is also available on the farm and pool cards\)

Therefore, only those users will be eligible for their rewards who respect the harvest lockup time!

