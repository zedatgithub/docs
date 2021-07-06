# 🔒 Locked Liquidity

Locker contract locks the initial liquidity \(LP tokens\).  
This contract also holds the [Automatic Liquidity](automatic-liquidity.md) from [Fee/Tax Distribution](deposit-fee-redistribution.md).

The ownership of the Locker [contract](../tokenomics/contracts.md) will be transferred to the [Timelock](../security/timelock.md).

Assets in the Locker contract are locked and can not be withdrwan without the 24H delay imposed by the Timelock.

* Q: Why don't we just burn the liquidity or lock the liquidity on other platforms?
* A: If there is an upgrade of AMM, we can migrate the liquidity to our new version exchange.



