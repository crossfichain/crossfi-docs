# Testnet EVM part

### EthersJS

[Ethers.js ](https://docs.ethers.org/v6/)is a compact Javascript library used for interacting with the Ethereum blockchain and other EVM compatible chains. &#x20;

```javascript
const { ethers } = require("ethers");

// URL of the RPC for the CrossFi Testnet 
const providerUrl = "https://rpc.testnet.ms/";

// Creating a provider to interact with the blockchain

const provider = new ethers.JsonRpcProvider(providerUrl);
async function main() {
	// Getting the current block number as a test of the connection
	const blockNumber = await provider.getBlockNumber();
	console.log(`Current block number: ${blockNumber}`);
}

main().catch((error) => {
	console.error("Error connecting to the blockchain:", error);
});

```



### Viem&#x20;

[Viem](https://viem.sh/docs/getting-started) is a TypeScript library that offers type-safe modules for interacting with the Ethereum and other EVM compatible chains.&#x20;



```javascript
import { defineChain, createPublicClient, http } from 'viem';

export const crossfi = defineChain({
  id: 4157,
  name: 'CrossFi Testnet',
  nativeCurrency: {
    decimals: 18,
    name: 'XFI',
    symbol: 'XFI',
  },
  rpcUrls: {
    default: {
      http: ['https://rpc.testnet.ms/'],
    },
  },
  blockExplorers: {
    default: { name: 'Explorer', url: 'https://test.xfiscan.com/' },
  },
});

const client = createPublicClient({
  chain: crossfi,
  transport: http(),
});

const blockNumber = await client.getBlockNumber();

export default `Block number: ${blockNumber}`;

```



### ThirdWeb&#x20;

[Thirdweb](https://portal.thirdweb.com/) is a developer platform that offers a suite of tools including wallets, contract deployment and   libraries to interact with any EVM chain.&#x20;

Here is a code example using their [TypeScript SDK](https://portal.thirdweb.com/typescript/v4) to read the balance of a wallet address:&#x20;

```typescript
import { CrossfiTestnet } from "@thirdweb-dev/chains";
import { ThirdwebSDK } from "@thirdweb-dev/sdk";

const sdk = new ThirdwebSDK(CrossfiTestnet, {
  clientId: "YOUR_clientId",
});

const getWalletBalance = async () => {
    const walletBalance = await sdk.getBalance("YOUR_WALLET_ADDRESS");
    console.log(walletBalance);
};

getWalletBalance();
```
