# API and Available Endpoints

These following API's are recommended for development purposes. For maximun control and reliability it's recommended to run your own node.

## Networks

Quickly connect your app or client to CrossFi mainnet and public testnets. Head over to Networks to find a list of publicly available endpoints that you can use to connect to the CrossFi

## Clients

The CrossFi Network supports different clients in order to support Cosmos and Ethereum transactions and queries. You can use Swagger as a REST interface for state queries and transactions:

<table data-full-width="false"><thead><tr><th></th><th>Description</th><th>Default Port</th><th>Url</th></tr></thead><tbody><tr><td><strong>Cosmos gRPC</strong></td><td>Query or send CrossFi transactions using gRPC</td><td><code>9091</code></td><td><a href="https://cosmos-rpc.mainnet.ms/">Mainnet</a> <a href="https://cosmos-rpc.testnet.ms/">Testnet</a></td></tr><tr><td><strong>Cosmos REST (gRPC-Gateway)</strong></td><td>Query or send CrossFi transactions using an HTTP RESTful API</td><td><code>1317</code></td><td><a href="https://cosmos-api.mainnet.ms/">Mainnet</a> <a href="https://cosmos-api.testnet.ms/">Testnet</a></td></tr><tr><td><strong>Ethereum JSON-RPC</strong></td><td>Query Ethereum-formatted transactions and blocks or send Ethereum txs using JSON-RPC</td><td><code>8545</code></td><td><a href="https://rpc.mainnet.ms/">Mainnet</a> <a href="https://rpc.testnet.ms/">Testnet</a></td></tr><tr><td><strong>Ethereum Websocket</strong></td><td>Subscribe to Ethereum logs and events emitted in smart contracts.</td><td><code>8586</code></td><td></td></tr><tr><td><strong>Tendermint RPC</strong></td><td>Query transactions, blocks, consensus state, broadcast transactions, etc.</td><td><code>26657</code></td><td><a href="https://tendermint-rpc.mainnet.ms/">Mainnet</a> <a href="https://tendermint-rpc.testnet.ms/">Testnet</a></td></tr><tr><td><strong>Tendermint</strong> <a href="broken-reference"><strong>Websocket</strong></a></td><td>Subscribe to Tendermint ABCI events</td><td><code>26657</code></td><td><a href="wss://tendermint-rpc.mainnet.ms/">Mainnet</a> <a href="wss://tendermint-rpc.testnet.ms/">Testnet</a></td></tr><tr><td><strong>Command Line Interface (CLI)</strong></td><td>Query or send CrossFi transactions using your Terminal or Console.</td><td>N/A</td><td></td></tr></tbody></table>
