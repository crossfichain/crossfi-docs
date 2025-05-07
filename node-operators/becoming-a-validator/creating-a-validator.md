# Creating A Validator

Any participant in the network can signal that they want to become a validator by sending a `create-validator` transaction, where they must fill out the following parameters:

* **Validator's `PubKey`:** The private key associated with this Tendermint `PubKey` is used to sign _prevotes_ and _precommits_.
* **Validator's Address:** Application level address that is used to publicly identify your validator. The private key associated with this address is used to delegate, unbond, claim rewards, and participate in governance.
* **Validator's name (moniker)**
* **Validator's website (Optional)**
* **Validator's description (Optional)**
* **Initial commission rate**: The commission rate on block rewards and fees charged to delegators.
* **Maximum commission:** The maximum commission rate that this validator can charge. This parameter is fixed and cannot be changed after the `create-validator` transaction is processed.
* **Commission max change rate:** The maximum daily increase of the validator commission. This parameter is fixed cannot be changed after the `create-validator` transaction is processed.
* **Minimum self-delegation:** Minimum amount of MPX the validator requires to have bonded at all time. If the validator's self-delegated stake falls below this limit, their validator gets jailed and kicked out of the active validator set.

After a validator is created, MPX holders can delegate MPX to them, effectively adding stake to the validator's pool. The total stake of an address is the combination of MPX bonded by delegators and MPX self-bonded by the validator.

From all validator candidates that signaled themselves, the 150 validators with the most total stake are the designated **validators**. If a validator's total stake falls below the top 150, then that validator loses its validator privileges. The validator cannot participate in consensus or generate rewards until the stake is high enough to be in the top 150. Over time, the maximum number of validators may be increased via on-chain governance proposal.

### What are hardware requirements?

A modest level of hardware specifications is initially required and rises as network use increases. Participating in the testnet is the best way to learn more. You can find the current hardware recommendations in the Joining Mainnet documentation.

Validators are recommended to set up [sentry nodes](https://docs.tendermint.com/v0.34/tendermint-core/validators.html) to protect your validator node from DDoS attacks.

### What are software requirements?

In addition to running a CrossFi Chain node, validators are expected to implement monitoring, alerting, and management solutions.&#x20;

### What are bandwidth requirements?

The Cosmos network has the capacity for very high throughput relative to chains like Ethereum or Bitcoin.

We recommend that the data center nodes connect only to trusted full nodes in the cloud or other validators that know each other socially. This connection strategy relieves the data center node from the burden of mitigating denial-of-service attacks.

Ultimately, as the network becomes more heavily used, multigigabyte per day bandwidth is very realistic.

### What are the different states a validator can be in?

After a validator is created with a `create-validator` transaction, the validator is in one of three states:

* `in validator set`: Validator is in the active set and participates in consensus. The validator is earning rewards and can be slashed for misbehavior.
* `jailed`: Validator misbehaved and is in jail, i.e. outside of the validator set.
  * If the jailing is due to being offline for too long (i.e. having missed more than `50%` out of the last `100` blocks), the validator can send an `unjail` transaction in order to re-enter the validator set.
  * If the jailing is due to double signing, the validator cannot unjail.
* `unbonded`: Validator is not in the active set, and therefore not signing blocks. The validator cannot be slashed and does not earn any reward. It is still possible to delegate MPX to an unbonded validator. Undelegating from an `unbonded` validator is immediate, meaning that the tokens are not subject to the unbonding period.
