---
description: farming token used for mixed pairs
---

# 🌖 TKENB

## Basic Information <a id="basic-information"></a>

* Name: TKENB Token
* Symbol: TKENB
* Contract address can be found in [Contracts](contracts.md) section

| Assignment | Amount | Percentage |
| :--- | :--- | ---: |
| Total supply: | 5,000,000,000 | 100% |
| Burned: | 2,000,000,000 | 40% |
| Liquidity mining:       | 1,000,000,000 | 20% |
| Locked in [bridge](https://github.com/zedatgithub/pancake-docs/tree/69f12926d7970e4756d48e399e4ed4a8a952acfe/tokenomics/features/token-bridge.md):        | 1,000,000,000 | 20% |
| Used in [presale](https://github.com/zedatgithub/pancake-docs/tree/69f12926d7970e4756d48e399e4ed4a8a952acfe/tokenomics/presale.md): | 499,900,000 available for buying | 9.99% |
|  | 499,900,000 used for pairing with the assets collected  from the presale and providing [locked liquidity](https://github.com/zedatgithub/pancake-docs/tree/69f12926d7970e4756d48e399e4ed4a8a952acfe/tokenomics/features/locked-liquidity.md) for farms | 9.99% |
| Devs: | 100,000 \(used for marketing purposes\) | 0.01% |
| Giveaway | 100,000 | 0.01% |

## **Liquidity Mining**

TKENB is mined via **liquidity mining** __where users can mine TKENB by staking other coins such as BNB, BUSD, ETH, etc., or by staking liquidity pairs \(LPs\) such as BNB-BTCB, BNB-ETH, etc.

## **Deflationary Auto Burn**

Since the coin is deflationary, the supply keeps decreasing with every transaction and ensures a limited availability in the near future. Deflation comes with burn wallet being one of the holders of TKENB, hence participating in reflection and auto burning tokens.

## Transfer Tax <a id="transfer-tax"></a>

* Reflection Rate: **4%** of transfer tax will be reflected back to current holders as [static rewards](static-rewards.md)
* Liquidity Rate: **10%** of transfer tax will be used for the [buyback and burn](../features/automatic-burning.md) mechanism
* Total Transfer Tax Rate: **10 + 4 = 14% of every transfer.**

{% hint style="info" %}
The transfer tax is applied **only** for transactions involving TKENB
{% endhint %}

## Mining rates <a id="emission-rate"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left">Network</th>
      <th style="text-align:center">Emission
        <br />rate</th>
      <th style="text-align:center">Emissions/
        <br />day</th>
      <th style="text-align:center">
        <p>Block</p>
        <p>time</p>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Binance Smart Chain</td>
      <td style="text-align:center">100 TKENB / block*</td>
      <td style="text-align:center">~ 28,000 TKENB / day</td>
      <td style="text-align:center"><a href="https://bscscan.com/chart/blocktime">~ 3 seconds</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Avalanche</td>
      <td style="text-align:center">33 TKENB / block*</td>
      <td style="text-align:center">~ 28,000 TKENB / day</td>
      <td style="text-align:center"><a href="https://cchain.explorer.avax.network/">~ 1 second</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Huobi ECO (HECO)</td>
      <td style="text-align:center">100 TKENB / block*</td>
      <td style="text-align:center">~ 28,000 TKENB / day</td>
      <td style="text-align:center"><a href="https://hecoinfo.com/chart/blocktime">~ 3 seconds</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Polygon (Matic)</td>
      <td style="text-align:center">66 TKENB / block*</td>
      <td style="text-align:center">~ 28,000 TKENB / day</td>
      <td style="text-align:center"><a href="https://polygonscan.com/chart/blocktime">~ 2 seconds</a>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Fantom</td>
      <td style="text-align:center">33 TKENB / block*</td>
      <td style="text-align:center">~ 28,000 TKENB / day</td>
      <td style="text-align:center"><a href="https://ftmscan.com/chart/blocktime">~ 1 second</a>
      </td>
    </tr>
  </tbody>
</table>

\*10% of the emission rate goes to the [lottery](../features/lottery.md)

## Why TKENB Has A Hard Cap?

There's a hard cap on the supply of TKENB, with a burn mechanism making it a deflationary coin.

{% hint style="info" %}
TKENB primary function is to become a deflationary utility coin with decreased supply and increased value over time, to incentivize people to mine it, hold it, and use it.
{% endhint %}

## What is TKENB Deflationary Mechanism?

**Transfer tax**

There is a **14%** transfer tax on each transaction, of which 4% is **10%** of which will be sold to get BNB/AVAX/HT/MATIC/FTM \(depending on the chain\) through the contract automatically. Every time the total of this transfer tax exceeds 100,000 TKENB, the contract will automatically sell 100,000 TKENB for BNB/AVAX/HT/MATIC/FTM \(depending on the chain\) and adding to TKENB's contract.

This liquidity will be locked in TKENB contract, no one, not even the developers can withdraw it, and this liquidity will be used for automatic buy backs and burn. It is very beneficial for long term because it keep price level of TKENB and raises it over time.

**Other burning mechanisms**

* Developing games for burning mechanisms. Regular token burns are built into many of TKENB's products \(like a high burn rate of up to 100% of TKENB spent on lottery tickets\), with more on the way
* New ideas and developments such as Predictions betting in progress

