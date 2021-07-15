---
description: preventing Whales from quickly buying/selling large amounts (pump & dump)
---

# 🐋 Anti Whale

Transfers that exceed **1.5%** of the circulating supply of NATIVE Tokens will be rejected.

Circulating supply = total supply - burn address - fee/tax address - bridge address

{% hint style="info" %}
The value of **1.5%** is set in the beginning and as the circulating supply grows this value will be adjusted.
{% endhint %}

{% hint style="success" %}
Following cases are not subject to this restriction:

* Farm: Deposit
* Farm: Withdraw
* Farm: Compound
* Lottery: Buy tickets
* Lottery: Collecting Prize
{% endhint %}

> The current value can be viewed in the TKENA, TKENB [contracts](../tokenomics/contracts.md)  
> \( scroll down and search for the `maxTransferAmount` function \)

## More Anti Whale Measures

To prevent whales from entering with high volumes, staking, compounding and then quickly unstaking **before** the harvest lockup time ends in order to dump their tokens, the pending amount and the compounded amount will be lost if unstaking before harvest lockup time has not passed \(all this information is also available on the farm and pool cards\)

Therefore, only those users will be eligible for their rewards who respect the harvest lockup time!

