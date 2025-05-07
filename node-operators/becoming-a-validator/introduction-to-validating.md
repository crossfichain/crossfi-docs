# Introduction to Validating

### What is a validator?

The CrossFi Chain is based on [Tendermint](https://docs.tendermint.com/v0.34/introduction/what-is-tendermint.html) that relies on a set of validators to secure the network. The role of validators is to run a full node and participate in consensus by broadcasting votes that contain cryptographic signatures signed by the validator's private key. Validators commit new blocks in the blockchain and receive revenue in exchange for their work. Validators must also participate in governance by voting on proposals. Validators are weighted according to their total stake.



### What are the responsibilities of a validator?

Validators have two main responsibilities:

* **Be able to constantly run a correct version of the software:** Validators must ensure that their servers are always online and their private keys are not compromised.
* **Actively participate in governance:** Validators are required to vote on every proposal.

Additionally, validators are expected to be active members of the community. Validators must always be up-to-date with the current state of the ecosystem so that they can easily adapt to any change

### What is staking?

The CrossFi Chain is a public Proof-Of-Stake (PoS) blockchain, meaning that the weight of validators is determined by the amount of staking tokens (MPX) bonded as collateral. These MPX tokens can be self-delegated directly by the validator or delegated to the validator by other MPX holders.

Any user in the system can declare their intention to become a validator by sending a `create-validator` transaction to become validator candidates.

The weight (i.e. voting power) of a validator determines whether they are an active validator. The active validator set is limited to [an amount](https://xfiscan.com/validators) that changes over time.

### What is a validator commission?

Revenue received by a validator's pool is split between the validator and their delegators. The validator can apply a commission on the part of the revenue that goes to their delegators. This commission is set as a percentage. Each validator is free to set their initial commission, maximum daily commission change rate, and maximum commission. The CrossFi Chain enforces the parameter that each validator sets. The maximum commission rate is fixed and cannot be changed. However, the commission rate itself can be changed after the validator is created as long as it does not exceed the maximum commission.

### What is a full node?

A full node is a server running a chain's _binary_ (its software) that fully validates transactions and blocks of a blockchain and keeps a full record of all historic activity. A full node is distinct from a pruned node that processes only block headers and a small subset of transactions. Running a full node requires more resources than a pruned node. Validators can decide to run either a full node or a pruned node, but they need to make sure they retain enough blocks to be able to validate new blocks.

Of course, it is possible and encouraged for users to run full nodes even if they do not plan to be validators.

You can find more details about the requirements in the Joining Mainnet Tutorial.

### What is a delegator?

Delegators are MPX holders who cannot, or do not want to, run a validator themselves. MPX holders can delegate MPX to a validator and obtain a part of their revenue in exchange. For details on how revenue is distributed, see [<mark style="color:blue;">What is the incentive to stake?</mark>](introduction-to-validating.md#what-is-the-incentive-to-stake) and [What is a validators commission?](introduction-to-validating.md#what-is-a-validator-commission) in this document.

Because delegators share revenue with their validators, they also share risks. If a validator misbehaves, each of their delegators are partially slashed in proportion to their delegated stake. This penalty is one of the reasons why delegators must perform due diligence on validators before delegating. Spreading their stake over multiple validators is another layer of protection.

Delegators play a critical role in the system, as they are responsible for choosing validators. Being a delegator is not a passive role. Delegators must actively monitor the actions of their validators and participate in governance. For details on being a delegator, read the [Delegator FAQ](https://hub.cosmos.network/main/delegators/delegator-faq.html).



### What is the incentive to run a validator?

Validators earn proportionally more revenue than their delegators because of the commission they take on the staking rewards from their delegators.

Validators also play a major role in governance. If a delegator does not vote, they inherit the vote from their validator. This voting inheritance gives validators a major responsibility in the ecosystem.



### Do validators need to be publicly identified?

No, they do not. Each delegator can value validators based on their own criteria. Validators are able to register a website address when they nominate themselves so that they can advertise their operation as they see fit. Some delegators prefer a website that clearly displays the team operating the validator and their resume, while other validators might prefer to be anonymous validators with positive track records.
