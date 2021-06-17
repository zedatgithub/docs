# 💵 Vaults

## What is a Vault? <a id="what-is-a-vault"></a>

Vaults are investment instruments that employ a specific set of strategies for yield farming. They make use of automation to continually invest and reinvest deposited funds, which help to achieve high levels of compounded interest. You earn more of the asset you stake in it regardless if this is an liquidity pool \(LP\) token or a single asset. For example, vaults where one can stake BUSD-USDT LP will result in more BUSD-USDT LP over time, effectively growing your share in the vault and thus allowing for more and more rewards over time.

When browsing the vaults on the platform, you will see the annual percentage yield \(APY\), which takes the frequent compounding into consideration compared to annual percentage rate \(APR\) which does not.

Summarizing, vaults can:

* Compound rewards into the initially deposited token amount.
* Use any asset as liquidity.
* Put any asset to work to generate a yield.
* Reinvest earned profits.



* Stake your DEFI or LP Tokens and forget about it! The DEFI or LP Tokens you stake in this Vaults will be automatically compounded \(reinvested\) for you, minus a small fee.
* The “automatic” compounding function is triggered by other users who get a small bounty for triggering it.
* Interest is displayed as APY, which includes compounding.
* A small performance fee is subtracted from your earnings each time the pool is automatically compounded. See below.
* An unstaking fee applies when you unstake within 48 hours of manually staking. See below.

## What are the fees for the Vaults? <a id="what-are-the-fees-for-the-auto-cake-syrup-pool"></a>

**Deposit fee**

**Unstaking fee**

* **4%    if you unstake \(withdraw\) within 48 hours.**
* Only applies within 2 days of manually staking.
* After 2 days, you can unstake with **no fee**.
* The 2-day timer resets every time you manually stake more in the vault.
* This fee only applies to manual unstaking: it does not apply to automatic compounding.

**Performance fee**

* **2%, subtracted automatically from each yield harvest**.
* For example, if the harvest was 1 DeFi, then 0.02 DeFI would be subtracted as the performance fee.

The collected via the unstaking fee and performance fee are sent to [Fee/Tax Distribution](deposit-fee-redistribution.md) 

## What’s the Bounty? <a id="whats-the-auto-cake-bounty"></a>

**Bounty: 0.5% of the respective pool pending yield**

This bounty is given as a reward for providing a service to other users.

Whenever you successfully claim the bounty, you’re also helping out by activating the Auto CAKE Pool’s compounding function for everyone.

Make sure the amount of CAKE you receive will be greater than the BNB fees you’ll spend to submit the blockchain transaction!

## Why can't someone just do this themselves? <a id="why-cant-someone-just-do-this-themselves"></a>

They could, but vaults help you save on personal time and transaction fees, maintain healthy collateral to debt ratios, self-optimize for the best possible yields, and automatically reinvest earnings. Attempting to do this manually would result in large inefficiencies. At Beefy we like to say: "Sit back and relax, the vault does all the work for you."

## **Does the performance fee get taken out when I withdraw my funds?** <a id="does-the-performance-fee-get-taken-out-when-i-withdraw-my-funds"></a>

* No, the fees are taken every time someone calls the harvest\(\) function.

## Does the vault page show the APY? <a id="does-the-vault-page-show-the-apy"></a>

Yes. Our displayed APY values reflect the predicted rate earned on a vault in a year. This rate is determined by the underlying platform it uses, the strategy that it is interacting with at the time, the total amount of funds in the vault and also takes into account the effect of compounding. As a unique feature, we have also included all vault fees in the APY calculation. What you see is what you get!

## What risks do the vaults have? <a id="what-risks-do-the-vaults-have"></a>

Beefy vaults are audited, but this does not mean that a vault is entirely risk free. Below are some of the general vault risks:

