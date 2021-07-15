# 💵 Auto Compounding Vaults

## What are the Vaults? <a id="what-is-a-vault"></a>

Vaults are investment instruments making use of automation to continually reinvest deposited funds, helping you achieve high levels of compounded interest and earning you more of the staked assets. For example, vaults where one staked USDC-USDT LPs will result in more USDC-USDT LPs over time, effectively growing your share in the vault and thus allowing for more and more rewards over time.

When browsing the vaults on the platform, you will see the annual percentage yield \(APY\), which takes the frequent compounding into consideration compared to annual percentage rate \(APR\) which does not.

Vaults can:

* Compound rewards into the initially deposited asset
* Use any asset as liquidity
* Put any asset to work to generate a yield
* Reinvest earned profits
* The assets staked in the Vaults will automatically be compounded \(reinvested\) for you for a small fee
* The compounding function is triggered by other users who get a small bounty for triggering it as well as automatically, by the platform, a few times per day
* Interest is displayed as APY, which takes into account the perpetual compounding
* A small performance fee is subtracted from your earnings each time the pool is automatically compounded \(see below\)
* An unstaking fee applies when you unstake within 48 hours after a manual staking \(see below\)

## What are the fees for the Vaults? <a id="what-are-the-fees-for-the-auto-cake-syrup-pool"></a>

**Deposit fee**

* 0% fee for NATIVE token/pairs 
* 4%    fee for NON NATIVE pairs

**Unstaking fee**

* **4%    if you unstake \(withdraw\) within 48 hours**
* Only applies within 2 days after manually staking
* After 2 days, you can unstake **without any fees**
* The 2-day timer resets every time you manually stake more in the vault
* This fee only applies to manual unstaking - it does not apply to automatic compounding

**Performance fee**

* **2%, subtracted automatically from each yield harvest**
* Example: if the harvest was 1 TKENA, then 0.02 TKENA would be subtracted as the performance fee

Fees collected from early unstaking, as well as the performance fees, are sent to [Fee/Tax Distribution](deposit-fee-redistribution.md)

## What’s the Bounty? <a id="whats-the-auto-cake-bounty"></a>

**Bounty: 0.5% of the respective pool's pending yield**

This bounty is given as a reward for providing a service to other users.

Whenever you successfully claim the bounty, you are also helping out by activating the auto-compounding feature for everyone.

_Make sure that the amount of NATIVE Token you receive will be greater than the BNB/MATIC/FTM fees you’ll spend to submit the blockchain transaction!_

## Why can't someone just do the compounding by themselves? <a id="why-cant-someone-just-do-this-themselves"></a>

They could, but vaults help you save on personal time and transaction fees and automatically reinvest your earnings. Attempting to do this manually would result in large inefficiencies. Basically, "Sit back and relax, the vault does all the work for you."

## **Does the performance fee get taken out when I withdraw my funds?** <a id="does-the-performance-fee-get-taken-out-when-i-withdraw-my-funds"></a>

No, the performance fees are taken every time someone claims the Bounty because the action will trigger the harvesting and the compounding for everyone.

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

