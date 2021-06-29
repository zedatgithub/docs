# 🔒 Locked Liquidity

Locker contract locks the initial liquidity \(LP tokens\)   
This contract also holds the [Automatic Liquidity](automatic-liquidity.md) from [Fee/Tax Distribution](deposit-fee-redistribution.md).

The owner of Locker [contract](../tokenomics/contracts.md) will be transferred to the [Timelock](../security/timelock.md)

Assests in the Locker contracts are locked and can not be withdrwan without Timelock delay of 24H

* Q: Why don't we just burn the liquidity or lock the liquidity on other platforms?
* A: If there is an upgrade of AMM, we can migrate the liquidity to our new version exchange.



