# 🏧 Automatic Liquidity

Details about how we automatically provide liquidity to the NATIVE token pairs are described in [Fee/Tax Distribution](deposit-fee-redistribution.md) section. 

Basically, for creating, for example, TKENA-USDC LPs, we will use whatever **USDC** we collect from **deposit fees** charged for staking on NON NATIVE farms, while the **TKENA** will be bought back from collected **deposit fees**. Therefore, we will not sell NATIVE Tokens at any point and instead we buy.

So, how is the _Automatic Liquidity_ working for other projects and why it is bad \(as most projects have suffered instead of gaining because of this feature\):

Every time a transaction takes place, half of the amount from the transfer is kept as token while the other half is **sold** for USDC in order to create LP tokens for the TKENA-USDC farm.

Therefore, when somebody **BUYS** token, the contract automatically **SELLS** half of the tax fee for USDC making the price _go down_. And when somebody **SELLS** token, the contract automatically **SELLS** half of the tax fee for USDC making the price _go down_.

This feature creates constant _selling pressure_ so we decided against it.

Have a look at [Fee/Tax Distribution](deposit-fee-redistribution.md) for more on how the fees are used.

