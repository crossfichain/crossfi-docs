# XFI Bridge

## XFI Bridge Overview

XFI Bridge is the most important infrastructural component of the CrossFi ecosystem, designed for the seamless transfer of digital assets between Ethereum Virtual Machine (EVM)-compatible networks and the CrossFi Chain blockchain built on Cosmos technology. The primary function of the bridge is to provide secure, fast, and transparent token transfers (e.g., XFI, XUSD, USDT) between CrossFi Chain and popular EVM networks such as Ethereum, BNB Chain, Basechain, and Polygon.

Using the decentralized deBridge protocol, XFI Bridge eliminates the need for centralized intermediaries while relying on decentralized liquidity pools that ensure the system functions correctly by maintaining sufficient liquidity. This increases the security and control users have over their funds and significantly simplifies the exchange and movement of assets between blockchains. As a result, users can effectively integrate their tokens into a variety of DeFi products, such as staking, trading, liquidity management, and also use them in CrossFi applications (e.g., xAPP or CrossFi APP).

### Purpose and Benefits

The primary goal of XFI Bridge is the free and secure transfer of value between different blockchains, uniting liquidity from external EVM ecosystems and the CrossFi Chain network. This allows asset owners to use their funds with maximum flexibility, maintaining access to all opportunities both within the CrossFi ecosystem and beyond its boundaries.

**Key advantages of XFI Bridge include:**

* **Security and decentralization:** Asset transfers occur through a network of independent deBridge validators, ensuring a high degree of transaction protection and the absence of a single point of failure.
* **High transaction speed:** Thanks to the optimized infrastructure and fast block finality on CrossFi Chain, asset transfers take minimal time without prolonged waiting periods.
* **A simple and intuitive interface:** Users can easily select the desired assets, destination networks, and execute transactions in a few clicks without requiring technical expertise.
* **Absence of intermediaries:** There is no need to use centralized exchanges for transferring assets between different networks or blockchains, which reduces risks and costs for users.

### Role of XFI Bridge in the CrossFi Ecosystem

XFI Bridge plays a central role by uniting the two main parts of CrossFi Chain: the Cosmos-based module and the EVM-based module. This interaction enables the implementation of a unified platform where traditional finance and DeFi products operate within a single space. For example, XFI—the native token of the ecosystem—can freely move between CrossFi Chain and other blockchains, participating in smart contracts on external networks or being traded on external platforms.

The bridge is also a key tool for attracting liquidity to the network. Users can easily transfer stablecoins (USDT, USDC, and others) into CrossFi Chain, increasing the accessibility and functionality of CrossFi’s DeFi products. As a result, the ecosystem becomes more attractive to a wide range of participants: users, investors, and developers seeking high interoperability and flexibility when working with digital assets.

### Technological Architecture

#### Cosmos SDK and Tendermint

CrossFi Chain is built on Cosmos SDK and the Tendermint Core consensus, which ensures high speed (\~5 seconds block finality, with a prospect of up to 1 second), security due to Byzantine fault tolerance (BFT), and network scalability. This technological foundation guarantees the stable operation of XFI Bridge: all transactions are confirmed quickly and finally.

#### Ethermint and Evmos

CrossFi Chain utilizes Ethermint and Evmos for full compatibility with Ethereum. The integrated Ethereum Virtual Machine allows for the execution of EVM smart contracts and the use of ERC-20 tokens (e.g., eMPX and XFI), enabling integration with MetaMask wallets and Ethereum applications. This architecture combines Ethereum’s flexibility with Cosmos’ security, simplifying the use of XFI Bridge.

#### Role of deBridge

XFI Bridge employs the deBridge protocol—a decentralized infrastructure for transferring tokens and data between blockchains. deBridge operates as a universal layer of cross-chain communication, ensuring secure asset exchange between CrossFi Chain and other EVM-compatible networks (Ethereum, BNB Chain, Polygon, etc.).

Asset transfer is implemented using special DeBridgeGate smart contracts deployed on each connected network, including CrossFi Chain (based on Ethermint). A user initiating a transfer interacts directly with the DeBridgeGate contract in the source network. The transaction is then validated by the decentralized network of deBridge validators, where a minimum of 2/3 validator signatures (BFT threshold) is required for successful confirmation.

Security is ensured by the delegated staking mechanism and slashing penalties imposed on validators for any violations or fraudulent actions. Thus, the bridge is entirely decentralized and does not depend on a single central authority.

**Key advantages of deBridge integration include:**

* **Security:** The protocol has undergone more than 25 audits (Halborn, Zokyo, Neodyme, and others) and features an active bug bounty program (up to $200K).
* **Absence of centralized liquidity pools:** Each transfer is processed individually (locking/unlocking of assets or exchange via external liquidity providers).
* **High performance:** Transactions are processed quickly (within minutes), even if individual networks are temporarily unavailable, thanks to off-chain validation and BFT consensus.

### Token Exchange Functionality

XFI Bridge supports the transfer of digital assets (XFI, MPX, XUSD, as well as external tokens like USDT or ETH) between EVM-compatible networks and CrossFi Chain using a lock-mint and burn-unlock model. This mechanism is applied both for exchanges between the internal modules of CrossFi (i.e., between the Cosmos and EVM parts) and for cross-chain transfers with external blockchains. The process involves several stages:

1. **Asset Locking on the Source Chain:** The user sends tokens to the bridge smart contract (DeBridgeGate) on the source network, where the tokens are locked and become unavailable until the transfer is completed.
2. **Confirmation and Message Transmission:** deBridge validators monitor the locking event and, after finalization, sign the transaction. Once a minimum of 2/3 of validator signatures is collected, a verified message is generated for the target network.
3. **Wrapped Token Issuance on the Target Chain:** Based on the verified message, the bridge smart contract on the target network mints wrapped tokens (on a 1:1 basis), which can then be used in the destination network’s applications.
4. **Reverse Exchange (Burn-Unlock):** To return tokens to the source network, the user sends the wrapped tokens back to the bridge smart contract, where they are burned. After validator confirmation, the original tokens are unlocked on the source chain.

### Fees and Execution Time

A small fee is charged for each cross-chain transfer in the form of a percentage of the amount and a fixed payment in the network's native token (e.g., XFI for CrossFi Chain). The average full cycle time for the exchange is a few minutes, depending on the transaction finality speed on the participating blockchains.
