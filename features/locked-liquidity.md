# 🔒 Locked Liquidity

The **Locker** contract locks and safeguards the initial liquidity \(LP tokens\) and also the [Automatic Liquidity](automatic-liquidity.md) created from [Fee/Tax Distribution](deposit-fee-redistribution.md).

The ownership of the **Locker** [contract](../tokenomics/contracts.md) will be transferred to the [Timelock](../security/timelock.md).

Assets in the **Locker** contract can not be withdrawn without the 24H delay imposed by the Timelock.

* Q: Why don't we just burn the liquidity or lock the liquidity on other platforms?
* A: If there is an upgrade of the AMM, we can migrate the liquidity to our new version exchange.



