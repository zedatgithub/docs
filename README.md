---
description: >-
  The Galactic Yield Farm and multi-chain Bridge On Binance Smart Chain, Heco,
  Polygon and Fantom
---

# 🏫 Home

## Introduction <a id="introduction"></a>

DXAMMFinance.One is the Galactic yield farm and multi-chain bridge, running on [Binance Smart Chain](https://www.binance.org/en/smartChain), [Avalanche](https://www.avax.network/), [Huobi Eco \(HECO\)](https://www.hecochain.com/en-us/), [Polygon](https://polygon.technology/) and [Fantom](https://fantom.foundation/), with yield farming, staking, lottery, auto-compounding vaults and more.

Our **MasterChef contract** is an **exact 1:1 fork** of thoreum.finance's MasterChef contract; [here are the 2 contracts compared](https://bscscan.com/contractdiffchecker?a1=0xf4168cd3c00799beeb9a88a6bf725eb84f5d41b7&a2=0xAf5Ff8E51648847c0e94eDC855ddD364E72a66EF) \(you have to click on the "Compare Difference" button at the bottom\) - you will notice that the only difference is that we changed all instances of **THOREUM** to **TKENB**.   
  
Our **Token contract** is an **exact 1:1 fork** of thoreum.finance's Token contract; [here are the 2 contracts compared](https://bscscan.com/contractdiffchecker?a1=0x580de58c1bd593a43dadcf0a739d504621817c05&a2=0xc979E70611D997Aa109528c6A9aa73D82Eaa2881) \(you have to click on the "Compare Difference" button at the bottom\) - you will notice that the only difference is that we changed all instances of **THOREUM** to **TKENB**. 

thoreum.finance's contracts were audited by [Techrate](https://docs.thoreum.finance/security/audits) \(paid version\), [Paladin BlockChain Security](https://docs.thoreum.finance/security/audits) and [CertiK](https://docs.thoreum.finance/security/audits)**.**

### About TKENB <a id="main-features"></a>

| Assignment | Amount | Percentage |
| :--- | :--- | ---: |
| Total supply: | 5,000,000,000 | 100% |
| Burned: | 2,000,000,000 | 40% |
| Liquidity mining: | 1,000,000,000 | 20% |
| Locked in [bridge](features/token-bridge.md): | 1,000,000,000 | 20% |
| Used in [presale](presale.md): | 499,900,000 available for buying | 9.99% |
|  | 499,900,000 used for pairing with the assets collected  from the presale and providing [locked liquidity](features/locked-liquidity.md) for farms | 9.99% |
| Devs: | 100,000 \(used for marketing purposes\) | 0.01% |
| Giveaway | 100,000 | 0.01% |

TKENB is mined via **liquidity mining** __where users can mine TKENB by staking other coins such as BNB, BUSD, ETH, etc., or by staking liquidity pairs \(LPs\) such as BNB-BTCB, BNB-ETH, etc.

[Read more](tokenomics/tkenb.md) about TKENB.

## **Main Features** <a id="main-features"></a>

* [Presale](presale.md)
* [Farms](features/harvest-lockup.md) where you deposit LP tokens to earn TKENB with high APYs
* [Pools](features/token-pools.md) where you deposit single tokens and earn TKENB with high APYs
* [Vaults](features/vaults.md) where you deposit LPs or single tokens and these \(the deposited LP tokens and/or single tokens\) are automatically and optimally compounded for you
* [Cross-chain transfer/exchange](features/token-bridge.md) between 5 chains via our own integrated [bridge](features/token-bridge.md):
  * [Binance Smart Chain](https://www.binance.org/en/smartChain)
  * [Avalanche](https://www.avax.network/)
  * [Huobi Eco \(HECO\)](https://www.hecochain.com/en-us/)
  * [Polygon](https://polygon.technology/)
  * [Fantom](https://fantom.foundation/)
* [Lottery](features/lottery.md) with ticket price always set to **$2**, regardless of the token's price
* improved [Referral Program](features/referral-program.md) where you now know who your referrer is and **you** are the one deciding if you want to have a referrer at all, who your referrer is, and when to confirm your referrer
* ownership of all contracts already transferred to the **24 hours** [Timelock](security/timelock.md)
* [Locked Liquidity](features/locked-liquidity.md)
* [Anti Whale](features/anti-whale.md) mechanism preventing Whales from quickly buying/selling large amounts \(pump & dump\)
* [No Migrator Code](security/no-migrator-code.md)

