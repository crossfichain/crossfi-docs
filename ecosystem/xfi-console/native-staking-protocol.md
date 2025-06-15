# Native Staking Protocol

{% embed url="https://xficonsole.com/validators" %}

## Introduction

The Native Staking Protocol is your key to generating passive income within the CrossFi ecosystem. It enables holders of the XFI token not only to store their assets but also to actively participate in the network, earning rewards and enhancing its security. In the CrossFi ecosystem, staking is implemented through the MPX token, which is used for delegation and participation in consensus. Thanks to the integration of EVM and Cosmos, it is now possible to use XFI as a staking asset: XFI is locked on the EVM side, after which the system automatically issues an equivalent amount of MPX and delegates it to a validator. This allows XFI holders to earn income from network participation without needing to interact with multiple tokens or directly with the Cosmos infrastructure.

**Why is this important for you?** Staking XFI offers several advantages. First, it incentivizes holders to retain their tokens rather than sell them, thereby reducing market selling pressure and potentially supporting an increase in the XFI price over time. Second, by delegating tokens through the Native Staking Protocol, you help the network become more decentralized, increasing the overall share of independent validators. Control over staking shifts to the community instead of remaining solely in the hands of the CrossFi team, making the network more reliable and resilient. Finally, you receive rewards in XFI – the primary token of the network – effectively turning your assets into a source of stable income.

The protocol operates on the basis of the Delegated Proof-of-Stake (DPoS) model. This means that network validators create new blocks and receive rewards for doing so, while delegators (token holders who allocate their tokens to validators) receive a share of those rewards. Normally, this process requires the use of MPX – the internal asset of the Cosmos part of CrossFi. With Native Staking, there is no need to worry about these complexities: your XFI is automatically converted into MPX within the system and delegated to a validator. All that is required is a wallet with XFI and the desire to begin – no extra steps, no technical knowledge, just income and participation in the CrossFi ecosystem.

Thus, any XFI holder can participate in staking and earn rewards without delving into the technical details of operating two blockchains.

## Protocol Fundamentals and CrossFi Architecture

The CrossFi ecosystem consists of two interconnected modules:

* **EVM (Ethereum Virtual Machine)** — responsible for executing smart contracts (similar to Ethereum within CrossFi).
* **Cosmos SDK** — ensures network consensus, high transaction speed, and validator management (the basis of the L1 network).

Each CrossFi user has two linked addresses: an EVM address (in the 0x… format, used, for example, in MetaMask) and a corresponding Cosmos address (in the mx1… format). This linked pair (often referred to as a _twin address_) combines the functionality of both modules for simple and efficient staking.

When a user sends XFI to stake, the tokens are locked in a smart contract on the EVM side. The system then automatically issues an equivalent amount of MPX on the user’s Cosmos address and immediately delegates it to a chosen validator. Although the user does not directly manage MPX, the system guarantees full transparency and ensures that the value of the locked XFI is accurately reflected by the issued MPX.

#### Roles of XFI and MPX Tokens

* **XFI** — the primary liquid token of the CrossFi network. Its issuance is limited, and new tokens are generated only as rewards for validators creating blocks. XFI is freely traded on exchanges.
* **MPX** — the utility token for staking in the Cosmos part. It is not traded on the open market; its nominal value is fixed at $0.04. MPX is issued as needed to support staking and delegation to validators.

#### How Is MPX Issued?

The amount of MPX issued by the protocol for delegation is calculated using the formula:

```
MPX = (Number of XFI × current price of XFI in USD) / 0.04 USD
```

For example:

* If XFI is trading at $0.08, 1 XFI will yield 2 MPX (since $0.08 / $0.04 = 2).
* If XFI rises to $0.40, 1 XFI will yield 10 MPX ($0.40 / $0.04 = 10).

Thus, the total MPX delegated always matches the current value of XFI, while the original XFI remains locked in the smart contract, “backing” the issued MPX. To prevent an excessive increase in the total supply of MPX, the protocol periodically burns an equivalent amount of MPX from CrossFi’s reserve (o-MPX) when issuing new tokens to users (b-MPX). As a result, the CrossFi team’s share of the overall stake gradually decreases, while the community’s share increases without negatively impacting the token’s economy.

#### Earning and Utilizing Rewards

After delegation, the validator earns rewards in XFI for every block created, which are then distributed proportionally among all delegators. These rewards accumulate within the protocol and are available for:

* Withdrawal (**Claim**);
* Reinvestment into the stake (**Compound**).

Below, the stages of staking — from the initial delegation (Bond) to exiting (Unbond), including reward withdrawal (Claim) and reinvestment (Compound) — are described in detail.

## Staking XFI: From Bond to Unbond

Staking XFI is a straightforward cycle consisting of several steps. Each step ensures clear management of your earnings.

### Bond – Initiating Staking

