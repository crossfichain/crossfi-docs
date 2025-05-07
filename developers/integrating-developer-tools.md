# Integrating Developer Tools

To allow options when developing on the CrossFi chain, we have integrated with several partners. This list will continue to grow:&#x20;

## Oracles

### [**DIA Oracles**](https://www.diadata.org/)

DIA is a cross-chain data and oracle platform, specializing in the sourcing and delivery of customizable data feeds both on-chain and off-chain.

***

## RPCs

### [**Blast**](https://blastapi.io/)&#x20;

#### Blast provides fast and reliable decentralized blockchain APIs by partnering with Node Providers, to deliver some of the best infrastructure services in the Web3 space.

To get started with Blast, you will need to create a Project ID and select the CrossFi Testnet under the Core API Category:&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2024-03-22 at 11.57.41.png" alt=""><figcaption></figcaption></figure>

After setting up your project, you can use your project ID to create a RPC request similiar to the one below.  A list of the available functions can be found[ on this page](https://docs.blastapi.io/blast-documentation/apis-documentation/core-api/crossfi).&#x20;

```bash

curl -X POST https://crossfi-testnet.blastapi.io/<project-id> -H 'Content-Type: application/json' -d '{"jsonrpc":"2.0","id":0,"method":"eth_blockNumber"}'
```

### [**POKT**](https://www.pokt.network/)&#x20;

&#x20;Web3 Infrastructure with high uptime, cost-effective access, and low latency.

***

### APIs

### [**Covalent**](https://www.covalenthq.com/)&#x20;

Covalent is a platform for retrieving data about different blockchain networks. Through an API request, you can find information about wallet, transaction and network activity.&#x20;

To get started using Covalent with CrossFi,  you need to create an account on the Covalent site. After that you can. make the available API calls to get data about the CrossFi chain.&#x20;

Here is a code snippet to get the token balance for a wallet address:&#x20;

```typescript
import { CovalentClient } from "@covalenthq/client-sdk";

const ApiServices = async () => {
    const client = new CovalentClient("YOUR_API_KEY");
    const resp = await client.BalanceService.getTokenBalancesForWalletAddress("crossfi-evm-testnet", "YOUR_WALLET_ADDRESS");
    console.log(resp.data);
}

ApiServices();

```

***

## Indexers

### [**Subsquid**](https://subsquid.io/)&#x20;

Subsquid Network is a decentralized query engine optimized for batch extraction of large volumes of data. It currently serves historial on-chain data, including event logs, transaction receipts, traces and per-transaction state diffs.

***

## Dev tools

### [**Thirdweb**](https://thirdweb.com/)&#x20;

The all-in-one platform for developers to easily bring their games onto web3. To use Thirdweb with CrossFi, you can use their [TypeScript SDKs. ](https://portal.thirdweb.com/typescript-sdks)Here is an example of how to get the token balance for a wallet address:&#x20;

```typescript
import { CrossfiTestnet } from "@thirdweb-dev/chains";
import { ThirdwebSDK } from "@thirdweb-dev/sdk";
'
const sdk = new ThirdwebSDK(CrossfiTestnet, {
  secretKey: "YOUR_SECRET_KEY",
});

const getWalletBalance = async () => {
    const walletBalance = await sdk.getBalance("YOUR_WALLET_ADDRESS");
    console.log(walletBalance);
};

getWalletBalance();
```

