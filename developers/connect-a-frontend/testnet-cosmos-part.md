# Testnet Cosmos Part

### CosmJS

In order to use the cosmJS library function in the CrossFi network, you need to patch the cosmJS library as in the example: [https://github.com/crossfichain/js-tx-example](https://github.com/crossfichain/js-tx-example)

{% code overflow="wrap" %}
```javascript
const { stringToPath } = require('@cosmjs/crypto');
const { DirectSecp256k1HdWallet } = require('@cosmjs/proto-signing');
const { SigningStargateClient, GasPrice } = require('@cosmjs/stargate');
const bech32Converter = require('bech32-converting');

require('dotenv').config();

const COSMOS_RPC_URL = 'https://tendermint-rpc.testnet.ms/';
const MNEMONIC = process.env.MNEMONIC || '';
const GAS_PRICE = {
  mpx: GasPrice.fromString('10000000000000mpx'),
  xfi: GasPrice.fromString('100000000000xfi'),
};
const PREFIX = 'mx';
const HD_PATHS = [stringToPath("m/44'/118'/0'/0/0"), stringToPath("m/44'/60'/0'/0/0")];

async function main() {
  const clientOptions = {
    gasPrice: GAS_PRICE.xfi,
    broadcastTimeoutMs: 5000,
    broadcastPollIntervalMs: 1000,
  };
  const signer = await DirectSecp256k1HdWallet.fromMnemonic(MNEMONIC, { prefix: PREFIX, hdPaths: HD_PATHS });
  const signingClient = await SigningStargateClient.connectWithSigner(COSMOS_RPC_URL, signer, clientOptions);
  const [oldAddressAccountData, newAddressAccountData] = await signer.getAccounts();
  const chainId = await signingClient.getChainId();

  console.log('chain id:', chainId);
  console.log('old address:', oldAddressAccountData.address); // previous mainnet network
  console.log('new address:', newAddressAccountData.address); // current mainnet network
  console.log('new evm address:', bech32Converter(PREFIX).toHex(newAddressAccountData.address));
}

main();
```
{% endcode %}

