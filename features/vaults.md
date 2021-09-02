# 💵 Vaults

## What are the Vaults? <a id="what-is-a-vault"></a>

Vaults are investment instruments making use of automation to continually reinvest deposited funds, helping you achieve high levels of compounded interest and earning you more of the staked assets. For example, vaults where one staked BNB-BUSD LPs will result in more BNB-BUSD LPs over time, effectively growing your share in the vault and thus allowing for more and more rewards over time.

When browsing the vaults on the platform, you will see the annual percentage yield \(APY\), which takes the frequent compounding into consideration compared to annual percentage rate \(APR\) which does not.

Vaults can:

* compound rewards into the **initially deposited asset** \(you will not earn TKENB but your invested asset, be that LPs or single tokens!\)
* use any asset as liquidity and put it to work for you and to generate interest
* reinvest earned profits
* the assets staked in the vaults will automatically be compounded \(reinvested\) for you for free
* the compounding function is triggered by other users who get a small bounty for triggering it as well as automatically, by the platform, a few times per day
* interest is displayed as APY, which takes into account the perpetual compounding
* an unstaking fee applies when you unstake before the required amount of time after a manual staking \(see below\)

## What are the fees for the Vaults? <a id="what-are-the-fees-for-the-auto-cake-syrup-pool"></a>

**Deposit fee**

* **0%** for TKENB token/pairs 
* **4%**    for NON TKENB pairs

**Unstaking fee**

* **4%**    if you unstake \(withdraw\) within **48 hours** for TKENB token/pairs 
* **4%** if you unstake \(withdraw\) within **72 hours** for NON TKENB pairs 
* only applies after manually staking \(not for auto-compounding\)
* after that, you can unstake **without any fees**
* the timer resets every time you manually stake more \(add\) to the vault
* this fee only applies to manual unstaking - it does not apply to automatic compounding

Fees collected from early unstaking are sent to [Fees/Taxes](deposit-fee-redistribution.md).

## What’s the Bounty? <a id="whats-the-auto-cake-bounty"></a>

**Bounty: 0.5% of the respective pool's pending yield**

This bounty is given as a reward for providing a service to other users.

Whenever you successfully claim the bounty, you are also helping out by activating the auto-compounding feature for everyone.

_Make sure that the amount of TKENB you receive will be greater than the BNB/AVAX/HT/MATIC/FTM \(depending on the chain\) fees you will be spending to submit the blockchain transaction!_

## Does the vault page show the APY? <a id="does-the-vault-page-show-the-apy"></a>

Yes. Our displayed APY values reflects the predicted earnings on a vault over a year. This rate is determined by the total amount of funds in the vault and takes into account the effect of compounding. As a unique feature, we have also included all vault fees in the APY calculation - what you see is what you get!

## What risks do the vaults have? <a id="what-risks-do-the-vaults-have"></a>

Below are some of the general vault risks:

* Assets deposited into the vault have no risk of decreasing in quantity but can decrease in monetary value.
* Vaults assets are held in the MasterContract.

## **How do LP vaults work?** <a id="how-do-lp-vaults-work"></a>

Our vaults regularly harvest rewards, sell it, buy more of the underlying assets, and then reinvest everything to complete the cycle.

## **How often are balances updated in the vaults?** <a id="how-often-are-balances-updated-in-the-vaults"></a>

Every time somebody collects the Bounty, or when the Automatic compounding feature runs \(3 times per day\)

