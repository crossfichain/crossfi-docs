# Governance (DAO)

{% embed url="https://xficonsole.com/proposals" %}

### Introduction

[Governance on XFI Console](https://xficonsole.com/proposals) is a comprehensive decentralized governance system that allows any community member to influence strategic and operational decisions within the CrossFi ecosystem. Based on [MPX (Mint Power) tokens](../../economy-overview/mpx-coin/), the Governance module ensures transparency, efficiency, and democracy in decision-making processes through smart contracts.

#### Core Goals and Principles

* **Decentralization:** Power is transferred directly to the community, without centralized governing bodies.
* **Transparency:** Every action, from creating a proposal to executing it, is recorded on the blockchain, enabling audits and analysis.
* **Encouraging Participation:** Economic and social incentives are aimed at increasing participant responsibility and actively involving them in the decision-making process.
* **Security and Stability:** Mechanisms are introduced to protect against abuses and ensure network stability even under changing market conditions.

These principles allow the system to adapt to changes while remaining flexible and reliable.

***

### Participant Roles

In the CrossFi ecosystem, formal DAO governance is carried out exclusively by participants holding MPX tokens. These tokens grant the right to vote and make key decisions in the system. Consequently, the central governance role is shared by two main categories: delegators and validators. Additionally, there is a category of active community members who submit proposals and help shape public opinion. However, their influence is indirect and does not include direct voting in the DAO.

#### Delegators

Delegators are participants who hold MPX tokens and delegate their voting rights to chosen validators. In this way, they participate in the DAO’s governance by delegating their rights. Key points characterizing delegators’ role:

* **Direct Influence:** Delegators participate in votes, influencing the ecosystem’s strategic decisions.
* **Economic Motivation:** For participating, they receive a portion of the rewards distributed by validators (for example, XFI, esXFI, WETH).
* **Risks:** If an unreliable validator is chosen, delegators may face reduced income or lower participation efficiency, affecting their voting weight.

#### Validators

Validators are the key participants responsible for the network’s operation. They directly ensure blockchain security, validate transactions, create new blocks, and participate in voting on DAO initiatives. Key aspects of validators’ role:

* **Security Function:** Validators monitor the network’s correct operation, preventing potential attacks or failures.
* **Active Participation in Governance:** With voting rights, validators influence decisions related to protocol upgrades, fund distribution, and other strategic issues.
* **Economic Support:** For their work, validators receive commission fees, interest accruals, and bonuses, incentivizing them to maintain a high level of performance.

#### Active Community Members

This category includes all users who actively participate in discussions, propose ideas, and monitor the project’s development. Their contribution is important for shaping public opinion and identifying pressing issues; however:

* **Indirect Influence:** Users who do not hold MPX cannot directly vote in the DAO.
* **Informational Role:** Their proposals and discussions may be taken into account in the development of initiatives, but the final decision is made by the community through delegators and validators.

***

### Governance Process

The governance process in the system begins with creating proposals, which can be initiated by any participant holding a minimum amount of MPX. Proposals may address protocol upgrades, treasury fund distribution, or be text-based initiatives.

When creating a proposal, the initiator must provide a detailed description of its purpose, rationale, and expected outcomes. To confirm the seriousness of the intention, the participant pays a minimum deposit. If the deposit is insufficient, the proposal remains in “Deposit period” status until the deposit is supplemented.

After reaching the required deposit, the proposal moves to the voting stage. During this period, every MPX holder can cast a vote using the following options:

* **Vote for:** Support the proposal.
* **Vote against:** Oppose the proposal.
* **Abstain:** Refrain from choosing.
* **Veto:** A decisive rejection that can lead to automatic proposal dismissal.

If a delegator does not participate in the voting, their vote is automatically counted via the chosen validator. However, if the delegator independently makes a decision, their vote takes precedence over the inherited vote. The final decision is determined by parameters such as the overall quorum (for example, 40% of staked MPX), the percentage of “For” votes, and the threshold for “Veto” votes.

Users can also monitor the voting process, adjust their votes (with a small fee for changes), and track results in real time using analytical dashboards.

***

### Execution of Decisions and Feedback

After a successful vote, the system automatically implements changes using smart contracts. This may include updating software, transferring funds to specified addresses, or adjusting the network’s economic parameters. All changes are recorded and made available for subsequent analysis, increasing participants’ trust in the system.

***

### Protection and Incentive Mechanisms

Several special mechanisms are in place to protect against abuses and ensure network stability:

* **Limiting Validators:** The number of validators is capped at 64, reducing the risk of power concentration.
* **Using Sentry Nodes:** Additional nodes protect against DDoS attacks and help respond to threats quickly.
* **Sanctions:** If a validator violates the rules, they may be subject to slashing—the loss of part of their staked tokens. The initiator’s deposit may be withheld if the veto threshold is exceeded.

Economic incentives for participants are expressed through regular payouts, bonuses for long-term participation, and additional rewards for active engagement in governance. These measures not only protect the network but also stimulate ecosystem growth.

***

### Governance Integration into the Ecosystem

Decisions made through Governance affect key components of the CrossFi ecosystem. For instance, changes to staking parameters, the conditions of liquidity pools, or new partnerships can be implemented through voting. This approach enables quick responses to changing market conditions and supports the platform’s stability.

***

### Submitting Proposals and Voting in Practice

#### Step-by-Step Guide: Creating a Proposal

{% stepper %}
{% step %}
**Access XFI Console:**&#x20;

Ensure you have at least 1 MPX in your wallet.
{% endstep %}

{% step %}
**Open GOV:**&#x20;

Go to the GOV tab and click “Create proposal.”
{% endstep %}

{% step %}
**Choose a Type:**&#x20;

Software upgrade, Community pool spend, or Text.
{% endstep %}

{% step %}
**Fill Out Parameters:**

* **Software upgrade:** version, activation block.
* **Community pool spend:** amount, address, purpose.
* **Text:** only title and description.
{% endstep %}

{% step %}
**Make a Deposit:**

&#x20;Minimum 1 MPX. If the deposit is insufficient, the proposal status remains “Deposit period.”
{% endstep %}

{% step %}
**Publish:**&#x20;

Once the deposit threshold is reached, the proposal moves into the “Voting period.”
{% endstep %}
{% endstepper %}

#### Voting Process

{% stepper %}
{% step %}
**View Details:**

&#x20;In the GOV tab, select the proposal of interest and review its current status.
{% endstep %}

{% step %}
**Choose a Voting Option:**

“Vote for,” “Vote against,” “Abstain,” or “Veto.”
{% endstep %}

{% step %}
**Change Vote:**

Allowed until the voting ends, but an additional fee is charged.
{% endstep %}

{% step %}
**Track Results:**&#x20;

After the voting period ends, the system announces the results.
{% endstep %}
{% endstepper %}

***

### Frequently Asked Questions (FAQ)

**Can I vote if I have very few MPX?**\
Yes, but your voting weight will be lower compared to large holders. If you wish, you can delegate your tokens to a reliable validator.

**What if a validator acts against my interests?**\
Re-delegate your delegated tokens to another validator after the “unbonding” period.

**What are the penalties for abuses?**\
If a validator breaks the rules, they may be slashed—meaning they lose part of their staked tokens. If a proposal fails due to veto thresholds, the initiator’s deposit is not returned.

**What happens if there are too many “No with veto” votes?**\
The proposal is rejected, and the initiator’s deposit is withheld by the system.

**Can I participate in Governance without MPX tokens?**\
Direct voting is unavailable; however, you can submit ideas, join discussions, help shape public opinion, and engage in trading activities.

***

### The Future of Governance in CrossFi

In the long term, the Governance module plans to expand its set of analytical tools, enhance transparency, and increase opportunities for collaboration with other blockchain projects. This will make the decision-making process more transparent and community participation even more active and effective. Potential development directions include:

* **Analytical Expansion:** Adding public monitoring dashboards for in-depth analysis of votes, proposals, and statistics.
* **Improved UX:** Creating additional hints that simplify understanding Governance mechanics.
* **Multi-Chain Integration:** Interacting with other networks to attract new users and tokens to the ecosystem.

#### In Conclusion

Governance on XFI Console is the foundation of decentralized management in the CrossFi ecosystem. Combining transparent processes, smart contract–based automation, and the active engagement of all community layers ensures the system’s reliability and flexibility. This approach not only enables a prompt response to changes but also stimulates innovation, contributing to the platform’s sustainable development.
