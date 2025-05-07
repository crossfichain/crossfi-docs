# Deploying Smart Contracts

The CrossFi Chain supports smart contracts written in Solidity. You can use popular tools like Hardhat and Foundry to deploy your smart contracts

This page provides guides for each of these tools:&#x20;

### Hardhat&#x20;

[Hardhat](https://hardhat.org/) - JavaScript/TypeScript-based smart contract development and testing framework

* All basic functionality of framework is working on CrossFi chain

For an exhaustive guide on how to make a smart contract on a CrossFi network, we advise you to first go through the official beginner's [guide by hardhat](https://hardhat.org/tutorial)

After tutorial completion add CrossFi chain to you hardhat.config.js and you'll be fully set up to start your building journey on CrossFi chain.

### Foundry&#x20;

[Foundry](https://github.com/foundry-rs/foundry) - high-performance smart contract development framework written on Rust All basic functionality of framework is working on CrossFi chain

* Can be used in pair with Hardhat
* Can have troubles with smart contracts verification

## Deploy with Ethereum JSON-RPC

CrossFi is fully compatible with the [Ethereum JSON-RPC](https://ethereum.org/en/developers/docs/apis/json-rpc) APIs, allowing you to deploy and interact with smart contracts on CrossFi and connect with existing Ethereum-compatible web3 tooling. This gives you direct access to reading Ethereum-formatted transactions or sending them to the network which otherwise wouldn't be possible on a Cosmos chain, such as CrossFi.

You can connect to the CrossFi Testnet to deploy and test your smart contracts before moving to Mainnet.

### Block Explorers

You can use block explorers to view and debug interactions with your smart contracts deployed on CrossFi. Block explorers index blocks and their transactions so that you can search for real-time and historical information about the blockchain, including data related to blocks, transactions, addresses, and more.

### Contract Verification

Contracts verification is not publicly available right now due to the Explorer API being under active development.
