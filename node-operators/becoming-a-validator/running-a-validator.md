# Running a Validator

### Validator Maintenance&#x20;

Running an effective operation is key to avoiding unexpected unbonding or slashing. Operations must be able to respond to attacks and outages, as well as maintain security and isolation in the data center.

Validators are expected to perform regular software updates to accommodate chain upgrades and bug fixes. It is suggested to consider using [Cosmovisor](https://docs.cosmos.network/v0.45/run-node/cosmovisor.html) to partially automate this process.

### Slashing Conditions&#x20;

If a validator misbehaves, their delegated stake is partially slashed. Two faults can result in slashing of funds for a validator and their delegators:

* **Double signing:** If someone reports on chain A that a validator signed two blocks at the same height on chain A and chain B, and if chain A and chain B share a common ancestor, then this validator gets slashed by 5% on chain A.
* **Downtime:** If a validator misses more than `50%` of the last `100` blocks, they are slashed by 0.00%.

### Self-Delegation&#x20;

Self-delegation is a delegation of MPX from a validator to themselves. The delegated amount can be increased by sending a `delegate` transaction from your validator's `application` application key.

### Are validators required to self-delegate MPX?

Yes, they do need to self-delegate at least `1 MPX`. Even though there is no obligation for validators to self-delegate more than `1 MPX`, delegators want their validator to have more self-delegated MPX in their staking pool. In other words, validators share the risk.

In order for delegators to have some guarantee about how much shared risk their validator has, the validator can signal a minimum amount of self-delegated MPX. If a validator's self-delegation goes below the limit that it predefined, the validator gets jailed and kicked out of the active set of validators while its delegators remain bonded to it.

Note however that it's possible that some validators decide to self-delegate via a different address for security reasons.

### Is there a minimum amount of MPX that must be delegated to be an active (bonded) validator?

The minimum is 1 MPX. But the network is currently secured by much higher values. You can check the minimum required MPX to become part of the active validator set on the [XFI Scan validator page.](https://xfiscan.com/validators)

### How do delegators choose their validators?

Delegators are free to choose validators according to their own subjective criteria. Selection criteria includes:

* **Amount of self-delegated MPX:** Number of MPX a validator self-delegated to themselves. A validator with a higher amount of self-delegated MPX indicates that the validator is sharing the risk and experienced consequences for their actions.
* **Amount of delegated MPX:** Total number of MPX delegated to a validator. A high voting power shows that the community trusts this validator. Larger validators also decrease the decentralization of the network, so delegators are suggested to consider delegating to smaller validators.
* **Commission rate:** Commission applied on revenue by validators before the revenue is distributed to their delegators.
* **Track record:** Delegators review the track record of the validators they plan to delegate to. This track record includes past votes on proposals and historical average uptime.
* **Community contributions:** Another (more subjective) criteria is the work that validators have contributed to the community, such as educational content, participation in the community channels, contributions to open source software, etc.

Apart from these criteria, validators send a `create-validator` transaction to signal a website address to complete their resume. Validators must build reputation one way or another to attract delegators. For example, a good practice for validators is to have a third party audit their setup. Note though, that the Tendermint team does not approve or conduct any audits themselves.&#x20;



### What does 'participate in governance' entail?

Validators and delegators on the CrossFi Chain can vote on proposals to change operational parameters (such as the block gas limit), coordinate upgrades, or make a decision on any given matter.

Validators play a special role in the governance system. As pillars of the system, validators are required to vote on every proposal. It is especially important since delegators who do not vote inherit the vote of their validator.

### What does staking imply?

Staking MPX can be thought of as a safety deposit on validation activities. When a validator or a delegator wants to retrieve part or all of their deposit, they send an `unbonding` transaction. Then, MPX undergoes a **3-week unbonding period** during which they are liable to being slashed for potential misbehaviors committed by the validator before the unbonding process started.

Validators, and by association delegators, receive block rewards, fees, and have the right to participate in governance. If a validator misbehaves, a certain portion of their total stake is slashed. This means that every delegator that bonded MPX to this validator gets penalized in proportion to their bonded stake. Delegators are therefore incentivized to delegate to validators that they anticipate will function safely.

### Can a validator run away with their delegators' MPX?

By delegating to a validator, a user delegates voting power. The more voting power a validator have, the more weight they have in the consensus and governance processes. This does not mean that the validator has custody of their delegators' MPX. **A validator cannot run away with its delegator's funds**.

Even though delegated funds cannot be stolen by their validators, delegators' tokens can still be slashed by a small percentage if their validator suffers a [slashing event](running-a-validator.md#what-are-the-slashing-conditions), which is why we encourage due diligence when[ selecting a validator.](running-a-validator.md#how-do-delegators-choose-their-validators)

### How often is a validator chosen to propose the next block? Does frequency increase with the quantity of bonded MPX?

The validator that is selected to propose the next block is called the proposer. Each proposer is selected deterministically. The frequency of being chosen is proportional to the voting power (i.e. amount of bonded MPX) of the validator. For example, if the total bonded stake across all validators is 100 MPX and a validator's total stake is 10 MPX, then this validator is the proposer \~10% of the blocks.

### How can a validator safely quit validating on the CrossFi Chain?

If a validator simply shuts down their node, this would result in the validator and their delegators getting slashed for being offline. The only way to safely exit a validator node running on the CrossFi Chain is by unbonding the validator's self-delegated stake so that it falls below its minimum self-delegation limit. As a result, the validator gets jailed and kicked out of the active set of validators, without getting slashed. They can then proceed to shut down their node without risking their tokens.

It's highly advised to inform your delegators when doing this, as they will still be bonded to your validator after it got jailed. They will need to manually unbond and they might not have been made aware of this via their preferred wallet application.



### What is the incentive to stake?

Each member of a validator's staking pool earns different types of revenue:

* **Block rewards:** Native tokens of applications (e.g. MPX on the CrossFi Chain) run by validators are inflated to produce block provisions. These provisions exist to incentivize MPX holders to bond their stake. Non-bonded MPX are diluted over time.
* **Transaction fees:** The CrossFi Chain maintains an allow list of tokens that are accepted as fee payment. The initial fee token is the `atom`.

This total revenue is divided among validators' staking pools according to each validator's weight. Then, within each validator's staking pool the revenue is divided among delegators in proportion to each delegator's stake. A commission on delegators' revenue is applied by the validator before it is distributed.

### How are block rewards distributed?

Block rewards are distributed proportionally to all validators relative to their voting power. This means that even though each validator gains MPX with each reward, all validators maintain equal weight over time.

For example, 10 validators have equal voting power and a commission rate of 1%. For this example, the reward for a block is 1000 MPX and each validator has 20% of self-bonded MPX. These tokens do not go directly to the proposer. Instead, the tokens are evenly spread among validators. So now each validator's pool has 100 MPX. These 100 MPX are distributed according to each participant's stake:

* Commission: `100*80%*1% = 0.8 MPX`
* Validator gets: `100\*20% + Commission = 20.8 MPX`
* All delegators get: `100\*80% - Commission = 79.2 MPX`

Then, each delegator can claim their part of the 79.2 MPX in proportion to their stake in the validator's staking pool.

### How are fees distributed?

Fees are similarly distributed with the exception that the block proposer can get a bonus on the fees of the block they propose if the proposer includes more than the strict minimum of required precommits.

When a validator is selected to propose the next block, the validator must include at least 2/3 precommits of the previous block. However, an incentive to include more than 2/3 precommits is a bonus. The bonus is linear: it ranges from 1% if the proposer includes 2/3rd precommits (minimum for the block to be valid) to 5% if the proposer includes 100% precommits. Of course the proposer must not wait too long or other validators may timeout and move on to the next proposer. As such, validators have to find a balance between wait-time to get the most signatures and risk of losing out on proposing the next block. This mechanism aims to incentivize non-empty block proposals, better networking between validators, and mitigates censorship.

For a concrete example to illustrate the aforementioned concept, there are 10 validators with equal stake. Each validator applies a 1% commission rate and has 20% of self-delegated MPX. Now comes a successful block that collects a total of 1025.51020408 MPX in fees.

First, a 2% tax is applied. The corresponding MPX go to the reserve pool. The reserve pool's funds can be allocated through governance to fund bounties and upgrades.

* `2% * 1025.51020408 = 20.51020408` MPX go to the reserve pool.

1005 MPX now remain. For this example, the proposer included 100% of the signatures in its block so the proposer obtains the full bonus of 5%.

To solve this simple equation to find the reward R for each validator:

`9*R + R + R*5% = 1005 ⇔ R = 1005/10.05 = 100`

* For the proposer validator:
  * The pool obtains `R + R * 5%`: 105 MPX
  * Commission: `105 * 80% * 1%` = 0.84 MPX
  * Validator's reward: `105 * 20% + Commission` = 21.84 MPX
  * Delegators' rewards: `105 * 80% - Commission` = 83.16 MPX (each delegator is able to claim its portion of these rewards in proportion to their stake)
* For each non-proposer validator:
  * The pool obtains R: 100 MPX
  * Commission: `100 * 80% * 1%` = 0.8 MPX
  * Validator's reward: `100 * 20% + Commission` = 20.8 MPX
  * Delegators' rewards: `100 * 80% - Commission` = 79.2 MPX (each delegator is able to claim their portion of these rewards in proportion to their stake)



###
