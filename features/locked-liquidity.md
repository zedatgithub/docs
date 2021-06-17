# 🔒 Locked Liquidity

Locker contract locks the initial liquididity \(LP tokens\)   
This contract also hold the [Automatic Liquidity](automatic-liquidity.md) from the [Fee/Tax Distribution](deposit-fee-redistribution.md).

The owner of Locker will be transferred to the [Timelock](../security/timelock.md) once the contract deployed.

* Q: Why don't we just burn the liquidity or lock the liquidity on other platforms?
* A: If there is an upgrade of AMM, we can migrate the liquidity to our new version exchange.



