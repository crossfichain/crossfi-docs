# CrossFi Chain Overview

## **Introduction**

CrossFi Chain is a next-generation Layer 1 blockchain built with a modular architecture, seamlessly integrating **Cosmos** and **Ethereum Virtual Machine (EVM)**. This synergy enables high performance, security, scalability, and deep interoperability, allowing users to leverage the benefits of both ecosystems without compromise.

CrossFi Chain serves as a robust foundation for **decentralized finance (DeFi), Web3 applications, integrations with traditional financial systems (TradFi), and innovative services**. Its primary goal is to provide developers, users, and institutional players with a **flexible infrastructure** that can adapt to the rapidly evolving market landscape.

## [**Architecture** ](architecture/)**and Technology**

At the core of **CrossFi Chain** lies the **Cosmos SDK**, which provides a developer-friendly framework for building blockchain applications using modular components. The Cosmos technology stack ensures consensus, coin issuance, transaction validation, and block formation, all powered by **Tendermint Core**—a robust consensus mechanism based on **Delegated Proof-of-Stake (DPoS) and Byzantine Fault Tolerance (BFT)**.

Simultaneously, the **EVM layer**, built on **Ethermint and Evmos**, offers full compatibility with **Ethereum smart contracts and dApps**. This hybrid approach ensures that developers can seamlessly migrate existing Ethereum-based solutions or build new ones using familiar tools such as **Solidity, Hardhat, and Truffle**, while benefiting from Cosmos’ scalability and high-speed execution.

## **Key Features**

* **Consensus Protocol:** DPoS + BFT, ensuring resilience against attacks and effective role distribution among validators and delegators.
* **High Performance:**
  * **Block time:** \~5 seconds (potentially reducible to 1 second in the future).
  * **Throughput:** Up to 10,000 transactions per second, supporting high-load applications like trading platforms or mass payment services.
  * **Operations per transaction:** Up to 100, increasing the functional density of data within a single block.
  * **Transaction confirmation:** 1 block, ensuring rapid finalization of operations.
* **Low Fees:** The average fee of approximately 2% enhances economic efficiency and makes the network attractive for mass adoption.
* **EVM Compatibility:** Full support for the Ethereum toolset and smart contracts simplifies adaptation and migration of projects, making CrossFi Chain open and developer-friendly.

***

## [**Cosmos SDK and Tendermint Core**](architecture/)

CrossFi Chain fully supports Inter-Blockchain Communication (IBC), which has become the standard for exchanging data and assets between independent Cosmos networks. Thanks to IBC, applications can leverage multiple chains simultaneously—for example, storing data on one network while executing financial transactions on another. This simplifies the development of complex decentralized systems and increases asset liquidity. Interoperability fosters the formation of a global network of interconnected blockchains, paving the way for cross-chain DEXs, multi-chain staking, and expanded DeFi services.

## Interoperability and IBC

CrossFi Chain fully supports Inter-Blockchain Communication (IBC), which has become the standard for exchanging data and assets between independent Cosmos networks. Thanks to IBC, applications can leverage multiple chains simultaneously—for example, storing data on one network while executing financial transactions on another. This simplifies the development of complex decentralized systems and increases asset liquidity. Interoperability fosters the formation of a global network of interconnected blockchains, paving the way for cross-chain DEXs, multi-chain staking, and expanded DeFi services.

## [**Token Economy**](../economy-overview/)

Key participants in the CrossFi Chain ecosystem include **validators, delegators, developers, users, and token holders**.

#### **Core Tokens:**

* [**MPX** ](../economy-overview/mpx-coin/)_(Cosmos Layer Token)_:
  * Used for [**staking**](../ecosystem/xfi-console/native-staking-protocol.md)**,** [**governance**](../ecosystem/xfi-console/governance-dao.md)**, and transaction fees**.
  * **Unlimited supply** to support network functionality and validator incentives.
* [**XFI**](../economy-overview/xfi-coin.md) _(EVM Layer Utility Token)_:
  * Grants access to **dApps, DeFi services, and payment solutions**.
  * **Capped supply**: **378,400,000 XFI** over 20 years, divided into five phases, ensuring inflation control and long-term value stability.

The existence of **eMPX**—the EVM version of MPX—simplifies interactions between Cosmos and Ethereum ecosystems and facilitates token usage in various DeFi protocols.

## **High Speed and Scalability**

CrossFi Chain is designed for mass adoption: its infrastructure enables the processing of vast transaction volumes with minimal latency and low fees. This is particularly important for applications targeting a broad audience, from payment services to high-liquidity DEXs. Scalability is achieved through a well-structured modular architecture, allowing network improvements without downtime or complex forks.

