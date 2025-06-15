# LP Tokens

Liquidity Provider Tokens (LP tokens) represent your share in a liquidity pool on the CrossFi decentralized exchange. By providing two tokens to a pool, you receive LP tokens, start earning trading fees, and gain access to additional rewards through staking.

<figure><img src="../../.gitbook/assets/image (3).png" alt="" width="563"><figcaption></figcaption></figure>

***

## Available Pools and LP Tokens

| LP Token  | Token Pair      | What the Pool Offers                                                                                              |
| --------- | --------------- | ----------------------------------------------------------------------------------------------------------------- |
| **lpXFI** | **XFI / xUSD**  | Main market of the network: high liquidity of XFI, highest volume of trading fees. In staking earns esXFI + WETH. |
| **lpUSD** | **USDC / xUSD** | Two stablecoins — low volatility, stable fee flow, ideal for conservative strategies.                             |

> In all pairs, the second token is xUSD — CrossFi's native stablecoin. It is issued with a 300% collateral in XFI and liquidated if the collateral falls to 200%.

***

## Why Hold LP Tokens

1. **Pool Fees** — every swap incurs a 1% fee. Your share of these fees is automatically capitalized in the pool, increasing the LP token price.
2. **Staking Rewards** — when you stake LP tokens in the **Staking** section, you receive:
   * **esXFI** — escrowed XFI, gradually becoming liquid XFI over time;
   * **WETH** — ETH from LayerZero bridge fees;
   * **Bonus Points (BP)** — loyalty points boosting your reward share.

***

## Reward Calculation Mechanics

The total pool reward in each distribution round is split proportionally by participant weight:

$$
Weight = LP_i + BP_i + ST_i
$$

$$
Share = Wei ght / (∑LP + ∑BP + ∑ST)
$$

* **LP** — number of your LP tokens.
* **BP** — bonus points. Earned continuously: +1 BP for every \~0.01 LP per day (\~100 BP per 1 LP annually). Reset to 0 on unstake.
* **ST** — amount of **esXFI** in your address; also boosts weight by compounding rewards.

The higher your combined components relative to the total across all participants, the more XFI and ETH you earn.

***

## How to Add Liquidity and Get LP Tokens

1. **Prepare assets** in equal dollar value (50 / 50):
   * lpXFI: XFI + xUSD
   * lpUSD: USDC + xUSD
2. **Go to “LP Tokens → Get LP”**, select a pool.
3. **Enter the amount** of one token — the system calculates the other.
4. Confirm two transactions:
   * `Approve` (one-time token approval);
   * `Add Liquidity` — deposit into the pool.
5. LP tokens will appear in your wallet — you are now a liquidity provider.

> Tip: If you lack the correct token ratio, perform a swap first in the Swap section.

***

## How to Remove Liquidity

1. **LP Tokens → Remove Liquidity**.
2. Select a pool, specify the number of LP tokens to burn.
3. Confirm the transaction — receive back your deposit + accumulated fees.

***

## How to Maximize Your Gains

| Strategy                     | Benefit                                                                        |
| ---------------------------- | ------------------------------------------------------------------------------ |
| **Long-term staking**        | BP accumulates over time, increasing weight — avoid interrupting stake.        |
| **Reward compounding**       | Convert WETH to XFI/xUSD → increase LP → boost weight, BP, future esXFI.       |
| **Monitor impermanent loss** | Watch price of first token: strong fluctuations cause IL; rebalance as needed. |

***

## Mini-FAQ

**Do I need to hold LP tokens for a full year to earn BP?**\
No. BP accrues every second proportionally. 100 BP ≈ 1 LP per year.

**What happens to BP if I partially withdraw liquidity?**\
BP decreases proportionally to withdrawn share. Full withdrawal resets BP to 0.

**Can I sell esXFI?**\
No, these are escrow tokens. They automatically convert into regular XFI on schedule as long as you remain staked.

***

## Summary

LP tokens are the foundation of DeFi income in CrossFi xAPP. By providing liquidity and staking the resulting LP tokens, you receive:

1. a constant stream of pool fees;
2. XFI rewards via esXFI;
3. ETH income in WETH;
4. bonus points that amplify future rewards.

The higher your contribution and the longer your participation, the bigger your share of the reward pie.