Everything begins with the **Bond** operation, where you send your XFI into staking. On the staking page (within the CrossFi interface), you choose the amount of tokens to stake (a minimum of 50 XFI) and select the validator to whom you wish to delegate your assets. This choice can be made manually—considering the validator’s reliability and fees—or by using a referral link that automatically assigns a specific validator.

After clicking the “Bond” button and confirming the transaction via your wallet (e.g., MetaMask), the smart contract locks your XFI on the EVM side. Subsequently, the system issues the corresponding amount of MPX and delegates them to the validator on the Cosmos side. Although this process occurs behind the scenes, the interface immediately shows the outcome: the amount of XFI locked, the volume of MPX delegated, and the expected yield (such as the annual percentage rate, APR). At this point, your tokens begin to generate profits, and you become an active participant in the CrossFi network.

### Earning Rewards and Compound – Boosting Your Returns

Once XFI is staked, the validator starts earning rewards in XFI for each block produced. These rewards accumulate on a separate balance within the interface and are available for either withdrawal or reinvestment.

**Compound (Reinvestment)** allows you to add the accumulated rewards back into your main stake, thus increasing your future earnings through compound interest. The minimum amount required for reinvestment is 10 XFI. Once the rewards reach this threshold, the Compound button becomes active. When you click it and confirm the transaction via your wallet, the protocol:

* Transfers the accrued rewards from your reward balance into your main stake.
* Issues additional MPX corresponding to the reinvested XFI and automatically delegates them to the same validator.
* As a result, your overall stake increases and the interface updates the locked XFI and delegated MPX figures, recalculating your expected yield.

Regular use of Compound boosts your effective yield (APY) compared to the base APR, allowing you to maximize long-term returns. You have the flexibility to reinvest as frequently as you prefer—weekly, monthly, or whenever a substantial reward amount is reached. While Compound is optional, reinvestment typically enhances profitability over time.

### Claim Rewards – Withdrawing Your Profits

The **Claim Rewards** operation lets you withdraw your accumulated XFI rewards to your wallet. You can use these funds for trading, participating in other projects, or simply securing your gains.

On the staking page, the available reward amount is clearly displayed. Claim has no minimum threshold, so you can withdraw any accumulated balance; however, it may be more cost-effective to wait until a larger sum is available due to network fees. To initiate a withdrawal, simply click “Claim” and confirm the transaction in your wallet (e.g., MetaMask). The protocol then transfers the specified amount of XFI to your primary EVM address.

When you perform a Claim operation, all of your accrued rewards are transferred to your wallet. There are no deductions or protocol-level fees applied to your claimed XFI. This ensures that users receive the full amount of their earned rewards.

Following a Claim, your accumulated reward balance decreases accordingly, while your original staked XFI and delegated MPX remain unchanged, continuing to generate new rewards. You can perform Claim at any time, offering flexible asset management.

### Unbond – Exiting Staking and Retrieving XFI

When it’s time to retrieve your originally staked XFI—whether to sell assets or conclude your staking participation—you initiate the **Unbond** operation. This process finalizes your staking cycle and returns your funds to your wallet.

To start, click the “Unbond” button in the CrossFi interface and confirm the transaction via your wallet. A standard unbonding period of 15 days then begins, which is a common measure in DPoS networks to protect against sudden mass withdrawals and potential attacks. During these 15 days, your delegated MPX gradually unwind from the validator, while your XFI remains locked in the smart contract and ceases to generate new rewards.

At the end of the period, the system automatically:

* Burns the b-MPX tokens that were issued and delegated on your behalf.
* Unlocks the original XFI tokens in the EVM smart contract.
* Transfers the unlocked XFI, along with any unclaimed rewards, back to your wallet.

After the Unbond process completes, your staking balance is reset to zero, and you regain full control of your funds.

***

## **Twin Colossus Program: An Incentive for Validators and Decentralization**

The Twin Colossus Program is a CrossFi initiative aimed at redistributing MPX tokens in favor of independent validators and enhancing overall network decentralization.

A significant portion of the MPX stake was previously controlled by the CrossFi team, which potentially impacted the network's robustness and independence. Twin Colossus addresses this issue by temporarily delegating large volumes of MPX to independent validators, giving them the opportunity to attract new users through native XFI staking.

### **How Does Twin Colossus Work?**

The program consists of several sequential phases:

**Phase 0 – Preparation:**\
CrossFi preemptively burns a portion of its own MPX (for example, 2 billion tokens) to balance the stake ratios before the program starts.

**Phase 1 – Advance Allocation:**\
CrossFi selects validators that meet strict criteria (high uptime, reliability, activity, and a personal stake of over 10,000 MPX) and delegates large volumes of MPX to them. These tokens serve as a temporary "advance," significantly increasing the share of the selected validators in the network.

