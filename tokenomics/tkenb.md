---
description: farming token used for mixed pairs
---

# 🌖 TKENB

## Basic Information <a id="basic-information"></a>

* Name: TKENB Token
* Symbol: TKENB
* Contract address can be found in [Contracts](contracts.md) section
* Set slipage to **17%**

TKENB is a deflationary coin with reflection \(and thus favoring holders\), hard capped at 5 billions, 2 billions burned at start, 1 billion locked in the cross-chain bridge, and 1 billion used in presale. Investors need to mine the rest of the 1 billions tokens.

| Assignment | Amount | Percentage |
| :--- | :--- | ---: |
| Total supply: | 5,000,000,000 | 100% |
| Burned: | 2,000,000,000 | 40% |
| Liquidity mining: | 1,000,000,000 | 20% |
| Locked in [bridge](https://github.com/zedatgithub/pancake-docs/tree/69f12926d7970e4756d48e399e4ed4a8a952acfe/tokenomics/features/token-bridge.md): | 1,000,000,000 | 20% |
| Used in [presale](https://github.com/zedatgithub/pancake-docs/tree/69f12926d7970e4756d48e399e4ed4a8a952acfe/tokenomics/presale.md): | 499,900,000 available for buying | 9.99% |
|  | 499,900,000 used for pairing with the assets collected  from the presale and providing [locked liquidity](https://github.com/zedatgithub/pancake-docs/tree/69f12926d7970e4756d48e399e4ed4a8a952acfe/tokenomics/features/locked-liquidity.md) for farms | 9.99% |
| Devs: | 100,000 \(used for marketing purposes\) | 0.01% |
| Giveaway | 100,000 | 0.01% |

## **Liquidity Mining**

TKENB is mined via **liquidity mining** where users can mine TKENB by staking other coins such as BNB, BUSD, ETH, etc., or by staking liquidity pairs \(LPs\) such as BNB-BTCB, BNB-ETH, etc.

## **Automatic Reflection Rewards to Holders**

Whenever TKENB is transferred, a **14%** tax fee is taxed for each transaction: **10%** is used for [automatic buy backs and burn](../features/automatic-burning.md), while the remaining **4%** is redistributed among existing TKENB holders as [reflection rewards](reflection-rewards.md).

Those who decide to hold their TKENB are rewarded from those who sell, so this mechanism encourages holders and discourages pump and dump traders. Holders are incentivized to hold their coin because their holdings will increase over time. And even if TKENB investors take no action, they still collect additional TKENB just by holding it.

## **Deflationary Auto Burn**

Since the coin is deflationary, the supply keeps decreasing with every transaction and ensures a limited availability in the near future. Deflation comes with burn wallet being one of the holders of TKENB, hence participating in reflection and auto burning tokens.

## Transfer Tax <a id="transfer-tax"></a>

* Transfer Tax Rate: **14% of every transfer**:
* Reflection Rate: **4%** will be reflected back to current holders as [reflection rewards](reflection-rewards.md)
* Liquidity Rate: **10%** will be used for the [buyback and burn](../features/automatic-burning.md) mechanism

{% hint style="info" %}
The transfer tax is applied **only** for transactions involving TKENB
{% endhint %}

You can see the values on chain in the [token contract](contracts.md) if you look for:

* _\_taxFee_ \(reflection rate\)
* _\_liquidityFee_ \(liquidity rate\)

## Mining rates <a id="emission-rate"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left">Network</th>
      <th style="text-align:left">Emission
        <br />rate</th>
      <th style="text-align:left">Emissions/
        <br />day</th>
      <th style="text-align:left">
        <p>Block</p>
        <p>time</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Binance Smart Chain</td>
      <td style="text-align:left">100 TKENB / block*</td>
      <td style="text-align:left">~ 2,800,000 TKENB / day</td>
      <td style="text-align:left"><a href="https://bscscan.com/chart/blocktime">~ 3 seconds</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Avalanche</td>
      <td style="text-align:left">33 TKENB / block*</td>
      <td style="text-align:left">~ 2,800,000 TKENB / day</td>
      <td style="text-align:left"><a href="https://cchain.explorer.avax.network/">~ 1 second</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Huobi ECO (HECO)</td>
      <td style="text-align:left">100 TKENB / block*</td>
      <td style="text-align:left">~ 2,800,000 TKENB / day</td>
      <td style="text-align:left"><a href="https://hecoinfo.com/chart/blocktime">~ 3 seconds</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Polygon (Matic)</td>
      <td style="text-align:left">66 TKENB / block*</td>
      <td style="text-align:left">~ 2,800,000 TKENB / day</td>
      <td style="text-align:left"><a href="https://polygonscan.com/chart/blocktime">~ 2 seconds</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Fantom</td>
      <td style="text-align:left">33 TKENB / block*</td>
      <td style="text-align:left">~ 2,800,000 TKENB / day</td>
      <td style="text-align:left"><a href="https://ftmscan.com/chart/blocktime">~ 1 second</a>
      </td>
    </tr>
  </tbody>
</table>

\*10% of the emission rate goes to the [lottery](../features/lottery.md) [contract](contracts.md) \(so it will actually accumulate on the lottery's contract and you will be able to see it in your preferred chain's explorer\), but we decided **not to use** this for the lottery but instead [🔥BURN🔥](https://testnet.bscscan.com/token/0x8a5a76401ada8998603d982d8343752fec75972b?a=0x000000000000000000000000000000000000dEaD) it periodically.

The lottery pot will be instead topped up from the **1%** deposit fee collected from staking into TKENB-paired farms and vaults.

## Why TKENB Has A Hard Cap?

There's a hard cap on the supply of TKENB, with a burn mechanism making it a deflationary coin.

{% hint style="info" %}
TKENB primary function is to become a deflationary utility coin with decreased supply and increased value over time, to incentivize people to mine it, hold it, and use it.
{% endhint %}

## What is TKENB Deflationary Mechanism?

**Transfer tax**

As mentioned previously, there is a **14%** transfer tax on each TKENB transaction: **4%** will be reflected back to current holders as [reflection rewards](reflection-rewards.md), while **10%** will be sold for BNB/AVAX/HT/MATIC/FTM \(depending on the chain\) through the contract automatically whenever 100,000 TKENB is collected, and added to TKENB's contract.

This liquidity will be locked in TKENB contract and no one - not even the developers - can withdraw it, and this liquidity will be used for doing the automatic buy backs and burns. It should be beneficial in the long term because it will help keep the price level of TKENB and raise it over time.

**Other burning mechanisms**

* via the [Lottery](../features/lottery.md)
* developing games for burning mechanisms
* new ideas and developments such as Predictions betting in progress

