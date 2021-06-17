---
description: >-
  Automated market makers (AMMs) allow digital assets to be traded without
  permission and automatically by using liquidity pools instead of a traditional
  market of buyers and sellers
---

# 💱 AMM

Our AMM exchange is a complete fork of PancakeSwap v1.

We consider that **0.2% trading fee** is high enough and so we will not use DEFI v2 **0.25% trading fee.**

On PancakeSwap v1 the **0.2% trading fee** was split between **0.17%** going to liquidity providers while **0.03%** going into the treasury. The **0.17%** going to liquidity providers was not really an earning until the liquidity providers did not unstake and remove the liquidity so, overall, it was not a predictable source of income nor could this be reinvested \(compounded\).

Instead we decided to use all of the **0.2% trading fee** which is sent to [Fee/Tax Distribution](deposit-fee-redistribution.md) and use it to give more value to the DEFI token so that the liquidity providers can earn more a valuable token which they can reinvest \([compound](farms-pools-compound.md)\).

## Contracts <a id="contracts"></a>

* Factory: [0xDf7909D3584a91504a821d80ED20a31584858E3a](https://testnet.bscscan.com/address/0xDf7909D3584a91504a821d80ED20a31584858E3a#code)
* Router: [0x5B5191851630C7eBa105Cd9Cec1E535dD48fF369](https://testnet.bscscan.com/address/0x5B5191851630C7eBa105Cd9Cec1E535dD48fF369#code)

The Factory & Router smart contracts are the same as PancakeSwap's.  
The only things we changed in these two contracts are:

* "pancake" to "DEFI"
* treasury fee from **0.03%** to **0.20%**, sent to [Fee/Tax Distribution](deposit-fee-redistribution.md) in Factory \(the **0.17%** fee sent to liquidity providers will automatically become **0** because of the way the contract is coded\)

```javascript
uint denominator = rootK.mul(3).add(rootKLast);

to

uint denominator = rootK.mul(20).add(rootKLast);
```

It means that the contracts where the liquidity is stored \(your money\) are as safe as PancakeSwap's.

You can use the links below to compare the smart contracts of DEFI and PancakeSwap.

## PancakeSwap v1 Contracts as reference <a id="contracts"></a>

* Factory: [https://bscscan.com/address/0xbcfccbde45ce874adcb698cc183debcf17952812](https://bscscan.com/address/0xbcfccbde45ce874adcb698cc183debcf17952812#code)
* Router: [https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f](https://bscscan.com/address/0x05ff2b0db69458a0750badebc4f9e13add608c7f#readContract)

## Trading Fee <a id="trading-fee"></a>

For each trade a **0.2% trading fee** is charged and sent to [Fee/Tax Distribution](deposit-fee-redistribution.md)

​

​

​

