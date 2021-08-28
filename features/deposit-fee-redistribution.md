# 💰 Fee/Tax Distribution

## Hourly Fee/Tax Distribution <a id="deposit-fee"></a>

* 30% of collected TKENB will be injected into the [Lottery](lottery.md)
* 50% of collected TKENB will be [🔥BURNED🔥](https://testnet.bscscan.com/token/0x8a5a76401ada8998603d982d8343752fec75972b?a=0x000000000000000000000000000000000000dEaD)
* 60% of the BUSD\*/BNB/BTCB/ETH will be converted to BUSD\* and will be held in the fee address as buyback reserve. From the fee address, every hour, `BUSD* value in buyback reserve/30/24` will be used for TKENB buybacks and added as [locked](locked-liquidity.md) TKENB-BUSD\* [liquidity](automatic-liquidity.md). The formula above ensures that the buyback reserve is not used up instantly but the BUSD\* amount in the buyback reserve is evenly split for hourly buybacks \(`24` hours/day\) over one month period \(`30` days\). The formula is applied every hour to the existing value in the buyback reserve
* 20% of the BUSD/BNB/BTCB/ETH will be sent to developer address for future development

_\* on Huobi Eco \(HECO\), USDT replaces BUSD_   
_\* on Polygon \(MATIC\), USDC replaces BUSD   
\* on Polygon, USDC replaces BUSD_

## Deposit Fee <a id="deposit-fee"></a>

When staking into NON NATIVE farms \(farms where the pair does not contain TKENB\), a **4% deposit fee** will be charged. Staking into NATIVE farms \(farms where the pair contains TKENB\) but **not** TKENB-BNB\*, a **1% deposit fee** will be charged. The deposit fee for for staking into TKENB-BNB\* is **0%**.

_\* HT on Huobi Eco \(HECO\), MATIC on Polygon, FTM on Fantom_

## Transfer Tax <a id="transfer-tax"></a>

For each transfer, an **4% transfer tax** is charged.

{% hint style="info" %}
The transfer tax applies **only** for transactions involving the TKENB
{% endhint %}

