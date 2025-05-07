# Mainnet EVM Part

### EthersJS

[Ethers.js ](https://docs.ethers.org/v6/)is a compact Javascript library used for interacting with the Ethereum blockchain and other EVM compatible chains. &#x20;

```javascript
const { ethers } = require("ethers");

// URL of the RPC for the CrossFi Mainnet
const providerUrl = "https://rpc.mainnet.ms/";

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
  id: 4158,
  name: 'CrossFi Mainet',
  nativeCurrency: {
    decimals: 18,
    name: 'XFI',
    symbol: 'XFI',
  },
  rpcUrls: {
    default: {
      http: ['https://rpc.mainnet.ms/'],
    },
  },
  blockExplorers: {
    default: { name: 'Explorer', url: 'https://xfiscan.com/' },
  },
});

const client = createPublicClient({
  chain: crossfi,
  transport: http(),
});

const blockNumber = await client.getBlockNumber();

export default `Block number: ${blockNumber}`;

```
