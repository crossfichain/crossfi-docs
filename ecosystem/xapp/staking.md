# Staking

Staking in xAPP is the voluntary locking of LP tokens (`lpXFI`, `lpUSD`) in the rewards contract. While your LP tokens remain in the pool earning swap fees, the contract:

* **Distributes esXFI** (escrowed XFI) to you (for `lpXFI`).
* **Shares cross‑chain & trading fees** as **WETH** (for `lpXFI`).
* **Distributes XFI** (direct, liquid XFI) when you stake **`lpUSD`**.
* **Accumulates Bonus Points (BP)** every second, boosting your share of total rewards.

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

***

## Why Stake LP Tokens?

**Snowball effect**: the longer you stay staked, the more BP you earn and the larger your share of WETH & XFI/esXFI distributions.

| LP Token  | Rewards           |
| --------- | ----------------- |
| **lpXFI** | esXFI + WETH + BP |
| **lpUSD** | **XFI** + BP      |

***

***

## How Your Share Is Calculated

**Position Weight**

$$
{Weight}_i = LP_i + BP_i + ST_i
$$

* **LPₙ** = your staked LP tokens
* **BPₙ** = your accumulated Bonus Points (see below)
* **STₙ** = your current esXFI balance (each 1 esXFI also counts as “1” in weight)

**Reward Share**

$$
{Share}_i = \frac{\text{Weight}_i}{\sum_j LP_j ;+; \sum_j BP_j ;+; \sum_j ST_j}
$$

**Unstaking effects**

* **Partial unstake**: reduces $$LP_i$$, preserves remaining $$BP_i$$.
* **Full unstake**: resets $$BP_i$$ to zero immediately.

***

## How esXFI Is Earned & Vested

* **Earning**: each distribution allocates your share of new XFI as **esXFI** (for `lpXFI`).
* **Vesting**: esXFI matures linearly over the protocol’s vesting period (e.g. \~6 months).
* **Unstaked LP** slows vesting; **re‑staking** accelerates it.

***

## Step‑by‑Step Staking

1. **Check your LP balance**\
   Acquire LP tokens in **LP Tokens → Get LP**.
2. **Open the Staking page**\
   View “Available” vs. “Staked” LP amounts for `lpXFI` and `lpUSD`.
3. **Select a pool**\
   Click **Stake** next to `lpXFI` or `lpUSD`.
4. **Enter amount & confirm**\
   Optionally click **Max**; approve in your wallet.
5. **Done**\
   Your LP tokens switch to **Staked**; esXFI/WETH/XFI and BP counters update in real time.

**Unstake anytime**

* **Partial**: preserves remaining BP.
* **Full**: resets BP to 0 and stops new esXFI vesting.

***

## Real‑World Examples

**Example 1: Compounding**

1. Stake **1 000 lpXFI**.
2. After 1 month, earn **0.6 WETH** (plus some esXFI).
3. Swap WETH → XFI + xUSD → Add Liquidity → Receive \~30 lpXFI.
4. Stake the new LP → weight ↑, BP ↑ → next cycle rewards ↑.

**Example 2: Long‑Term Hold (`lpUSD`)**

* Stake **500 lpUSD** for 365 days → earn **\~500 BP** + **XFI**.
* Weight = 500 LP + 500 BP = 1 000.
* If total pool weight = 10 000, your share = 10 % of every XFI distribution.

***

## Optimal Strategies

| Goal                     | Action                                                   |
| ------------------------ | -------------------------------------------------------- |
| **Maximize APY**         | Stay staked ≥ 90–180 days; reinvest WETH/XFI weekly.     |
| **Minimize Volatility**  | Choose **lpUSD** (stablecoin pool) for XFI-only rewards. |
| **Balance Risk & Yield** | Split between `lpXFI` and `lpUSD` as needed.             |

***

## Mini‑FAQ

* **Do BP ever expire?**\
  No—as long as you don’t fully unstake, BP stay active and continue boosting your share.
* **Can I stake multiple LP pools at once?**\
  Yes—each pool’s rewards accumulate separately and sum together.
* **Does esXFI disappear if I unstake LP?**\
  No—already‑earned esXFI remains and continues vesting (just slower).
* **Where do I track my unlocked XFI?**\
  In **Escrow → Vesting status** or alongside your esXFI balance in the **Rewards** page.

***

## Conclusion

Staking LP tokens in xAPP turns your liquidity into a dual income stream for `lpXFI` plus direct XFI for `lpUSD`, all boosted by BP:

1. **lpXFI** → esXFI + WETH
2. **lpUSD** → XFI
3. **BP** → increases every distribution

Stake, compound, and watch your rewards snowball over time!