**Phase 2 – Delegator Attraction (30 Days):**\
Over the next month, validators actively attract new delegators through native XFI staking, using referral links and leveraging their reputation. The more new users stake XFI—and automatically delegate MPX—to a validator, the more of the initial advance that validator can retain.

**Phase 3 – Finalization and Redistribution:**\
At the end of the 30-day period, the system evaluates the results. Any unused portion of the advanced MPX is returned to CrossFi. From this amount, half is burned to reduce the overall supply, and the remaining half is redistributed among the top 20 most successful validators, proportional to the stake they attracted.

As a result, validators that successfully attract users significantly increase their long-term stake, while less successful ones revert to their previous levels.

### **Why Is This Important for Users?**

By delegating XFI tokens to a validator through a referral link during the Twin Colossus program, users directly support that validator and contribute to enhanced decentralization of the network. This leads to a more stable platform and may improve staking conditions through increased competition among validators (for example, by lowering fees).

Twin Colossus is a temporary but crucial initiative that allows the community to gain greater control over the network, while CrossFi gradually reduces its own stake without abrupt changes. Once the program concludes, the native staking protocol continues to operate in the normal mode, albeit with a more resilient and decentralized structure.

## Reliability, Security, and Delegator Protection

The Native Staking Protocol accounts for the inherent risks of blockchain staking and implements robust mechanisms to safeguard user assets.

### Infrastructure Security

All staking operations are executed through audited smart contracts and secure wallets. Critical actions (Bond, Compound, Claim, Unbond) require explicit confirmation via your crypto wallet, guaranteeing that only you can manage your XFI. Your tokens remain securely locked in the smart contract throughout the staking period, immune to unauthorized spending or theft. In the event of technical issues—such as network congestion—the protocol will automatically retry the transaction or safely revert changes, ensuring complete asset protection.

### Selection of Reputable Validators

CrossFi carefully selects validators for automatic delegation based on stringent criteria:

* **Uptime:** Validators must maintain nearly 100% operational uptime.
* **Personal Stake:** Validators are required to invest significant funds in their own nodes, demonstrating commitment and responsibility.
* **Validator Fees:** Lower fees ensure better returns for delegators.
* **Track Record:** Validators with no history of slashing or rule violations are preferred.

Even if you do not choose a validator manually or via a referral link, the protocol allocates your stake in a risk-minimized manner, ensuring stable income. CrossFi continuously monitors validator reputations and can exclude or suspend any that pose potential threats.

***

## User Experience and Interface

The staking interface streamlines the staking process, presenting all crucial information in a clear and concise manner:

* **Balance Overview:** Displays both total XFI and the portion currently staked.
* **Delegated MPX:** Shows the amount of MPX automatically delegated to your chosen validator.
* **Current Rates:** Provides real-time exchange rates (XFI/USDT and nominal MPX/USDT) along with your effective conversion rate.
* **Accrued Rewards:** Clearly indicates the rewards that have been generated.
* **Operational Status:** Provides updates on processes such as Unbonding, including time remaining.

Four main functions—Bond, Compound, Claim, and Unbond—allow you to manage staking with ease. Each action comes with context-sensitive prompts (for example, reminding you of the 10 XFI minimum for Compound) and requires confirmation via your wallet, ensuring you stay in control at all times. Notifications keep you informed of successful transactions or any important changes in your staking status. The interface eliminates the need to understand the underlying EVM or Cosmos mechanisms—simply use your XFI and follow the steps.

***

## Glossary of Key Terms

* **XFI:** The primary token of CrossFi, used for staking and earning rewards. It is liquid and traded on exchanges.
* **MPX:** A utility token used in the Cosmos module for staking. It is issued automatically, not directly managed by users, and has a fixed nominal value (e.g., $0.04).
* **Delegated Proof-of-Stake (DPoS):** A consensus mechanism where validators produce blocks and share rewards with delegators based on stake contributions.
* **Bond:** The operation of locking XFI into the staking protocol, which triggers the issuance of MPX for delegation.
* **Compound:** The process of reinvesting accrued XFI rewards into the main stake, thus boosting future yields through compound interest.
* **Claim Rewards:** The operation of withdrawing accrued XFI rewards to your wallet.
* **Unbond:** The operation for exiting staking, involving a 15-day waiting period after which the staked XFI and any remaining rewards are returned.
* **Twin Address:** A paired set of addresses for a CrossFi user — an EVM address for XFI and a Cosmos address for MPX. The protocol links them to ensure a one-to-one correspondence between staked XFI and delegated MPX.
* **Twin Colossus:** A program aimed at redistributing a portion of CrossFi’s MPX to independent validators, thereby increasing network decentralization. It is conducted in multiple phases and factors in referrals.
* **Referral Link:** A URL that automatically directs staking to a specific validator by including its identifier in the link.
* **APR and APY:** Annual Percentage Rate (basic yield) and Annual Percentage Yield (yield with compounding), respectively.