* Assets deposited into the vault have no risk of decreasing in quantity but can decrease in monetary value.
* As with any smart contract, the ultimate risk is that an investor's funds can end up stolen or unable to be withdrawn. The team does take steps to quantify the security risks of smart contracts and only will interact with ones that meet a specific set of requirements after excessive testing to make sure the underlying platform does not contain so called 'rug-pull' functions.

## **How do LP vaults work?** <a id="how-do-lp-vaults-work"></a>

Liquidity pool \(LP\) vaults work by reinvesting the fees awarded to LP participants. In return for providing liquidity to the pool, many platforms reward investors with tokens. Our vaults regularly harvest these rewards, sell it, buy more of the LP’s underlying assets, and then reinvest to complete the cycle.

This compounds the rewards gained from a liquidity pool. Beefy.Finance creates strategies that automate this process, saving you time and gas fees in comparison to farming manually. This is all done for a tiny fee that is distributed back to those how stake in Beefy's governance pool or in the BIFI Maxi vault. A small percentage also goes to the Beefy Finance treasury.

## **How often are balances updated in the vaults?** <a id="how-often-are-balances-updated-in-the-vaults"></a>

* Pending rewards are not reflected in the balance until they are swapped for the initial deposited token. This can vary depending on the strategy running.

## **Why do I have less mooToken than the amount of tokens I deposited?** <a id="why-do-i-have-less-mootoken-than-the-amount-of-tokens-i-deposited"></a>

* The mooTokens represent the share of the Vault the user has. As the vaults generate profit, the amount of shares \(mooToken\) remain constant, and the underlying token amount increases.
* There generally are no deposit fees, so the amount of tokens you deposit is maintained the second after you deposited. That amount should increase over time as the strategy generates profit.

## **How do vaults get added to Beefy.Finance?** <a id="how-do-vaults-get-added-to-beefy-finance"></a>

New potential vaults can be discussed in our Discord in the \#whiteboard channel. Our strategists then add the potential investment strategy to our strategy list. A priority is assigned to each new, potential strategy based on its APY, TVL and sustainability. Our developers/strategists then attack the list from top priority to bottom. The official forum is used for submitting actual [vault requests](https://forum.beefy.finance/c/vault-requests).

## **What’s your vault naming process?** <a id="whats-your-vault-naming-process"></a>

Each vault on the platform is named after the token that users can deposit in it. For example, the CAKE-BNB LP vault uses CAKE-BNB LP tokens for its investment strategy. A BTC vault uses the BTC token, etc.

Underneath the vault name, you can find the platform used for investing the token and farming its yields. For example, Uses: Venus means that that particular vault invests the token in Venus, a DeFi algorithmic money market and synthetic stablecoin protocol.

## **How do Aave and Venus vaults work?** <a id="how-do-aave-and-venus-vaults-work"></a>

Aave and Venus are decentralized marketplaces for lenders and borrowers. By depositing your initial asset in the vault, Beefy deposits it into Aave or Venus and borrows against your token. This is done at safe levels of collateral.

The borrowed tokens are then redeposited into the platform, and once again used as collateral to borrow more tokens. This cycle is repeated multiple times to generate as much interest as possible to buy more of your originally deposited assets. It is noteworthy that this "leveraged" multi lending and multi borrowing is only with the native token, so there is no liquidation risk due to token price swings. Also, because of the multi supply/borrow cycle, a transaction fee for these vaults is generally 4x as high as compared to other vaults.

Because of accruing debt/supply interest, one may notice that the deposited token amount may decline ever so slightly in between harvests. After the harvest, you will see your deposited token amount go up as the yields are compounded back into it. The change in deposited token amount over time of typical Aave / Venus style vault looks as follows:

![](https://gblobscdn.gitbook.com/assets%2F-MJZ0tXJc-hdgL-YTlPk%2Fsync%2F4d04d93829ff3ac3c549e0d9d26b6eab358d3d8a.png?alt=media)

After a harvest event, the yields are added to the deposited token amount

