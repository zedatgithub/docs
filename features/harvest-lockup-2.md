# ⏳ Harvest Lockup

**Harvest lockup** mechanism is implemented where harvesting is possible only once the **harvest** **lockup timer** expires. The remaining time until harvesting becomes possible is shown on each farm/pool card.

This feature helps us limiting the harvesting frequency and prevents farming arbitrage bots from constantly harvesting and dumping.

{% hint style="info" %}
The **harvest lockup** only locks users' _farming rewards!_   
Staked LP tokens in farms can be withdrawn at anytime.
{% endhint %}

You can check the harvest lockup times for [farms](harvest-lockup.md) and [pools](token-pools.md).

{% hint style="danger" %}
Unstaking before **harvest lockup** expiration time will result in the loss of the pending rewards and of the compounded amount. In case of [vaults](vaults.md) these will be instead sent to [Fess/Taxes](deposit-fee-redistribution.md), while in the case of [farms](harvest-lockup.md) and [pools](token-pools.md) these will remain on the TKENB contract. 
{% endhint %}



