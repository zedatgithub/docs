# ⏰ Boosted Farms

**Boosted Farms** is a unique and creative way of farming where each farm's multiplier is constantly being cycled between a **boosted** \(very-high APR\) and a **cool-down** mode \(lower APR\). 

The farm's multiplier changes at exact hours \(shown on each farm's card\), affecting everyone in the same way. 

Additionally, a **harvest lockup** mechanism is also implemented where harvesting is possible only once the **lockup time** expires. The remaining time until harvesting becomes possible is shown on each farm's card.

Both these features can help us limit the harvesting frequency and prevent farming arbitrage bots from constantly harvesting and dumping.

{% hint style="info" %}
The **harvest lockup** only locks users' _farming rewards -_ staked LP tokens  in farms can be withdrawn at anytime.
{% endhint %}

{% hint style="danger" %}
Unstaking before **harvest lockup** expiration time ****will result in the loss of the pending rewards and of the compounded amount, both of which will be instead sent to [Fee/Tax Distribution](deposit-fee-redistribution.md)
{% endhint %}

## Example

For example, the DEFI-BUSD farm has a multiplier changing cycle of **2 hours** and its multiplier cycles between **40x** and **4x** \(just these 2 values\). This means that, at the start, the farm will run with a multiplier of **40x** for **2 hours**. After the 2 hours have passed, harvesting becomes possible and the farm's multiplier changes from **40x** to **4x**, and the cycle will repeat.

## Farms 

Below is the list of farms available at launch and their boosted/cooldown rates:

| Farm  ID | Pairs | Boosted/Cooldown Rates |
| :---: | :--- | :---: |
| 1 | DEFI-BUSD LP                                                                                      | 40x / 4x |
| 2 | DEFI-USDC LP | 4x / 40x |
| 3 | DEFI-USDT LP | 40x / 4x |
| 4 | DEFI-DAI LP | 4x / 40x |
| 5 | BUSD-USDT LP | 10x / 1x |
| 6 | BUSD-DAI LP | 1x / 10x |
| 7 | USDC-BUSD LP | 10x / 1x |
| 8 | USDC-DAI LP | 1x / 10x |
| 9 | USDT-USDC LP | 10x / 1x |
| 10 | USDT-DAI LP | 1x / 10x |