### **Low Fees**

Affordable transaction fees make CrossFi Chain attractive for developers (lower deployment costs) and users (microtransactions and daily operations without significant expenses). This encourages network growth and enhances its appeal for startups and businesses.

## [**Developer Tools**](broken-reference)

Developers can utilize:

* **Cosmos gRPC and REST:** For interacting with Cosmos-level functionality.
* **Ethereum JSON-RPC and WebSocket:** Standard tools for Ethereum developers.
* **Tendermint RPC and WebSocket:** For low-level access to network state and block data.

Comprehensive documentation, starter project templates, integration with popular frameworks, and public testnets simplify rapid adaptation and prototyping. An active developer community, regular AMA sessions, hackathons, and grant programs support innovation and new project development.

## **Integration with Traditional Finance and Oracles**

CrossFi Chain aims to bridge decentralized and traditional financial systems. Support for **SWIFT, IBAN, and payment systems (VISA, MIR)** enables instant crypto-to-fiat conversion and international transactions. Integration with **oracles (DIA, Covalent)** provides access to reliable external data (exchange rates, stock prices, weather conditions), allowing smart contracts to respond to real-world events. **Infrastructure providers like POKT and Blast** ensure stable and fast RPC access from anywhere in the world.

## **Security**

The use of **DPoS and BFT** ensures that the network is resilient to malicious activities and failures. Combined with regular smart contract audits, modern encryption techniques, and continuous network monitoring, CrossFi Chain minimizes risks of theft and attacks. Economic incentives (such as **slashing for malicious validators**) help maintain discipline among network participants.

## **Grant Program and Incentives**

CrossFi offers grants for promising projects aimed at improving the ecosystem, ranging from user interfaces to infrastructure solutions and educational initiatives. Grant recipients receive not only financial support but also expert consultations, marketing assistance, partner connections, and access to community resources. Rewards in **XFI tokens** and staking options promote long-term collaboration and ecosystem growth.

## **User Benefits**

End-users benefit from fast and low-cost transactions, a wide range of dApps (DEXs, lending protocols, stablecoins, NFT marketplaces), staking opportunities, and governance participation. **Integration with TradFi** makes crypto finance more accessible, while non-custodial solutions enhance user control over their assets.

CrossFi Chain is at the core of a rapidly evolving ecosystem designed to provide comprehensive infrastructure for users, developers, and investors, uniting multiple services and applications.

## CrossFi Ecosystem

#### **CrossFi App**

A unified Web3 platform that integrates everyday finance with digital assets:

* Manage VISA and MIR payment cards.
* Conduct crypto transactions and manage CrossFi Chain tokens.
* Access financial education resources and basic portfolio tools.

#### [**CrossFi xAPP**](../ecosystem/xapp/)

A universal DeFi hub offering access to a full suite of decentralized tools:

* Token swaps, staking, liquidity provisioning, synthetic asset issuance.
* Built-in cross-chain capabilities via secure bridge infrastructure.
* Anonymous payment support and EVM wallet compatibility.
* Incentive systems that reward active ecosystem participants.

#### **XAssets**

A protocol for the creation and trading of synthetic assets:

* Allows users to gain on-chain exposure to real-world assets such as commodities, indices, and currencies.
* Enables decentralized trading without needing to hold the underlying asset.

#### **XStake**

An omnichain yield optimization protocol:

* Automatically locates and allocates assets to the most profitable staking opportunities across multiple chains.
* Improves capital efficiency and reduces manual strategy execution.

#### [**XFI Bridge**](../ecosystem/xfi-bridge.md)

A secure and scalable infrastructure component enabling token mobility between CrossFi (Cosmos-based) and EVM-compatible blockchains:

* Supports bidirectional transfers of XFI with parity via mint/burn mechanisms.
* Deep integration with xAPP and the staking ecosystem.
* Powered by deBridge for fast, transparent, and low-fee cross-chain routing.

#### [**XFI Scan**](../ecosystem/xfi-scan.md)

A powerful blockchain explorer for the CrossFi Chain:

* Provides real-time access to transaction data, block history, validator statistics, and address balances.
* Enables users and developers to audit network activity, verify transaction status, and monitor staking rewards.
* Serves as an essential transparency layer for the entire CrossFi ecosystem.

For additional details on each component and its functionality, visit the [**Ecosystem** ](../ecosystem/)page.

{% content-ref url="../ecosystem/" %}
[ecosystem](../ecosystem/)
{% endcontent-ref %}

