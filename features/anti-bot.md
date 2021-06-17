---
description: preventing Bots from buying/selling the token too frequently
---

# 🤖 Anti Bot

A new Anti-Bot protection system is premiered by DEFI in order to prevent bots from buying/selling the token too frequently.

A minimum of **5 blocks** \(_approximately 15 seconds_\) must pass between **every** DEFI transfer. 

{% hint style="warning" %}
When transferring DEFI from one wallet to another,  the condition must be true for both wallets.
{% endhint %}

> The current value can be viewed in the [DEFI](https://testnet.bscscan.com/address/0x8a5a76401ada8998603d982d8343752fec75972b#readContract) token contract.  
> \( scroll down and search for `minTransferBlockRate` function \)

