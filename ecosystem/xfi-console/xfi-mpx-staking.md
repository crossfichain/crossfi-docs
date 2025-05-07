# XFI-MPX Staking

{% embed url="https://xficonsole.com/validators" %}

### Overview

The XFI-MPX staking protocol is an integration of two blockchain networks—EVM and Cosmos—to create a unified system in which users can lock their XFI tokens and receive an equivalent amount of MPX. These MPX are automatically delegated to verified validators in the Cosmos network, allowing users to participate in staking with the ability to reinvest earnings (APY). This process is fully automated and does not require constant manual management. With this approach, users can accumulate rewards and increase profitability through compound interest.

When you transfer your XFI into the system, they are locked in a smart contract on the EVM side, and an equivalent amount of MPX is generated and sent to validators in the Cosmos network. If you decide to end staking, your original XFI will be returned along with the accrued profit, and the delegated MPX will be returned to the system’s general pool.

### Delegated Proof of Stake (DPoS) Mechanism

CrossFi Chain employs the Delegated Proof of Stake (DPoS) mechanism to ensure network security, stability, and consensus. Validators self-delegate a minimal amount of MPX to qualify for block creation and consensus responsibilities. Other network participants, known as delegators, may delegate their MPX to selected validators, thereby increasing the validators' total stakes and enhancing their chances of block creation.

Validators earn MPX rewards for successfully creating blocks and maintaining consensus within the network. Delegators receive a share of these validator rewards, making delegation economically advantageous for all participants. This structure ensures robust network security and promotes active community involvement through a balanced economic model.

Users leveraging MPX for staking not only contribute to the network’s resilience against potential threats but also benefit financially by receiving XFI rewards. The more MPX a user stakes compared to the total MPX staked in the network, the greater their individual rewards. However, as the total number of staked MPX grows, each participant’s individual reward share may decrease proportionally.

### Staking Mechanism

The staking process begins when a user transfers their XFI to a dedicated smart contract. After confirming the transaction via MetaMask, the system locks the XFI on the EVM side and issues an equivalent amount of MPX. These MPX are automatically delegated to validators selected based on strict criteria of reliability and economic efficiency.

The system regularly recalculates the MPX exchange rate relative to USDT (e.g., a fixed rate of $0.04) and the market rate of XFI to USDT, obtained from an exchange. This allows for determining the exact amount of MPX that will be issued for delegation. Every two weeks, the system automatically reinvests accumulated rewards, adding new MPX to the stake. This way, users earn income through compound interest.

If you decide to end staking, you need to press the "Unstake" button. The system will then return your original XFI along with the accrued earnings, and the delegated MPX will be redistributed back into the system’s general pool.

### Protection Against Validator Misconduct

In any blockchain network, there is always a risk of validator misconduct, such as block omissions or double signing of transactions. To minimize the impact of such incidents on users, the XFI-MPX protocol includes a slashing protection mechanism. Slashing is a penalty applied to validators for violating network rules, where 5% of the validator’s total stake is automatically burned by the network.

In the event of slashing, the system automatically records the incident and re-stakes the remaining MPX to a new, more reliable validator. The lost 5% is compensated from the general CrossFi Treasury pool to restore the staking balance. Rewards for the current period will be reduced due to the penalty, but in the next cycle, profitability is fully restored.

This mechanism minimizes financial losses for users and ensures uninterrupted staking operations without requiring manual intervention. Users receive notifications about slashing and re-staking to stay informed about changes.

### User Experience

The XFI-MPX protocol is designed with a focus on convenience and transparent asset management. After transferring XFI into the system, users immediately gain access to information about locked funds, delegated MPX, and expected earnings considering automatic reinvestment. The interface provides real-time data on exchange rates, staking status, and balances.

The main staking page displays XFI and MPX balances, current XFI/USDT and MPX/USDT exchange rates, and the status of operations. Users can easily track their progress and plan further actions. All transactions are executed through verified crypto wallets such as MetaMask, ensuring a high level of security.

If a user wishes to end staking, they can press the "Unstake" button, after which the system will return their XFI along with the accrued earnings. The unstaking process takes minimal time, and the user immediately sees the available XFI balance, including profits.

### System Architecture

The protocol’s operation is based on the close interaction of smart contracts and the backend system. Smart contracts handle XFI locking, MPX issuance, and staking record management. They also process fund withdrawal operations, including XFI returns and MPX redistribution into the general pool.

The backend system ensures real-time exchange rate retrieval, validator selection based on predefined criteria, and automatic network status updates. Validators are chosen based on their reliability, performance, and economic efficiency. For example, the system considers a validator’s uptime, the size of their own stake, commission fees, and workload distribution. This minimizes centralization risks and ensures fair stake distribution among network participants.

The system also monitors validator behavior to prevent slashing risks and verifies exchange rates to ensure transaction accuracy. All these processes occur automatically, allowing the system to operate quickly, stably, and efficiently allocate resources to achieve maximum profitability.
