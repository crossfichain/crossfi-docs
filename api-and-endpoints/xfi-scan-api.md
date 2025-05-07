---
description: >-
  These following API's are recommended for development on mainnet and testnet.
  When receive example pay attention to the domain:
---

# XFI Scan API

* [**xfiscan**](https://xfiscan.com/dashboard) **— for mainnet network**
* [t**est.xfiscan**](https://test.xfiscan.com/dashboard) **— for testnet network**

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name   | Type   | Description      |
| ------ | ------ | ---------------- |
| `name` | string | Name of the user |
| `age`  | number | Age of the user  |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "id": 1,
  "name": "John",
  "age": 30
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}

### txs - Queries for transactions

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/txs](https://test.xfiscan.com/api/1.0/swagger#/txs/TransactionController_find)

Retrieving a list of transactions.

**Parameters**

<table data-full-width="false"><thead><tr><th>Parameter</th><th>Type</th><th>Description</th></tr></thead><tbody><tr><td>from_height</td><td>string</td><td>Block number from.</td></tr><tr><td>to_height</td><td>string</td><td>Block number to.</td></tr><tr><td>address</td><td>string</td><td>Account Address. </td></tr><tr><td>addresses</td><td>array [string]</td><td>Account addresses array.</td></tr><tr><td>txhash</td><td>string</td><td>Transaction hash.</td></tr><tr><td>txhashes</td><td>array [string]</td><td>Transaction hash array.</td></tr><tr><td>height</td><td>string</td><td>Block Height.</td></tr><tr><td>existsEVM</td><td>boolean</td><td>True - only EVM part transactions, false - only Cosmos part transactions.</td></tr><tr><td>messageType</td><td>string</td><td>Transaction message type.</td></tr><tr><td>page</td><td>number</td><td>Page Number.</td></tr><tr><td>limit</td><td>number</td><td>The number of entities to give away</td></tr><tr><td>sort</td><td>string</td><td>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field<br>Example: '-height' is descending, 'height' is ascending.</td></tr></tbody></table>

<details>

<summary>Sample Response</summary>

```bash
{
  "docs": [
    {
      "txhash": "8a31d98d252be6dbec82fabc9b57a592e66e15bb70ea856bcf6f30c08e349e9a",
      "addresses": [
        "0x9449078b371ff30a90ec36fe6191f164cd527d64",
        "mx1j3ys0zehrles4y8vxmlxry03vnx4yltyg2alsv"
      ],
      "auth_info": {
        "signer_infos": [],
        "fee": {
          "amount": [
            {
              "denom": "xfi",
              "amount": "252031500000000000"
            }
          ],
          "gas_limit": "21000",
          "payer": "",
          "granter": ""
        }
      },
      "body": {
        "messages": [
          {
            "data": {
              "chain_id": "4156",
              "nonce": "10",
              "gas_tip_cap": "1500000000",
              "gas_fee_cap": "12001500000000",
              "gas": "21000",
              "to": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
              "value": "1000000000000000000",
              "data": null,
              "accesses": [],
              "v": "0",
              "r": "0x4b5b357aace26ec5f9ec1d402dcb9d77fe3adeba58535624c3cecee03c96c425",
              "s": "0x05fde619bcb77662af9f1248c4435f6e4386c3bf9c60c1efae43429d61b9a96e",
              "@type": "/ethermint.evm.v1.DynamicFeeTx",
              "from": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
              "base_fee_per_gas": "10000000000000"
            },
            "size": 0,
            "hash": "0xd18df3e4684b3f4b0904b1c05391602faf14aa68e318ac1509c5d1d25ad05b7b",
            "from": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
            "@type": "/ethermint.evm.v1.MsgEthereumTx"
          }
        ],
        "memo": "",
        "timeout_height": "0",
        "extension_options": [
          {
            "@type": "/ethermint.evm.v1.ExtensionOptionsEthereumTx"
          }
        ],
        "non_critical_extension_options": []
      },
      "code": 0,
      "codespace": "",
      "evm_txhashes": [
        "0xd18df3e4684b3f4b0904b1c05391602faf14aa68e318ac1509c5d1d25ad05b7b"
      ],
      "gas_used": "21000",
      "gas_wanted": "21000",
      "height": 30,
      "info": "",
      "isEVM": true,
      "logs": [
        {
          "msg_index": 0,
          "events": [
            {
              "type": "ethereum_tx",
              "attributes": [
                {
                  "key": "amount",
                  "value": "1000000000000000000"
                },
                {
                  "key": "ethereumTxHash",
                  "value": "0xd18df3e4684b3f4b0904b1c05391602faf14aa68e318ac1509c5d1d25ad05b7b"
                },
                {
                  "key": "txIndex",
                  "value": "0"
                },
                {
                  "key": "txGasUsed",
                  "value": "21000"
                },
                {
                  "key": "txHash",
                  "value": "8A31D98D252BE6DBEC82FABC9B57A592E66E15BB70EA856BCF6F30C08E349E9A"
                },
                {
                  "key": "recipient",
                  "value": "0x9449078b371FF30A90EC36Fe6191F164Cd527D64"
                }
              ]
            },
            {
              "type": "message",
              "attributes": [
                {
                  "key": "action",
                  "value": "/ethermint.evm.v1.MsgEthereumTx"
                },
                {
                  "key": "module",
                  "value": "evm"
                },
                {
                  "key": "sender",
                  "value": "0x9449078b371FF30A90EC36Fe6191F164Cd527D64"
                },
                {
                  "key": "txType",
                  "value": "2"
                }
              ]
            },
            {
              "type": "tx_log",
              "attributes": null
            }
          ]
        }
      ],
      "signatures": [],
      "timestamp": "2023-08-10T06:05:35.448Z",
      "xds": []
    }
  ],
  "hasNext": true,
  "limit": 1,
  "page": 1
}
```

</details>

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/txs/{hash}](https://test.xfiscan.com/api/1.0/swagger#/txs/TransactionController_findByHash)

Getting the transaction hash.

#### Parameters

| Parameter | Type   | Description                        |
| --------- | ------ | ---------------------------------- |
| hash      | string | Transaction hash. Mandatory field. |

<details>

<summary>Sample Response</summary>

```bash
{
  "txhash": "8a31d98d252be6dbec82fabc9b57a592e66e15bb70ea856bcf6f30c08e349e9a",
  "addresses": [
    "0x9449078b371ff30a90ec36fe6191f164cd527d64",
    "mx1j3ys0zehrles4y8vxmlxry03vnx4yltyg2alsv"
  ],
  "auth_info": {
    "signer_infos": [],
    "fee": {
      "amount": [
        {
          "denom": "xfi",
          "amount": "252031500000000000"
        }
      ],
      "gas_limit": "21000",
      "payer": "",
      "granter": ""
    }
  },
  "body": {
    "messages": [
      {
        "data": {
          "chain_id": "4156",
          "nonce": "10",
          "gas_tip_cap": "1500000000",
          "gas_fee_cap": "12001500000000",
          "gas": "21000",
          "to": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
          "value": "1000000000000000000",
          "data": null,
          "accesses": [],
          "v": "0",
          "r": "0x4b5b357aace26ec5f9ec1d402dcb9d77fe3adeba58535624c3cecee03c96c425",
          "s": "0x05fde619bcb77662af9f1248c4435f6e4386c3bf9c60c1efae43429d61b9a96e",
          "@type": "/ethermint.evm.v1.DynamicFeeTx",
          "from": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
          "base_fee_per_gas": "10000000000000"
        },
        "size": 0,
        "hash": "0xd18df3e4684b3f4b0904b1c05391602faf14aa68e318ac1509c5d1d25ad05b7b",
        "from": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
        "@type": "/ethermint.evm.v1.MsgEthereumTx"
      }
    ],
    "memo": "",
    "timeout_height": "0",
    "extension_options": [
      {
        "@type": "/ethermint.evm.v1.ExtensionOptionsEthereumTx"
      }
    ],
    "non_critical_extension_options": []
  },
  "code": 0,
  "codespace": "",
  "evm_txhashes": [
    "0xd18df3e4684b3f4b0904b1c05391602faf14aa68e318ac1509c5d1d25ad05b7b"
  ],
  "gas_used": "21000",
  "gas_wanted": "21000",
  "height": 30,
  "info": "",
  "isEVM": true,
  "logs": [
    {
      "msg_index": 0,
      "events": [
        {
          "type": "ethereum_tx",
          "attributes": [
            {
              "key": "amount",
              "value": "1000000000000000000"
            },
            {
              "key": "ethereumTxHash",
              "value": "0xd18df3e4684b3f4b0904b1c05391602faf14aa68e318ac1509c5d1d25ad05b7b"
            },
            {
              "key": "txIndex",
              "value": "0"
            },
            {
              "key": "txGasUsed",
              "value": "21000"
            },
            {
              "key": "txHash",
              "value": "8A31D98D252BE6DBEC82FABC9B57A592E66E15BB70EA856BCF6F30C08E349E9A"
            },
            {
              "key": "recipient",
              "value": "0x9449078b371FF30A90EC36Fe6191F164Cd527D64"
            }
          ]
        },
        {
          "type": "message",
          "attributes": [
            {
              "key": "action",
              "value": "/ethermint.evm.v1.MsgEthereumTx"
            },
            {
              "key": "module",
              "value": "evm"
            },
            {
              "key": "sender",
              "value": "0x9449078b371FF30A90EC36Fe6191F164Cd527D64"
            },
            {
              "key": "txType",
              "value": "2"
            }
          ]
        },
        {
          "type": "tx_log",
          "attributes": null
        }
      ]
    }
  ],
  "signatures": [],
  "timestamp": "2023-08-10T06:05:35.448Z",
  "xds": []
}
```

</details>

### blocks -  query for blocks

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/blocks](https://test.xfiscan.com/api/1.0/swagger#/blocks/BlockController_find)

Getting a list of blocks.

#### Parameters

| Parameter    | Type   | Description                                                                                                                                                                                        |
| ------------ | ------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| height       | string | Block Height.                                                                                                                                                                                      |
| from\_height | string | Block number from.                                                                                                                                                                                 |
| to\_height   | string | Block number to.                                                                                                                                                                                   |
| page         | number | Page Number.                                                                                                                                                                                       |
| limit        | number | The number of entities to give away.                                                                                                                                                               |
| sort         | string | The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field Example: '-height' is descending, 'height' is ascending. |

<details>

<summary>Sample Response</summary>

```bash
{
  "docs": [
    {
      "block_hash": "9ef8bf42d1916b7617955ddce3da8e31c61ca1830d27e6ef718c2ee5f22d4059",
      "app_hash": "8b651dcde4f67a1eada92185c8b5a3dd450369505f4e9d4df2059c8940c2f62c",
      "block_size": "714",
      "chain_id": "mineplex-testnet-2-5",
      "consensus_hash": "16dbfd0aaa36e214d4e55a6eaadf68e9802dd4845dbd49eb58daa89f885d1fc0",
      "data_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
      "evidence_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
      "evm": {
        "baseFeePerGas": "500000000000",
        "difficulty": "0",
        "extraData": "0x",
        "gasLimit": "20000000",
        "gasUsed": "0",
        "hash": "0x9ef8bf42d1916b7617955ddce3da8e31c61ca1830d27e6ef718c2ee5f22d4059",
        "miner": "0x9b98f8601013ee11b88dd202c954965c59e12e65",
        "nonce": "0x0000000000000000",
        "number": "8241762",
        "parentHash": "0x8d07a38af8b799c4f3e972fb44a1b76244e409e4811bd2a8032cced1d5549d26",
        "transactions": []
      },
      "height": 8241762,
      "last_block_hash": "8d07a38af8b799c4f3e972fb44a1b76244e409e4811bd2a8032cced1d5549d26",
      "last_commit_hash": "f5352ae0162f664b3ad7b9872174bc363fa6dc60d66a03d5454afe5dc7787662",
      "last_results_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
      "next_validators_hash": "baac843746eabd58fff69cabccee6836d3c1259cc815c08533fba272842e7cfb",
      "proposer": {
        "address": "mxvaloper1nwv0scqsz0hprwyd6gpvj4ykt3v7ztn97kjwc5",
        "description": {
          "moniker": "validator1",
          "identity": "",
          "website": "",
          "security_contact": "",
          "details": ""
        }
      },
      "sigs": [
        {
          "address": "mxvaloper1nwv0scqsz0hprwyd6gpvj4ykt3v7ztn97kjwc5",
          "signed": true
        },
        {
          "address": "mxvaloper17u9dufjvscqh56u4kd7ag236u0wu3zrw9e8fwc",
          "signed": false
        }
      ],
      "timestamp": "2025-01-31T13:20:32.370Z",
      "txs": [],
      "validators_hash": "baac843746eabd58fff69cabccee6836d3c1259cc815c08533fba272842e7cfb",
      "version": {
        "block": "11"
      }
    }
  ],
  "hasNext": true,
  "limit": 1,
  "page": 1
}
```

</details>

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/blocks/latest](https://test.xfiscan.com/api/1.0/swagger#/blocks/BlockController_findLatest)

Receiving the current confirmed block.

#### Parameters&#x20;

None

<details>

<summary>Sample Response</summary>

```ruby
{
  "block_hash": "5e5fe4888e1d76bdb00c5d7097ed552d39676ba2d89abb17d777ce07dcbe081e",
  "app_hash": "ad11a1a3261fafceff29decd2702065e42d6bea97d7f10d2120cbe4297b0bb92",
  "block_size": "712",
  "chain_id": "mineplex-testnet-2-5",
  "consensus_hash": "16dbfd0aaa36e214d4e55a6eaadf68e9802dd4845dbd49eb58daa89f885d1fc0",
  "data_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "evidence_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "evm": {
    "baseFeePerGas": "500000000000",
    "difficulty": "0",
    "extraData": "0x",
    "gasLimit": "20000000",
    "gasUsed": "0",
    "hash": "0x5e5fe4888e1d76bdb00c5d7097ed552d39676ba2d89abb17d777ce07dcbe081e",
    "miner": "0x9b98f8601013ee11b88dd202c954965c59e12e65",
    "nonce": "0x0000000000000000",
    "number": "8242223",
    "parentHash": "0x70af1a8df04ab529a97f47b1d892ff0a08839ecdbf77890255800f26b655b903",
    "transactions": []
  },
  "height": 8242223,
  "last_block_hash": "70af1a8df04ab529a97f47b1d892ff0a08839ecdbf77890255800f26b655b903",
  "last_commit_hash": "3884227c2ed9983c56bb2f0ce15d3228423ed363ec790c8737c6f00cc1ca415c",
  "last_results_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "next_validators_hash": "baac843746eabd58fff69cabccee6836d3c1259cc815c08533fba272842e7cfb",
  "proposer": {
    "address": "mxvaloper1nwv0scqsz0hprwyd6gpvj4ykt3v7ztn97kjwc5",
    "description": {
      "moniker": "validator1",
      "identity": "",
      "website": "",
      "security_contact": "",
      "details": ""
    }
  },
  "sigs": [
    {
      "address": "mxvaloper1nwv0scqsz0hprwyd6gpvj4ykt3v7ztn97kjwc5",
      "signed": true
    },
    {
      "address": "mxvaloper17u9dufjvscqh56u4kd7ag236u0wu3zrw9e8fwc",
      "signed": false
    }
  ],
  "timestamp": "2025-01-31T14:00:03.220Z",
  "txs": [],
  "validators_hash": "baac843746eabd58fff69cabccee6836d3c1259cc815c08533fba272842e7cfb",
  "version": {
    "block": "11"
  }
}
```

</details>

<mark style="background-color:blue;">GET</mark> [/api/1.0/blocks/{height}](https://test.xfiscan.com/api/1.0/swagger#/blocks/BlockController_findByHash)

Getting a specific block.

#### Parameters

| Parameter | Type   | Description                              |
| --------- | ------ | ---------------------------------------- |
| height    | string | <p>Block height.<br>Mandatory field.</p> |

<details>

<summary>Sample Response</summary>

```ruby
{
  "block_hash": "98e7e6441ce004842396f5869b4d34fa2a43a2fc51810e791e632ec86798ba5b",
  "app_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "block_size": "347",
  "chain_id": "mineplex-testnet-2-5",
  "consensus_hash": "16dbfd0aaa36e214d4e55a6eaadf68e9802dd4845dbd49eb58daa89f885d1fc0",
  "data_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "evidence_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "evm": {
    "baseFeePerGas": "10000000000000",
    "difficulty": "0",
    "extraData": "0x",
    "gasLimit": "20000000",
    "gasUsed": "0",
    "hash": "0x98e7e6441ce004842396f5869b4d34fa2a43a2fc51810e791e632ec86798ba5b",
    "miner": "0xb6aba457a6bc2e53119fb442903fa018e0496800",
    "nonce": "0x0000000000000000",
    "number": "1",
    "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "transactions": []
  },
  "height": 1,
  "last_block_hash": "",
  "last_commit_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "last_results_hash": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
  "next_validators_hash": "4238f8531482f5edc3d6641d8180957815e2ed4af8869d826d09f7b214ac92d9",
  "proposer": {
    "address": "mxvaloper1k646g4axhsh9xyvlk3pfq0aqrrsyj6qqj85d5m",
    "description": {
      "moniker": "validator3",
      "identity": "",
      "website": "",
      "security_contact": "",
      "details": ""
    }
  },
  "sigs": [
    {
      "address": "mxvaloper17qj66wq56dmh7zpurj966kdzks9dnfmhv26s92",
      "signed": true
    },
    {
      "address": "mxvaloper1nwv0scqsz0hprwyd6gpvj4ykt3v7ztn97kjwc5",
      "signed": true
    },
    {
      "address": "mxvaloper1k646g4axhsh9xyvlk3pfq0aqrrsyj6qqj85d5m",
      "signed": true
    },
    {
      "address": "mxvaloper17u9dufjvscqh56u4kd7ag236u0wu3zrw9e8fwc",
      "signed": true
    }
  ],
  "timestamp": "2023-03-15T00:00:00.000Z",
  "txs": [],
  "validators_hash": "4238f8531482f5edc3d6641d8180957815e2ed4af8869d826d09f7b214ac92d9",
  "version": {
    "block": "11"
  }
}
```

</details>

### addresses -  Queries for account addresses

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/addresses](https://test.xfiscan.com/api/1.0/swagger#/addresses/AddressController_find)

Retrieve a list of account addresses.

#### Parameters

| Parameter        | Type            | Description                                                                                                                                                                                                  |
| ---------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| address          | string          | Account Address.                                                                                                                                                                                             |
| validatorAddress | string          | Validator Address.                                                                                                                                                                                           |
| addresses        | array \[string] | Account addresses array.                                                                                                                                                                                     |
| blockNumber      | string          |   Block Number.                                                                                                                                                                                              |
| page             | number          |   Page Number.                                                                                                                                                                                               |
| limit            | number          |   The number of entities to give away.                                                                                                                                                                       |
| sort             | string          | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field<br>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response</summary>

```bash
{
  "docs": [
    {
      "mx": "mx1j3ys0zehrles4y8vxmlxry03vnx4yltyg2alsv",
      "blockNumber": 1711526,
      "coins": [
        {
          "denom": "xfi",
          "amount": "951704940132136241914269"
        }
      ],
      "delegations": [],
      "evm": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
      "holdCoins": {
        "xfi": "951704940132136241914269"
      },
      "isValidator": false,
      "number": "90",
      "redelegations": [],
      "sequence": "1044",
      "timestamp": "2023-11-30T06:39:44.316Z",
      "unbonding_delegations": []
    }
  ],
  "hasNext": true,
  "limit": 1,
  "page": 1
}
```

</details>

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/addresses/{address}](https://test.xfiscan.com/api/1.0/swagger#/addresses/AddressController_findByHash)

Get address by hash of account address.

#### Parameters

| Parameter      | Type    | Description                                |
| -------------- | ------- | ------------------------------------------ |
| address        | string  | <p>Account Address<br>Mandatory field.</p> |
| withoutRewards | boolean | Awards where they're not needed.           |

<details>

<summary>Sample Response </summary>

```json
{
  "mx": "mx1j3ys0zehrles4y8vxmlxry03vnx4yltyg2alsv",
  "blockNumber": 1711526,
  "coins": [
    {
      "denom": "xfi",
      "amount": "951704940132136241914269"
    }
  ],
  "delegations": [],
  "evm": "0x9449078b371ff30a90ec36fe6191f164cd527d64",
  "holdCoins": {
    "xfi": "951704940132136241914269"
  },
  "isValidator": false,
  "number": "90",
  "redelegations": [],
  "sequence": "1044",
  "timestamp": "2023-11-30T06:39:44.316Z",
  "unbonding_delegations": [],
  "rewards": {
    "rewards": [],
    "total": []
  }
}
```

</details>

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/addresses/rich-list/{type}](https://test.xfiscan.com/api/1.0/swagger#/addresses/AddressController_richList)

Getting a list of addresses by the number of tokens purchased.

#### Parameters

| Parameter | Type   | Description                               |
| --------- | ------ | ----------------------------------------- |
| type      | string | Token type (MPX or XFI). Mandatory field. |

<details>

<summary>Sample Response</summary>

```json
{
  "docs": [
    {
      "mx": "mx1f83rnk6s2kqcdl0knp8dj6p5s9u5km925spepg",
      "blockNumber": 0,
      "coins": [
        {
          "denom": "mpx",
          "amount": "77605105225994146032010823"
        },
        {
          "denom": "xfi",
          "amount": "635906491456039568577746"
        }
      ],
      "delegations": [
        {
          "delegation": {
            "delegator_address": "mx1f83rnk6s2kqcdl0knp8dj6p5s9u5km925spepg",
            "validator_address": "mxvaloper1f83rnk6s2kqcdl0knp8dj6p5s9u5km92qmc8qh",
            "shares": "999999999999999999999999.000000000000000000"
          },
          "balance": {
            "denom": "mpx",
            "amount": "990000004052981946152236"
          }
        },
        {
          "delegation": {
            "delegator_address": "mx1f83rnk6s2kqcdl0knp8dj6p5s9u5km925spepg",
            "validator_address": "mxvaloper1nwv0scqsz0hprwyd6gpvj4ykt3v7ztn97kjwc5",
            "shares": "1.000000000000000000"
          },
          "balance": {
            "denom": "mpx",
            "amount": "1"
          }
        }
      ],
      "evm": "0x49e239db50558186fdf6984ed9683481794b6caa",
      "holdCoins": {
        "xfi": "635906491456039568577746",
        "mpx": "78595105230047127978163060"
      },
      "isValidator": false,
      "number": "5",
      "redelegations": [],
      "sequence": "3",
      "timestamp": "2024-10-06T13:39:56.390Z",
      "unbonding_delegations": []
    }
  ],
  "hasNext": true,
  "limit": 1,
  "page": 1
}
```

</details>

### validators -  Queries for validators.

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/validators](https://test.xfiscan.com/api/1.0/swagger#/validators/ValidatorController_find)

Getting a list of validators.

#### Parameters

| Parameter         | Type            | Description                                                                                                                                                                                                  |
| ----------------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| validatorJailed   | boolean         | If the validatorJailed field is true, it means that the validator is locked and temporarily cannot participate in the validation process and receive rewards.                                                |
| validatorStatuses | string          | The field filters validators by their current status.                                                                                                                                                        |
| ninAddresses      | array \[string] | The passed list ninAddresses of the threat from the search.                                                                                                                                                  |
| address           | string          | Account Address.                                                                                                                                                                                             |
| addresses         | array \[string] | Account addresses array.                                                                                                                                                                                     |
| page              | number          | Page number.                                                                                                                                                                                                 |
| limit             | number          | The number of entities to give away.                                                                                                                                                                         |
| sort              | string          | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field<br>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response</summary>

```json
{
  "docs": [
    {
      "validator": {
        "operator_address": "mxvaloper1f83rnk6s2kqcdl0knp8dj6p5s9u5km92qmc8qh",
        "consensus_pubkey": {
          "@type": "/cosmos.crypto.ed25519.PubKey",
          "key": "4xr65XxFRDaSxDZeoOKUaA2ct5P0FOdFRo7aFrEwuA4="
        },
        "jailed": true,
        "status": "BOND_STATUS_UNBONDED",
        "tokens": "990198998156041678366202",
        "delegator_shares": "1000201004143681884897493.256170380531418749",
        "description": {
          "moniker": "validator6",
          "identity": "",
          "website": "",
          "security_contact": "",
          "details": ""
        },
        "unbonding_height": "0",
        "unbonding_time": "2023-05-29T09:38:56.327294001Z",
        "commission": {
          "commission_rates": {
            "rate": "0.100000000000000000",
            "max_rate": "0.200000000000000000",
            "max_change_rate": "0.010000000000000000"
          },
          "update_time": "2023-03-15T00:00:00Z"
        },
        "min_self_delegation": "1",
        "mxAddress": "mx1f83rnk6s2kqcdl0knp8dj6p5s9u5km925spepg",
        "hexAddress": "f5eaed2e3f3afe488e66825802d31a00fb55aaad"
      },
      "active": true,
      "signedBlocks": 0,
      "unsignedBlocks": 0,
      "delegators_count": "25",
      "unbonding": [
        {
          "denom": "mpx",
          "amount": "0"
        }
      ],
      "unclaimed": []
    }
  ],
  "hasNext": true,
  "limit": 1,
  "page": 1
}
```

</details>

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/validators/{address}](https://test.xfiscan.com/api/1.0/swagger#/validators/ValidatorController_findByHash)

Getting the validator by the address.

#### Parameters

| Parameter | Type   | Description                                   |
| --------- | ------ | --------------------------------------------- |
| address   | string | <p>Validator Address.<br>Mandatory field.</p> |

<details>

<summary>Sample Response</summary>

```json
{
  "validator": {
    "operator_address": "mxvaloper1f83rnk6s2kqcdl0knp8dj6p5s9u5km92qmc8qh",
    "consensus_pubkey": {
      "@type": "/cosmos.crypto.ed25519.PubKey",
      "key": "4xr65XxFRDaSxDZeoOKUaA2ct5P0FOdFRo7aFrEwuA4="
    },
    "jailed": true,
    "status": "BOND_STATUS_UNBONDED",
    "tokens": "990198998156041678366202",
    "delegator_shares": "1000201004143681884897493.256170380531418749",
    "description": {
      "moniker": "validator6",
      "identity": "",
      "website": "",
      "security_contact": "",
      "details": ""
    },
    "unbonding_height": "0",
    "unbonding_time": "2023-05-29T09:38:56.327294001Z",
    "commission": {
      "commission_rates": {
        "rate": "0.100000000000000000",
        "max_rate": "0.200000000000000000",
        "max_change_rate": "0.010000000000000000"
      },
      "update_time": "2023-03-15T00:00:00Z"
    },
    "min_self_delegation": "1",
    "mxAddress": "mx1f83rnk6s2kqcdl0knp8dj6p5s9u5km925spepg",
    "hexAddress": "f5eaed2e3f3afe488e66825802d31a00fb55aaad"
  },
  "active": true,
  "signedBlocks": 0,
  "unsignedBlocks": 0,
  "delegators_count": "25",
  "unbonding": [
    {
      "denom": "mpx",
      "amount": "0"
    }
  ],
  "unclaimed": []
}
```

</details>

### stat -  Getting statistics

<mark style="background-color:blue;">GET</mark> [/api/1.0/stat](https://test.xfiscan.com/api/1.0/swagger#/stat/StatisticsController_findOne)

<details>

<summary>Sample Response</summary>

```json
{
  "validator": {
    "operator_address": "mxvaloper1f83rnk6s2kqcdl0knp8dj6p5s9u5km92qmc8qh",
    "consensus_pubkey": {
      "@type": "/cosmos.crypto.ed25519.PubKey",
      "key": "4xr65XxFRDaSxDZeoOKUaA2ct5P0FOdFRo7aFrEwuA4="
    },
    "jailed": true,
    "status": "BOND_STATUS_UNBONDED",
    "tokens": "990198998156041678366202",
    "delegator_shares": "1000201004143681884897493.256170380531418749",
    "description": {
      "moniker": "validator6",
      "identity": "",
      "website": "",
      "security_contact": "",
      "details": ""
    },
    "unbonding_height": "0",
    "unbonding_time": "2023-05-29T09:38:56.327294001Z",
    "commission": {
      "commission_rates": {
        "rate": "0.100000000000000000",
        "max_rate": "0.200000000000000000",
        "max_change_rate": "0.010000000000000000"
      },
      "update_time": "2023-03-15T00:00:00Z"
    },
    "min_self_delegation": "1",
    "mxAddress": "mx1f83rnk6s2kqcdl0knp8dj6p5s9u5km925spepg",
    "hexAddress": "f5eaed2e3f3afe488e66825802d31a00fb55aaad"
  },
  "active": true,
  "signedBlocks": 0,
  "unsignedBlocks": 0,
  "delegators_count": "25",
  "unbonding": [
    {
      "denom": "mpx",
      "amount": "0"
    }
  ],
  "unclaimed": []
}
```

</details>

### event-logs - Smart contracts logs

<mark style="background-color:blue;">GET</mark> [/api/1.0/event-logs](https://test.xfiscan.com/api/1.0/swagger#/event-logs/EventLogController_find)

Getting smart contracts logs.

#### Parameters

| Parameter                    | Type   | Description                                                                                                                                                                                                  |
| ---------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>blockHash</p><p> </p>     | string | Block hash.                                                                                                                                                                                                  |
| <p>originAddress</p><p> </p> | string | The address that called the smart contract.                                                                                                                                                                  |
| transactionHash              | string | Transaction hash.                                                                                                                                                                                            |
| transactionIndex             | number | The log index in the transaction.                                                                                                                                                                            |
| blockNumber                  | string | Block number.                                                                                                                                                                                                |
| contractAddress              | string | Smart contract address.                                                                                                                                                                                      |
| page                         | number | Page number.                                                                                                                                                                                                 |
| limit                        | number | The number of entities to give away.                                                                                                                                                                         |
| sort                         | string | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field<br>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response </summary>

```json
{
  "validator": {
    "operator_address": "mxvaloper1f83rnk6s2kqcdl0knp8dj6p5s9u5km92qmc8qh",
    "consensus_pubkey": {
      "@type": "/cosmos.crypto.ed25519.PubKey",
      "key": "4xr65XxFRDaSxDZeoOKUaA2ct5P0FOdFRo7aFrEwuA4="
    },
    "jailed": true,
    "status": "BOND_STATUS_UNBONDED",
    "tokens": "990198998156041678366202",
    "delegator_shares": "1000201004143681884897493.256170380531418749",
    "description": {
      "moniker": "validator6",
      "identity": "",
      "website": "",
      "security_contact": "",
      "details": ""
    },
    "unbonding_height": "0",
    "unbonding_time": "2023-05-29T09:38:56.327294001Z",
    "commission": {
      "commission_rates": {
        "rate": "0.100000000000000000",
        "max_rate": "0.200000000000000000",
        "max_change_rate": "0.010000000000000000"
      },
      "update_time": "2023-03-15T00:00:00Z"
    },
    "min_self_delegation": "1",
    "mxAddress": "mx1f83rnk6s2kqcdl0knp8dj6p5s9u5km925spepg",
    "hexAddress": "f5eaed2e3f3afe488e66825802d31a00fb55aaad"
  },
  "active": true,
  "signedBlocks": 0,
  "unsignedBlocks": 0,
  "delegators_count": "25",
  "unbonding": [
    {
      "denom": "mpx",
      "amount": "0"
    }
  ],
  "unclaimed": []
}
```

</details>

### contracts - Smart contracts queries

&#x20;<mark style="background-color:blue;">GET</mark> [/api/1.0/contracts](https://dev.xfiscan.com/api/1.0/swagger#/contracts/ContractController_find)

Getting smart contracts.

#### Parameters

| Parameter                      | Type    | Description                                                                                                                                                                                                     |
| ------------------------------ | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>contractAddress</p><p> </p> | string  | <p>Smart Contract Address.</p><p><br></p>                                                                                                                                                                       |
| <p>tokenType</p><p> </p>       | string  | Search by token type.                                                                                                                                                                                           |
| creatorAddress                 | string  | The address of the contract creator.                                                                                                                                                                            |
| txHash                         | string  | Contract hash.                                                                                                                                                                                                  |
| blockNumber                    | string  | Block Number.                                                                                                                                                                                                   |
| verified                       | boolean | Whether or not the smart contract is verified.                                                                                                                                                                  |
| page                           | number  | Page Number.                                                                                                                                                                                                    |
| limit                          | number  | The number of entities to be given away.                                                                                                                                                                        |
| sort                           | string  | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field</p><p>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response</summary>

[https://test.xfiscan.com/api/1.0/contracts](https://test.xfiscan.com/api/1.0/contracts)

</details>

<mark style="background-color:blue;">**GET**</mark>[**/api/1.0/contracts/compiler-versions**](https://test.xfiscan.com/api/1.0/swagger#/contracts/ContractController_compilerVersions)

Getting a list of compiler versions.

<details>

<summary>Sample Response</summary>

```json
[
  "0.8.28",
  "0.8.27",
  "0.8.26",
  "0.8.25",
  "0.8.24",
  "0.8.23",
  "0.8.22",
  "0.8.21",
  "0.8.20",
  "0.8.19",
  "0.8.18",
  "0.8.17",
  "0.8.16",
  "0.8.15",
  "0.8.14",
  "0.8.13",
  "0.8.12",
  "0.8.11",
  "0.8.10",
  "0.8.9",
  "0.8.8",
  "0.8.7",
  "0.8.6",
  "0.8.5",
  "0.8.4",
  "0.8.3",
  "0.8.2",
  "0.8.1",
  "0.8.0",
  "0.7.6",
  "0.7.5",
  "0.7.4",
  "0.7.3",
  "0.7.2",
  "0.7.1",
  "0.7.0",
  "0.6.12",
  "0.6.11",
  "0.6.10",
  "0.6.9",
  "0.6.8",
  "0.6.7",
  "0.6.6",
  "0.6.5",
  "0.6.4",
  "0.6.3",
  "0.6.2",
  "0.6.1",
  "0.6.0",
  "0.5.17",
  "0.5.16",
  "0.5.15",
  "0.5.14",
  "0.5.13",
  "0.5.12",
  "0.5.11",
  "0.5.10",
  "0.5.9",
  "0.5.8",
  "0.5.7",
  "0.5.6",
  "0.5.5",
  "0.5.4",
  "0.5.3",
  "0.5.2",
  "0.5.1",
  "0.5.0",
  "0.4.26",
  "0.4.25",
  "0.4.24",
  "0.4.23",
  "0.4.22",
  "0.4.21",
  "0.4.20",
  "0.4.19",
  "0.4.18",
  "0.4.17",
  "0.4.16",
  "0.4.15",
  "0.4.14",
  "0.4.13",
  "0.4.12",
  "0.4.11",
  "0.4.10"
]
```

</details>

#### <mark style="background-color:blue;">GET</mark> [/api/1.0/contracts/{address}](https://test.xfiscan.com/api/1.0/swagger#/contracts/ContractController_findOne)

Getting the address of a smart contract.

#### Parameters

| Parameter | Type   | Description                       |
| --------- | ------ | --------------------------------- |
| address   | string | Contract Address. Required field. |

<details>

<summary>Sample Response </summary>

```
{
  "_id": "679d05091b2f6507083becba",
  "contractAddress": "0x516354c4024246173b06f1d7bf834de3865b7a47",
  "blockNumber": 1819079,
  "bytecode": "0x60a06040523480156200001157600080fd5b5060405162003880380380620038808339810160408190526200003491620001da565b6200003f336200006a565b6001600160a01b038216608052805162000061906001906020840190620000ba565b5050506200049c565b600080546001600160a01b038381166001600160a01b0319831681178455604051919092169283917f8be0079c531659141344cd1fd0a4f28419497f9722a3daafe3b4186f6b6457e09190a35050565b82805482825590600052602060002090810192821562000105579160200282015b82811115620001055782518290620000f49082620003d0565b5091602001919060010190620000db565b506200011392915062000117565b5090565b80821115620001135760006200012e828262000138565b5060010162000117565b508054620001469062000341565b6000825580601f1062000157575050565b601f0160209004906000526020600020908101906200017791906200017a565b50565b5b808211156200011357600081556001016200017b565b634e487b7160e01b600052604160045260246000fd5b604051601f8201601f191681016001600160401b0381118282101715620001d257620001d262000191565b604052919050565b6000806040808486031215620001ef57600080fd5b83516001600160a01b03811681146200020757600080fd5b602085810151919450906001600160401b03808211156200022757600080fd5b8187019150601f88818401126200023d57600080fd5b82518281111562000252576200025262000191565b8060051b62000263868201620001a7565b918252848101860191868101908c8411156200027e57600080fd5b87870192505b838310156200032e578251868111156200029e5760008081fd5b8701603f81018e13620002b15760008081fd5b8881015187811115620002c857620002c862000191565b620002db818801601f19168b01620001a7565b8181528f8c838501011115620002f15760008081fd5b60005b8281101562000311578381018d01518282018d01528b01620002f4565b5060009181018b0191909152835250918701919087019062000284565b8099505050505050505050509250929050565b600181811c908216806200035657607f821691505b6020821081036200037757634e487b7160e01b600052602260045260246000fd5b50919050565b601f821115620003cb57600081815260208120601f850160051c81016020861015620003a65750805b601f850160051c820191505b81811015620003c757828155600101620003b2565b5050505b505050565b81516001600160401b03811115620003ec57620003ec62000191565b6200040481620003fd845462000341565b846200037d565b602080601f8311600181146200043c5760008415620004235750858301515b600019600386901b1c1916600185901b178555620003c7565b600085815260208120601f198616915b828110156200046d578886015182559484019460019091019084016200044c565b50858210156200048c5787850151600019600388901b60f8161c191681555b5050505050600190811b01905550565b6080516133c1620004bf600039600081816101ea015261141901526133c16000f3fe608060405234801561001057600080fd5b50600436106101365760003560e01c80638e5ea8df116100b2578063b241d0d311610081578063e0a8541211610066578063e0a85412146102ec578063ec11c823146102ff578063f2fde38b1461031257600080fd5b8063b241d0d3146102c6578063b4a85801146102d957600080fd5b80638e5ea8df146102485780639061b9231461025b578063a1cbcbaf1461026e578063a6b16419146102a657600080fd5b8063715018a6116101095780637b103999116100ee5780637b103999146101e55780638da5cb5b146102245780638e25a0f31461023557600080fd5b8063715018a6146101c857806376286c00146101d257600080fd5b806301ffc9a71461013b5780630667cfea14610163578063206c74c9146101845780636dc4fb73146101a5575b600080fd5b61014e610149366004612170565b610325565b60405190151581526020015b60405180910390f35b610176610171366004612397565b61035c565b60405161015a929190612475565b610197610192366004612520565b610391565b60405161015a929190612589565b6101b86101b33660046125fe565b61047e565b60405161015a949392919061266a565b6101d061054b565b005b6101976101e03660046126a6565b61055f565b61020c7f000000000000000000000000000000000000000000000000000000000000000081565b6040516001600160a01b03909116815260200161015a565b6000546001600160a01b031661020c565b610176610243366004612705565b610587565b6101d06102563660046127cb565b61061c565b610176610269366004612808565b61063b565b61028161027c366004612867565b610734565b604080516001600160a01b03909416845260208401929092529082015260600161015a565b6102b96102b43660046128a9565b61075a565b60405161015a91906128c2565b6101b86102d43660046128d5565b610806565b6101976102e73660046125fe565b6108f7565b6101766102fa3660046125fe565b61093b565b6101b861030d366004612867565b61099f565b6101d0610320366004612949565b610a94565b60006001600160e01b03198216639061b92360e01b148061035657506301ffc9a760e01b6001600160e01b03198316145b92915050565b606060006103848686868663e0a8541260e01b60405180602001604052806000815250610587565b9150915094509492505050565b606060006104728585856001805480602002602001604051908101604052809291908181526020016000905b828210156104695783829060005260206000200180546103dc90612966565b80601f016020809104026020016040519081016040528092919081815260200182805461040890612966565b80156104555780601f1061042a57610100808354040283529160200191610455565b820191906000526020600020905b81548152906001019060200180831161043857829003601f168201915b5050505050815260200190600101906103bd565b5050505061055f565b91509150935093915050565b6060600080808080808061049c8c8c8c8c636dc4fb7360e01b610b29565b935093509350935060008151111561050e57600080828060200190518101906104c591906129e5565b915091506000866000815181106104de576104de612a37565b60200260200101518060200190518101906104f99190612a4d565b929a5091985096509294506105409350505050565b6105338460008151811061052457610524612a37565b60200260200101518484610eaf565b9750975097509750505050505b945094509450949050565b610553611010565b61055d600061106a565b565b606060006103848686868663b4a8580160e01b604051806020016040528060008152506110d2565b6040805160018082528183019092526060916000918291816020015b60608152602001906001900390816105a357905050905086816000815181106105ce576105ce612a37565b60200260200101819052506000806105ea8b8b858b8b8b6110d2565b915091508160008151811061060157610601612a37565b60200260200101518194509450505050965096945050505050565b610624611010565b805161063790600190602084019061209d565b5050565b606060006104728585856001805480602002602001604051908101604052809291908181526020016000905b8282101561071357838290600052602060002001805461068690612966565b80601f01602080910402602001604051908101604052809291908181526020018280546106b290612966565b80156106ff5780601f106106d4576101008083540402835291602001916106ff565b820191906000526020600020905b8154815290600101906020018083116106e257829003601f168201915b505050505081526020019060010190610667565b5050505063e0a8541260e01b60405180602001604052806000815250610587565b60008060008060008061074988886000611212565b919750955093505050509250925092565b6001818154811061076a57600080fd5b90600052602060002001600091509050805461078590612966565b80601f01602080910402602001604051908101604052809291908181526020018280546107b190612966565b80156107fe5780601f106107d3576101008083540402835291602001916107fe565b820191906000526020600020905b8154815290600101906020018083116107e157829003601f168201915b505050505081565b6060600080600080610852600089898080601f01602080910402602001604051908101604052809392919081815260200183838082843760009201919091525092939250506114c09050565b60405160240161086491815260200190565b60408051601f19818403018152918152602080830180516001600160e01b03167f691f3431000000000000000000000000000000000000000000000000000000001790528151908101909152600080825291925081906108d4908b908b9086908c90636dc4fb7360e01b90610587565b915091506108e382828a610eaf565b965096509650965050505093509350935093565b60606000808061092a888888887fb4a8580100000000000000000000000000000000000000000000000000000000610b29565b50919a909950975050505050505050565b60606000808061096e888888887fe0a8541200000000000000000000000000000000000000000000000000000000610b29565b5050915091508160008151811061098757610987612a37565b60200260200101518193509350505094509492505050565b60606000806000610a8286866001805480602002602001604051908101604052809291908181526020016000905b82821015610a795783829060005260206000200180546109ec90612966565b80601f0160208091040260200160405190810160405280929190818152602001828054610a1890612966565b8015610a655780601f10610a3a57610100808354040283529160200191610a65565b820191906000526020600020905b815481529060010190602001808311610a4857829003601f168201915b5050505050815260200190600101906109cd565b50505050610806565b93509350935093505b92959194509250565b610a9c611010565b6001600160a01b038116610b1d5760405162461bcd60e51b815260206004820152602660248201527f4f776e61626c653a206e6577206f776e657220697320746865207a65726f206160448201527f646472657373000000000000000000000000000000000000000000000000000060648201526084015b60405180910390fd5b610b268161106a565b50565b60606000606080610b8d60405180610100016040528060608152602001606081526020016060815260200160006001600160e01b031916815260200160001515815260200160006001600160a01b0316815260200160608152602001606081525090565b6001600160e01b031986166060820152600080610bac8b8d018d612a78565b90925090506060610bbf8a8c018c612b30565b60c089019190915260408801919091526001600160a01b0390911660a08701529015156080860152805183519192501015610bf957600080fd5b805167ffffffffffffffff811115610c1357610c136121dd565b604051908082528060200260200182016040528015610c4657816020015b6060815260200190600190039081610c315790505b506020850152805167ffffffffffffffff811115610c6657610c666121dd565b604051908082528060200260200182016040528015610c8f578160200160208202803683370190505b5060e08501526000805b8251811015610e7d578251600090849083908110610cb957610cb9612a37565b6020026020010151600001516001600160e01b03191603610d1857828181518110610ce657610ce6612a37565b60200260200101516020015186602001518281518110610d0857610d08612a37565b6020026020010181905250610e6b565b848281518110610d2a57610d2a612a37565b602002602001015115610da15760018660e001518281518110610d4f57610d4f612a37565b602002602001019015159081151581525050838281518110610d7357610d73612a37565b602002602001015186602001518281518110610d9157610d91612a37565b6020026020010181905250610e5d565b828181518110610db357610db3612a37565b602002602001015160000151848381518110610dd157610dd1612a37565b6020026020010151848381518110610deb57610deb612a37565b602002602001015160200151604051602401610e08929190612cb4565b604051602081830303815290604052906001600160e01b0319166020820180516001600160e01b03838183161783525050505086602001518281518110610e5157610e51612a37565b60200260200101819052505b610e68826001612cf8565b91505b80610e7581612d0b565b915050610c99565b50610e878561157f565b8560a0015186604001518760c001519850985098509850505050505095509550955095915050565b606060008060008087806020019051810190610ecb9190612d24565b9050600080610ed9836119c9565b91509150600081604051602401610ef291815260200190565b60408051601f19818403018152918152602080830180516001600160e01b03167f3b3b57de000000000000000000000000000000000000000000000000000000001790529051919250600091610f4c9187918e9101612475565b6040516020818303038152906040529050600080306001600160a01b0316638e25a0f387868f636dc4fb7360e01b886040518663ffffffff1660e01b8152600401610f9b959493929190612db1565b600060405180830381865afa158015610fb8573d6000803e3d6000fd5b505050506040513d6000823e601f3d908101601f19168201604052610fe091908101906129e5565b91509150600082806020019051810190610ffa9190612a4d565b979f979e50909b50959950505050505050505050565b6000546001600160a01b0316331461055d5760405162461bcd60e51b815260206004820181905260248201527f4f776e61626c653a2063616c6c6572206973206e6f7420746865206f776e65726044820152606401610b14565b600080546001600160a01b038381167fffffffffffffffffffffffff0000000000000000000000000000000000000000831681178455604051919092169283917f8be0079c531659141344cd1fd0a4f28419497f9722a3daafe3b4186f6b6457e09190a35050565b606060008060006110e38a8a610734565b919450849350909150506001600160a01b03821661112d576040517f7199966d00000000000000000000000000000000000000000000000000000000815260040160405180910390fd5b604080516101206020601f8d01819004028201810190925261010081018b815283151592611202929182918f908f9081908501838280828437600092019190915250505090825250602081018c9052604081018b90526001600160e01b03198a16606082015283151560808201526001600160a01b03871660a082015260c081018990528b5160e09091019067ffffffffffffffff8111156111d1576111d16121dd565b6040519080825280602002602001820160405280156111fa578160200160208202803683370190505b50905261157f565b9450505050965096945050505050565b60008060008086868681811061122a5761122a612a37565b919091013560f81c915050600081900361124e5750600092508291508390506114b7565b600061125a8287612cf8565b611265906001612cf8565b905060008260421480156112ab57508888611281896001612cf8565b81811061129057611290612a37565b9050013560f81c60f81b6001600160f81b031916605b60f81b145b80156112e9575088886112bf600185612e1a565b8181106112ce576112ce612a37565b9050013560f81c60f81b6001600160f81b031916605d60f81b145b1561136157611359600060408b8b6113028c6002612cf8565b9061130e600189612e1a565b9261131b93929190612e2d565b8080601f016020809104026020016040519081016040528093929190818152602001838380828437600092019190915250929493925050611bf29050565b509050611393565b888861136e896001612cf8565b61137a92859290612e2d565b604051611388929190612e57565b604051809103902090505b60008060006113a38c8c87611212565b925092509250600082856040516020016113c7929190918252602082015260400190565b60408051601f198184030181529082905280516020909101207f0178b8bf0000000000000000000000000000000000000000000000000000000082526004820181905291506000906001600160a01b037f00000000000000000000000000000000000000000000000000000000000000001690630178b8bf90602401602060405180830381865afa158015611460573d6000803e3d6000fd5b505050506040513d601f19601f820116820180604052508101906114849190612a4d565b90506001600160a01b038116156114a857995097508996506114b795505050505050565b50929850919650909450505050505b93509350939050565b60008060006114cf8585611cc3565b90925090508161154157600185516114e79190612e1a565b84146115355760405162461bcd60e51b815260206004820152601d60248201527f6e616d65686173683a204a756e6b20617420656e64206f66206e616d650000006044820152606401610b14565b50600091506103569050565b61154b85826114c0565b6040805160208101929092528101839052606001604051602081830303815290604052805190602001209250505092915050565b6020810151516060906000808267ffffffffffffffff8111156115a4576115a46121dd565b60405190808252806020026020018201604052801561160257816020015b6115ef604051806060016040528060006001600160a01b0316815260200160608152602001606081525090565b8152602001906001900390816115c25790505b50905060008367ffffffffffffffff811115611620576116206121dd565b60405190808252806020026020018201604052801561166657816020015b60408051808201909152600081526060602082015281526020019060019003908161163e5790505b5090508367ffffffffffffffff811115611682576116826121dd565b6040519080825280602002602001820160405280156116b557816020015b60608152602001906001900390816116a05790505b5086515160a088015191965015906000906116cf90611d7a565b9050876080015180156116e0575080155b15611717576040517f82c2c72800000000000000000000000000000000000000000000000000000000815260040160405180910390fd5b60005b868110156119075760008960200151828151811061173a5761173a612a37565b6020026020010151905060008a60e00151838151811061175c5761175c612a37565b60200260200101519050801561179157818a848151811061177f5761177f612a37565b602002602001018190525050506118f5565b8415801561179c5750835b156117e2578a516040516117b591908490602401612cb4565b60408051601f198184030181529190526020810180516001600160e01b0316639061b92360e01b17905291505b6000806000806117f68f60a0015187611df5565b9350935093509350831561186b57828060200190518101906118189190612ee7565b8b8d8151811061182a5761182a612a37565b6020026020010181905250818a888151811061184857611848612a37565b602090810291909101015261185e60018d612cf8565b9b505050505050506118f5565b8080156118755750875b15611891578280602001905181019061188e9190612d24565b92505b828e88815181106118a4576118a4612a37565b60200260200101819052508e6020015187815181106118c5576118c5612a37565b60200260200101518a88815181106118df576118df612a37565b6020026020010151602001819052505050505050505b806118ff81612d0b565b91505061171a565b508460000361191b57505050505050919050565b84845230886040015163a780bab660e01b8660405160240161193d9190612fe2565b604051602081830303815290604052906001600160e01b0319166020820180516001600160e01b0383818316178352505050508a606001518b608001518c60a001518d604001518e60c001518a60405160200161199e959493929190613044565b60408051601f1981840301815290829052630556f18360e41b8252610b149594939291600401613101565b8051606090600090819084906119e0816002612cf8565b67ffffffffffffffff8111156119f8576119f86121dd565b6040519080825280601f01601f191660200182016040528015611a22576020820181803683370190505b50945060009350808403611a6757600060f81b85600081518110611a4857611a48612a37565b60200101906001600160f81b031916908160001a905350505050915091565b60001981015b828181518110611a7f57611a7f612a37565b01602001517fff00000000000000000000000000000000000000000000000000000000000000167f2e0000000000000000000000000000000000000000000000000000000000000003611b41578360f81b868260010181518110611ae557611ae5612a37565b60200101906001600160f81b031916908160001a90535084611b0e846001840160ff8816611f92565b60408051602081019390935282015260600160405160208183030381529060405280519060200120945060009350611b91565b600184019350828181518110611b5957611b59612a37565b602001015160f81c60f81b868260010181518110611b7957611b79612a37565b60200101906001600160f81b031916908160001a9053505b8015611ba05760001901611a6d565b5083611bb183600060ff8716611f92565b6040805160208101939093528201526060016040516020818303038152906040528051906020012093508260f81b85600081518110611a4857611a48612a37565b8251600090600190831115611c0657600080fd5b611c57565b6000603a8210602f83111615611c235750602f190190565b60478210604083111615611c3957506036190190565b60678210606083111615611c4f57506056190190565b5060ff919050565b60208501845b84811015611cb957611c748183015160001a611c0b565b611c866001830184015160001a611c0b565b60ff811460ff83141715611c9f57600094505050611cb9565b60049190911b1760089490941b9390931792600201611c5d565b5050935093915050565b60008083518310611d165760405162461bcd60e51b815260206004820152601e60248201527f726561644c6162656c3a20496e646578206f7574206f6620626f756e647300006044820152606401610b14565b6000848481518110611d2a57611d2a612a37565b016020015160f81c90508015611d5657611d4f85611d49866001612cf8565b83611f92565b9250611d5b565b600092505b611d658185612cf8565b611d70906001612cf8565b9150509250929050565b6040516301ffc9a760e01b8152639061b92360e01b60048201526000906001600160a01b038316906301ffc9a79061c350906024016020604051808303818786fa93505050508015611de9575060408051601f3d908101601f19168201909252611de691810190613135565b60015b61035657506000919050565b60408051808201909152600080825260606020830181905290916000611e1b8686611fb6565b90503d8115611e41576000611e31600083612048565b909550935060019150610a8b9050565b60048110611f88576000611e5760006004612048565b90506000611e6f6004611e6a8186612e1a565b612048565b9050630556f18360e41b611e8283613152565b6001600160e01b03191603611f5057600080600080600085806020019051810190611ead919061318a565b945094509450945094508d6001600160a01b0316856001600160a01b031603611f46576040518060600160405280866001600160a01b0316815260200185815260200184815250604051602001611f04919061323a565b60408051601f198184030181528282019091526001600160e01b03199093168152602081019190915260019b50909950975060009650610a8b95505050505050565b5050505050611f85565b8181604051602001611f6392919061324d565b60408051601f19818403018152919052600097509550869350610a8b92505050565b50505b5092959194509250565b8251600090611fa18385612cf8565b1115611fac57600080fd5b5091016020012090565b60006001600160a01b0383163b6120355760405162461bcd60e51b815260206004820152602e60248201527f4c6f774c6576656c43616c6c5574696c733a207374617469632063616c6c207460448201527f6f206e6f6e2d636f6e74726163740000000000000000000000000000000000006064820152608401610b14565b600080835160208501865afa9392505050565b60608167ffffffffffffffff811115612063576120636121dd565b6040519080825280601f01601f19166020018201604052801561208d576020820181803683370190505b5090508183602083013e92915050565b8280548282559060005260206000209081019282156120e3579160200282015b828111156120e357825182906120d390826132cb565b50916020019190600101906120bd565b506120ef9291506120f3565b5090565b808211156120ef5760006121078282612110565b506001016120f3565b50805461211c90612966565b6000825580601f1061212c575050565b601f016020900490600052602060002090810190610b2691905b808211156120ef5760008155600101612146565b6001600160e01b031981168114610b2657600080fd5b60006020828403121561218257600080fd5b813561218d8161215a565b9392505050565b60008083601f8401126121a657600080fd5b50813567ffffffffffffffff8111156121be57600080fd5b6020830191508360208285010111156121d657600080fd5b9250929050565b634e487b7160e01b600052604160045260246000fd5b6040805190810167ffffffffffffffff81118282101715612216576122166121dd565b60405290565b604051601f8201601f1916810167ffffffffffffffff81118282101715612245576122456121dd565b604052919050565b600067ffffffffffffffff821115612267576122676121dd565b50601f01601f191660200190565b60006122886122838461224d565b61221c565b905082815283838301111561229c57600080fd5b828260208301376000602084830101529392505050565b600082601f8301126122c457600080fd5b61218d83833560208501612275565b600067ffffffffffffffff8211156122ed576122ed6121dd565b5060051b60200190565b600082601f83011261230857600080fd5b81356020612318612283836122d3565b82815260059290921b8401810191818101908684111561233757600080fd5b8286015b8481101561238c57803567ffffffffffffffff81111561235b5760008081fd5b8701603f8101891361236d5760008081fd5b61237e898683013560408401612275565b84525091830191830161233b565b509695505050505050565b600080600080606085870312156123ad57600080fd5b843567ffffffffffffffff808211156123c557600080fd5b6123d188838901612194565b909650945060208701359150808211156123ea57600080fd5b6123f6888389016122b3565b9350604087013591508082111561240c57600080fd5b50612419878288016122f7565b91505092959194509250565b60005b83811015612440578181015183820152602001612428565b50506000910152565b60008151808452612461816020860160208601612425565b601f01601f19169290920160200192915050565b6040815260006124886040830185612449565b90506001600160a01b03831660208301529392505050565b600082601f8301126124b157600080fd5b813560206124c1612283836122d3565b82815260059290921b840181019181810190868411156124e057600080fd5b8286015b8481101561238c57803567ffffffffffffffff8111156125045760008081fd5b6125128986838b01016122b3565b8452509183019183016124e4565b60008060006040848603121561253557600080fd5b833567ffffffffffffffff8082111561254d57600080fd5b61255987838801612194565b9095509350602086013591508082111561257257600080fd5b5061257f868287016124a0565b9150509250925092565b6000604082016040835280855180835260608501915060608160051b8601019250602080880160005b838110156125e057605f198887030185526125ce868351612449565b955093820193908201906001016125b2565b50508394506001600160a01b03871681870152505050509392505050565b6000806000806040858703121561261457600080fd5b843567ffffffffffffffff8082111561262c57600080fd5b61263888838901612194565b9096509450602087013591508082111561265157600080fd5b5061265e87828801612194565b95989497509550505050565b60808152600061267d6080830187612449565b6001600160a01b0395861660208401529385166040830152509216606090920191909152919050565b600080600080606085870312156126bc57600080fd5b843567ffffffffffffffff808211156126d457600080fd5b6126e088838901612194565b909650945060208701359150808211156126f957600080fd5b6123f6888389016124a0565b60008060008060008060a0878903121561271e57600080fd5b863567ffffffffffffffff8082111561273657600080fd5b6127428a838b01612194565b9098509650602089013591508082111561275b57600080fd5b6127678a838b016122b3565b9550604089013591508082111561277d57600080fd5b6127898a838b016122f7565b94506060890135915061279b8261215a565b909250608088013590808211156127b157600080fd5b506127be89828a016122b3565b9150509295509295509295565b6000602082840312156127dd57600080fd5b813567ffffffffffffffff8111156127f457600080fd5b612800848285016122f7565b949350505050565b60008060006040848603121561281d57600080fd5b833567ffffffffffffffff8082111561283557600080fd5b61284187838801612194565b9095509350602086013591508082111561285a57600080fd5b5061257f868287016122b3565b6000806020838503121561287a57600080fd5b823567ffffffffffffffff81111561289157600080fd5b61289d85828601612194565b90969095509350505050565b6000602082840312156128bb57600080fd5b5035919050565b60208152600061218d6020830184612449565b6000806000604084860312156128ea57600080fd5b833567ffffffffffffffff8082111561290257600080fd5b61290e87838801612194565b9095509350602086013591508082111561292757600080fd5b5061257f868287016122f7565b6001600160a01b0381168114610b2657600080fd5b60006020828403121561295b57600080fd5b813561218d81612934565b600181811c9082168061297a57607f821691505b60208210810361299a57634e487b7160e01b600052602260045260246000fd5b50919050565b600082601f8301126129b157600080fd5b81516129bf6122838261224d565b8181528460208386010111156129d457600080fd5b612800826020830160208701612425565b600080604083850312156129f857600080fd5b825167ffffffffffffffff811115612a0f57600080fd5b612a1b858286016129a0565b9250506020830151612a2c81612934565b809150509250929050565b634e487b7160e01b600052603260045260246000fd5b600060208284031215612a5f57600080fd5b815161218d81612934565b8015158114610b2657600080fd5b60008060408385031215612a8b57600080fd5b823567ffffffffffffffff80821115612aa357600080fd5b818501915085601f830112612ab757600080fd5b81356020612ac7612283836122d3565b82815260059290921b84018101918181019089841115612ae657600080fd5b948201945b83861015612b0d578535612afe81612a6a565b82529482019490820190612aeb565b96505086013592505080821115612b2357600080fd5b50611d70858286016124a0565b600080600080600060a08688031215612b4857600080fd5b612b528635612a6a565b85359450612b636020870135612934565b6020860135935067ffffffffffffffff8060408801351115612b8457600080fd5b612b9488604089013589016122f7565b93508060608801351115612ba757600080fd5b612bb788606089013589016122b3565b92508060808801351115612bca57600080fd5b6080870135870188601f820112612be057600080fd5b612bed61228382356122d3565b81358082526020808301929160051b8401018b1015612c0b57600080fd5b602083015b6020843560051b850101811015612ca2578481351115612c2f57600080fd5b803584016040818e03601f19011215612c4757600080fd5b612c4f6121f3565b612c5c602083013561215a565b602082013581528660408301351115612c7457600080fd5b612c878e602060408501358501016122b3565b60208201528085525050602083019250602081019050612c10565b50809450505050509295509295909350565b604081526000612cc76040830185612449565b8281036020840152612cd98185612449565b95945050505050565b634e487b7160e01b600052601160045260246000fd5b8082018082111561035657610356612ce2565b600060018201612d1d57612d1d612ce2565b5060010190565b600060208284031215612d3657600080fd5b815167ffffffffffffffff811115612d4d57600080fd5b612800848285016129a0565b600082825180855260208086019550808260051b84010181860160005b84811015612da457601f19868403018952612d92838351612449565b98840198925090830190600101612d76565b5090979650505050505050565b60a081526000612dc460a0830188612449565b8281036020840152612dd68188612449565b90508281036040840152612dea8187612d59565b90506001600160e01b0319851660608401528281036080840152612e0e8185612449565b98975050505050505050565b8181038181111561035657610356612ce2565b60008085851115612e3d57600080fd5b83861115612e4a57600080fd5b5050820193919092039150565b8183823760009101908152919050565b600082601f830112612e7857600080fd5b81516020612e88612283836122d3565b82815260059290921b84018101918181019086841115612ea757600080fd5b8286015b8481101561238c57805167ffffffffffffffff811115612ecb5760008081fd5b612ed98986838b01016129a0565b845250918301918301612eab565b600060208284031215612ef957600080fd5b815167ffffffffffffffff80821115612f1157600080fd5b9083019060608286031215612f2557600080fd5b604051606081018181108382111715612f4057612f406121dd565b6040528251612f4e81612934565b8152602083015182811115612f6257600080fd5b612f6e87828601612e67565b602083015250604083015182811115612f8657600080fd5b612f92878286016129a0565b60408301525095945050505050565b6001600160a01b0381511682526000602082015160606020850152612fc96060850182612d59565b905060408301518482036040860152612cd98282612449565b6000602080830181845280855180835260408601915060408160051b870101925083870160005b8281101561303757603f19888603018452613025858351612fa1565b94509285019290850190600101613009565b5092979650505050505050565b8515158152600060206001600160a01b03871681840152604060a08185015261307060a0850188612d59565b84810360608601526130828188612449565b905084810360808601528086518083528483019150848160051b84010185890160005b838110156130ee57858303601f19018552815180516001600160e01b03191684528801518884018890526130db88850182612449565b95890195935050908701906001016130a5565b50909d9c50505050505050505050505050565b6001600160a01b038616815260a06020820152600061312360a0830187612d59565b8281036040840152612dea8187612449565b60006020828403121561314757600080fd5b815161218d81612a6a565b6000815160208301516001600160e01b0319808216935060048310156131825780818460040360031b1b83161693505b505050919050565b600080600080600060a086880312156131a257600080fd5b85516131ad81612934565b602087015190955067ffffffffffffffff808211156131cb57600080fd5b6131d789838a01612e67565b955060408801519150808211156131ed57600080fd5b6131f989838a016129a0565b94506060880151915061320b8261215a565b60808801519193508082111561322057600080fd5b5061322d888289016129a0565b9150509295509295909350565b60208152600061218d6020830184612fa1565b6000835161325f818460208801612425565b835190830190613273818360208801612425565b01949350505050565b601f8211156132c657600081815260208120601f850160051c810160208610156132a35750805b601f850160051c820191505b818110156132c2578281556001016132af565b5050505b505050565b815167ffffffffffffffff8111156132e5576132e56121dd565b6132f9816132f38454612966565b8461327c565b602080601f83116001811461332e57600084156133165750858301515b600019600386901b1c1916600185901b1785556132c2565b600085815260208120601f198616915b8281101561335d5788860151825594840194600190910190840161333e565b508582101561337b5787850151600019600388901b60f8161c191681555b5050505050600190811b0190555056fea2646970667358221220fe9326ee5538b7f9616057320df0aa1d5bfe9c93fa8e618d955c777a8e60471164736f6c6343000811003300000000000000000000000049a7e4e0741cc91d5ff9cbf86d3ca1893f76b7d700000000000000000000000000000000000000000000000000000000000000400000000000000000000000000000000000000000000000000000000000000002000000000000000000000000000000000000000000000000000000000000004000000000000000000000000000000000000000000000000000000000000000800000000000000000000000000000000000000000000000000000000000000011687474703a2f2f676f6f676c652e636f6d0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000011687474703a2f2f676f6f676c652e636f6d000000000000000000000000000000",
  "creatorAddress": "0x5b4433697925a9620183759f65b3f7bdd5c05548",
  "timestamp": "2023-12-07T06:36:57.715Z",
  "txHash": "0xa383e24639adb5b81e2c57a0b616edfc876f0a70016f448024dafdf34bdc493c"
}
```

</details>

#### <mark style="background-color:green;">POST</mark> [/api/1.0/contracts/verify](https://test.xfiscan.com/api/1.0/swagger#/contracts/ContractController_verify)

The request responsible for verifying the contract.

After successful verification of the contract, the Application Binary Interface (ABI) is stored in the database, which allows you to define the methods of the contract.

#### Request body

```
{
  "contractAddress": "string",
  "sourceFiles": [
    {
      "name": "string",
      "value": "string"
    }
  ],
  "evmVersion": "default",
  "compilerVersion": "string",
  "optimizationRuns": 0
}
```

### tokens - List of tokens

<mark style="background-color:blue;">GET</mark>[ ](https://test.xfiscan.com/api/1.0/swagger#/tokens-erc20/TokenERC20Controller_find)[/api/1.0/tokens](https://test.xfiscan.com/api/1.0/swagger#/tokens/TokenController_find)

Getting a list of tokens.

#### Parameters

| Parameter                                     | Type                                  | Description                                                                                                                                                                                                     |
| --------------------------------------------- | ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>tokenSymbol</p><p><br></p><p>tokenType</p> | <p>string</p><p><br></p><p>string</p> | <p>Token character<br><br></p><p>Search by token type.</p><p><br></p>                                                                                                                                           |
| contractAddress                               | string                                | Contract address                                                                                                                                                                                                |
| txHashCreate                                  | string                                | The hash of the token creation.                                                                                                                                                                                 |
| creatorAddress                                | string                                | The address of the creator of the token.                                                                                                                                                                        |
| page                                          | number                                | Page number.                                                                                                                                                                                                    |
| limit                                         | number                                | The number of entities to give away.                                                                                                                                                                            |
| sort                                          | string                                | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field</p><p>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response</summary>

```json
{
  "docs": [
    {
      "contractAddress": "0x10d1a6c0c2f4f1ab1924f7271b2cc95e94e8a223",
      "blockNumberCreate": "866356",
      "creatorAddress": "0xa331f5c6b23c87d292da8b2118ebcc6a39633bb2",
      "timestamp": "2023-10-05T14:17:14.281Z",
      "tokenType": "CFC-20",
      "txHashCreate": "0x66cc14d6fc72561965e5f4a8088f17ae044fa4f0dc5a0eddfb3d1637022f6724",
      "transferCount": 12,
      "holderCount": 2
    },
    {
      "contractAddress": "0xb88a04d3eb73239377897607369a3af5e3f21ed3",
      "blockNumberCreate": "866337",
      "creatorAddress": "0xa331f5c6b23c87d292da8b2118ebcc6a39633bb2",
      "timestamp": "2023-10-05T14:15:27.559Z",
      "tokenType": "CFC-20",
      "txHashCreate": "0x39a35b84ee7013edfdd1b03e5004e11302d08dfd01da366694529816a33e92ee",
      "transferCount": 3,
      "holderCount": 2
    },
    {
      "contractAddress": "0x028d08e7591433460539ae5a1410e85d8f329e4b",
      "blockNumberCreate": "866326",
      "creatorAddress": "0xa331f5c6b23c87d292da8b2118ebcc6a39633bb2",
      "timestamp": "2023-10-05T14:14:25.804Z",
      "tokenType": "CFC-20",
      "txHashCreate": "0xbf5b7708498520914ec7d14eadf5366310689370aa11b9b7f2e2432f35bd67fb",
      "holderCount": 2,
      "transferCount": 2
    },
    {
      "contractAddress": "0x423ecc6395de26b82e1474818302377e40e09160",
      "blockNumberCreate": "8123386",
      "creatorAddress": "0xa08a49880ce57880c4530182c8451a542a8db096",
      "decimals": 18,
      "name": "FromNode",
      "timestamp": "2025-01-24T12:32:56.411Z",
      "tokenSymbol": "FN",
      "totalSupply": "0",
      "txHashCreate": "0x30f0896d6c1d38f80db8fa448016c6b688b6e6399cf94296d31645692ee32290"
    },
    {
      "contractAddress": "0x1b7dda99828e99c2ad934fc3942ad46e9addab60",
      "blockNumberCreate": "8123124",
      "creatorAddress": "0xa08a49880ce57880c4530182c8451a542a8db096",
      "decimals": 18,
      "name": "FromNode",
      "timestamp": "2025-01-24T12:10:31.911Z",
      "tokenSymbol": "FN",
      "totalSupply": "0",
      "txHashCreate": "0xc698f1c31285f993b5b5b62fe4c8e09b347756d914807188dcc2c18660d6d48c"
    },
    {
      "contractAddress": "0xcbe80a1c6073bae23a2ad4568fd62a533b1d4cbd",
      "blockNumberCreate": "8122908",
      "creatorAddress": "0xa08a49880ce57880c4530182c8451a542a8db096",
      "decimals": 18,
      "name": "FromNode",
      "timestamp": "2025-01-24T11:52:02.911Z",
      "tokenSymbol": "FN",
      "totalSupply": "0",
      "txHashCreate": "0xa8d3ed1702487e1ae0252ba4f371f0a316f6a043ef47f901f58eba10ff42a9ae"
    },
    {
      "contractAddress": "0xae91a6382b72f52466f69cf7274b2b78d5a7bbbc",
      "blockNumberCreate": "8122773",
      "creatorAddress": "0x79f9860d48ef9ddfaf3571281c033664de05e6f5",
      "decimals": 18,
      "name": "SmallQa",
      "timestamp": "2025-01-24T11:40:28.902Z",
      "tokenSymbol": "SQA",
      "totalSupply": "1000009000000000000000000",
      "txHashCreate": "0x76809ff850f4f3726cd0935b1c3c39ebfd4405f08478275fffcaaee415fb1870",
      "tokenType": "CFC-20",
      "holderCount": 2,
      "transferCount": 2
    },
    {
      "contractAddress": "0xa682d659e2eedcb5569b0152dab7d5dd863e67e9",
      "blockNumberCreate": "8122445",
      "creatorAddress": "0x79f9860d48ef9ddfaf3571281c033664de05e6f5",
      "decimals": 18,
      "name": "SmallQa",
      "timestamp": "2025-01-24T11:12:29.410Z",
      "tokenSymbol": "SQA",
      "totalSupply": "1000009000000000000000000",
      "txHashCreate": "0xa62899a7cd6827ef6e5f94d1c418f3c2a3311cb3e9856190265b6ba6ea48045b",
      "tokenType": "CFC-20",
      "holderCount": 1,
      "transferCount": 1
    },
    {
      "contractAddress": "0xa3f1b72f6a6ee1685d653c27b1a62e4d5f914bc1",
      "blockNumberCreate": "8121935",
      "creatorAddress": "0xa08a49880ce57880c4530182c8451a542a8db096",
      "decimals": 18,
      "name": "FromNode",
      "timestamp": "2025-01-24T10:28:57.371Z",
      "tokenSymbol": "FN",
      "totalSupply": "0",
      "txHashCreate": "0x886017f062aade26696ab524a6b7fd880de74beddfc49b2059251482ef03f340"
    },
    {
      "contractAddress": "0x11ddd993c606ff8d851fa6dcce0098d5c8a41260",
      "blockNumberCreate": "8121409",
      "creatorAddress": "0xa08a49880ce57880c4530182c8451a542a8db096",
      "decimals": 18,
      "name": "FromNode",
      "timestamp": "2025-01-24T09:43:56.976Z",
      "tokenSymbol": "FN",
      "totalSupply": "0",
      "txHashCreate": "0x5b91446a709d94cd837ee3e1395ac10bcece402241c9e7c7b2f05737d95e16d9"
    }
  ],
  "hasNext": true,
  "limit": 10,
  "page": 1
}
```

</details>



<mark style="background-color:blue;">GET</mark>[ ](https://dev.xfiscan.com/api/1.0/swagger#/tokens-erc20/TokenERC20Controller_findOne)[/api/1.0/tokens/{address}](https://test.xfiscan.com/api/1.0/swagger#/tokens/TokenController_findOne)

Receiving a token.

#### Parameters

| Parameter | Type   | Description                                  |
| --------- | ------ | -------------------------------------------- |
| address   | string | <p>Token address.</p><p>Mandatory field.</p> |

<details>

<summary>Sample Response</summary>



</details>

### tokens-transfers

<mark style="background-color:blue;">GET</mark> [/api/1.0/token-transfers](https://test.xfiscan.com/api/1.0/swagger#/token-erc20-transfers/TokenERC20TransferController_find)

Query for tokenized transfers.

**Parameters**

| Parameter                      | Type           | Description                                                                                                                                                                                                  |
| ------------------------------ | -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>contractAddress</p><p> </p> | string         | Contract address.                                                                                                                                                                                            |
| <p>blockNumber</p><p> </p>     | string         | Block number.                                                                                                                                                                                                |
| address                        | string         | Account address.                                                                                                                                                                                             |
| addressTo                      | string         | Address to.                                                                                                                                                                                                  |
| addressFrom                    | string         | Address from.                                                                                                                                                                                                |
| tokenSymbol                    | string         | Token character.                                                                                                                                                                                             |
| tokenName                      | string         | Name of the token.                                                                                                                                                                                           |
| txHash                         | string         | Contract hash.                                                                                                                                                                                               |
| tokenId                        | string         | Token ID.                                                                                                                                                                                                    |
| tokenIds                       | array\[string] | Token ID list.                                                                                                                                                                                               |
| tokenType                      | string         | Search by token type.                                                                                                                                                                                        |
| page                           | number         | Page number.                                                                                                                                                                                                 |
| limit                          | number         | The number of entities to give away.                                                                                                                                                                         |
| sort                           | string         | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field<br>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response</summary>

```json
{
  "docs": [
    {
      "uniqueHash": "eab16566509c8e2d815a2f2f05e33a67a5da4204879d25cf859f056d5c3c32c9",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8290098,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-02-03T10:16:49.020Z",
      "tokenId": "86259672042933921108750533828034886098428647589353731446404076201671430837847",
      "tokenType": "CFC-721",
      "txHash": "0x21b5d3e799b4a2733071c31100e9f93557b7d5062854330457b5d7bb28d154c4",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "5c31555d4076e561daf9dbdbda5928e7f714c82bf5e8d075bbf8addf7e18f854",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8289285,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-02-03T09:07:19.558Z",
      "tokenId": "107948749889035633804101137653889800474810990198484868044219599332006897436436",
      "tokenType": "CFC-721",
      "txHash": "0xb2792ed09f3e7694da4d27bfaa65e95efab49465c09cb08285068e07a71b8731",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "0b33f19a7b6f302062603fa8a51f2c7468293cf9e1e6b7ee1ad425a26f799689",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8289229,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-02-03T09:02:30.386Z",
      "tokenId": "67389414631714337960914266559079967364879151081230528149006581127326232964795",
      "tokenType": "CFC-721",
      "txHash": "0xaa10c97e7e4924dd22e7688c72a5ce422a1ff084fd92094cc3fa72a6ee6fb826",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "f0d172819d6dedb7012eed2f51677785daa74453ef999ca42e876561a1b113df",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8289106,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-02-03T08:51:58.881Z",
      "tokenId": "10342004145284402555203276061056567166692663915491028051427057374002188629695",
      "tokenType": "CFC-721",
      "txHash": "0xee9b756d49b563cb912f2d71bd13c6921920b5516717ffd3c4c8a7296bd99592",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "26667bd4fb9da5f79b973aebde7ed927b7c95c5089f728726c203dd17b9a2f62",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8289044,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-02-03T08:46:40.347Z",
      "tokenId": "65620315796280350674090121011808359222324936623213947213741429252606863469299",
      "tokenType": "CFC-721",
      "txHash": "0xb2ce1e553306a22fe5592a5cd1fe4ca1916777b794b214896af64271d820f740",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "22224cda01f57c200b03163a85324f2f6a10066f37add54491daa4461d6668cb",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8239654,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-01-31T10:20:11.544Z",
      "tokenId": "25545973485761316460330510359994482907632646233309271214536774824048483265015",
      "tokenType": "CFC-721",
      "txHash": "0x53c20a9350217f1d6b3089121d451ab996a1595333ab701afe21e30bc5749275",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "b90c9725e41f173b22f98d45192ca1fed702dbfc29234e942c855f91b0c0a40f",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8239526,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-01-31T10:09:15.564Z",
      "tokenId": "56403825734850848835751208234899110992947072782206033317882969848619018130270",
      "tokenType": "CFC-721",
      "txHash": "0x578c54100d325db3b614c5ab494b0cc793f9346164e3054c554e03316bccc69e",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "68b1e2ec9db38f8fb77428b6bfe9a5e0b7fa0efa3da7a0fb3e8adbe50876e324",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8239492,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-01-31T10:06:21.436Z",
      "tokenId": "44518249326998271361926681932926418564711054199744588070048541592954066219058",
      "tokenType": "CFC-721",
      "txHash": "0xf87fd59b6e797c05205f793a5e868669485c84f1e374050c7f38c15ed11b9055",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "50993aa2986e83db7f8947f668d671c54193d790fa0274e534db12e0001fd188",
      "addressFrom": "0x0000000000000000000000000000000000000000",
      "addressTo": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "blockNumber": 8208765,
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "quant": 0,
      "timestamp": "2025-01-29T14:17:26.110Z",
      "tokenId": "23812235854850737159471834548686096795766308791790053552344050144343199832628",
      "tokenType": "CFC-721",
      "txHash": "0xfe3bbe6a248ac2493ce12ee78f1afc52d8210f70162decd133a82bbfb07664fa",
      "xds": [
        null,
        null
      ]
    },
    {
      "uniqueHash": "28a25238566331f6cbafb9d5fffd7b193fe8da763f8ce266a830069ae3eca856",
      "addressFrom": "0x8f8b611b981287fde6279906947e19da90776a9e",
      "addressTo": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "blockNumber": 8208650,
      "contractAddress": "0x53d7027dac339c04d10ac61928747185398c3774",
      "decimals": null,
      "quant": 0,
      "timestamp": "2025-01-29T14:07:37.926Z",
      "tokenId": "0",
      "tokenName": "Hello",
      "tokenSymbol": "HHH",
      "tokenType": "CFC-721",
      "txHash": "0xcb603c7c2b97b1822dbd0bbbb0a1b5fb84eb7fa1dee53c3d2204f7fbf2dae59a",
      "xds": [
        {
          "name": "juuu",
          "address": "0x8f8b611b981287fde6279906947e19da90776a9e",
          "expires": "2025-01-31T11:09:15.000Z"
        },
        {
          "name": "1234",
          "address": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
          "expires": "2025-01-31T11:20:11.000Z"
        }
      ]
    }
  ],
  "hasNext": true,
  "limit": 10,
  "page": 1
}
```

</details>

### tokens-holders

<mark style="background-color:blue;">GET</mark> [/api/1.0/token-holders](https://test.xfiscan.com/api/1.0/swagger#/token-erc20-holders/TokenERC20HolderController_find)

Getting a list of token holders.

| Parameter                      | Type   | Description                                                                                                                                                                                                  |
| ------------------------------ | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| <p>tokenSymbol</p><p> </p>     | string | Token character                                                                                                                                                                                              |
| <p>address</p><p> </p>         | string | Account address.                                                                                                                                                                                             |
| <p>contractAddress</p><p> </p> | string | Contract address.                                                                                                                                                                                            |
| blockNumber                    | string | Block number.                                                                                                                                                                                                |
| tokenType                      | string | Search by token type.                                                                                                                                                                                        |
| page                           | number | Page number.                                                                                                                                                                                                 |
| limit                          | number | The number of entities to give away.                                                                                                                                                                         |
| sort                           | string | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field<br>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response</summary>

```json
{
  "docs": [
    {
      "address": "0x7d41861263af5d96f945b21bc74d90f660976722",
      "balance": "1000000000000000000000000000000000",
      "blockNumber": 3781571,
      "contractAddress": "0xf7c564761605772ba4dd552ad02244eaa06b9455",
      "timestamp": "2024-04-19T08:54:35.326Z",
      "tokenIds": [],
      "tokenName": "azx",
      "tokenType": "CFC-20"
    },
    {
      "address": "0x79f9860d48ef9ddfaf3571281c033664de05e6f5",
      "balance": "48575776978294620504878481408",
      "blockNumber": 2597692,
      "contractAddress": "0x9704ba5199274040203beb7e8b3d457afc38f9c5",
      "timestamp": "2024-01-29T13:12:21.198Z",
      "tokenIds": [],
      "tokenName": "Myqatoken",
      "tokenType": "CFC-20"
    },
    {
      "address": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "balance": "10000000000000000000000000000",
      "blockNumber": 4513524,
      "contractAddress": "0xa1ca14bf04fd59152a25082f13002a4bfa3d53d8",
      "timestamp": "2024-06-11T10:07:49.524Z",
      "tokenIds": [],
      "tokenName": "TiKK",
      "tokenType": "CFC-20"
    },
    {
      "address": "0xd7f10371eb160d00e0307bd4b15a335d6ac70dd4",
      "balance": "10000000000000000000000000000",
      "blockNumber": 3839822,
      "contractAddress": "0x987daf80b8330a5fd32b686989dd492bf1981a3f",
      "timestamp": "2024-04-23T06:57:31.757Z",
      "tokenIds": [],
      "tokenName": "KitToken",
      "tokenType": "CFC-20"
    },
    {
      "address": "0x7d41861263af5d96f945b21bc74d90f660976722",
      "balance": "1000000000000000000000000000",
      "blockNumber": 3769252,
      "contractAddress": "0x8f37f86f13c251ff55b79ff94ec2307fb214c9fe",
      "timestamp": "2024-04-18T13:10:45.373Z",
      "tokenIds": [],
      "tokenName": "GIGA",
      "tokenType": "CFC-20"
    },
    {
      "address": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "balance": "777777777000000000000000000",
      "blockNumber": 3769378,
      "contractAddress": "0x67703cdb390b1af7dadfd43bc743b1496ef1640d",
      "timestamp": "2024-04-18T13:22:47.352Z",
      "tokenIds": [],
      "tokenName": "Tik",
      "tokenType": "CFC-20"
    },
    {
      "address": "0xcdbfae998872190feac0856f74c9c17a0a2e3d0c",
      "balance": "666666666000000000000000000",
      "blockNumber": 5891763,
      "contractAddress": "0xfa5730e0c314edababc82cd65ade56e3de6f0418",
      "timestamp": "2024-09-11T10:49:34.734Z",
      "tokenIds": [],
      "tokenName": "Ptk",
      "tokenType": "CFC-20"
    },
    {
      "address": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "balance": "577777777876543210987654322",
      "blockNumber": 7825588,
      "contractAddress": "0x1e2532f23bdb3d132ac9919fff49cc8ea55fb39b",
      "timestamp": "2025-01-06T14:26:28.949Z",
      "tokenIds": [],
      "tokenName": "Tik",
      "tokenType": "CFC-20"
    },
    {
      "address": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "balance": "555555555000000000000000000",
      "blockNumber": 7825519,
      "contractAddress": "0x783d0e67319ecfbc8289f1fc3bd67662717ccc61",
      "timestamp": "2025-01-06T14:20:34.417Z",
      "tokenIds": [],
      "tokenName": "KKK",
      "tokenType": "CFC-20"
    },
    {
      "address": "0xb3562f025b5abe7b6e7c66ce36326afeba463a57",
      "balance": "499979000000000000000000000",
      "blockNumber": 7030758,
      "contractAddress": "0x6c1cca3ffa719a1a85db551e69c766c0d5ad85cd",
      "timestamp": "2024-11-20T06:16:00.506Z",
      "tokenIds": [],
      "tokenType": "CFC-20"
    }
  ],
  "hasNext": true,
  "limit": 10,
  "page": 1
}
```

</details>

### Token-inventory -  ERC-721 token inventory&#x20;

<mark style="background-color:blue;">GET</mark>[/api/1.0/token-inventory](https://test.xfiscan.com/api/1.0/swagger#/token-inventory/TokenInventoryController_find)

Asset management and display information about available tokens in the blockchain system.

| Parameter                      | Type   | Description                                                                                                                                                                                                     |
| ------------------------------ | ------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <p>contractAddress</p><p> </p> | string | <p>Smart Contract Address.</p><p><br></p>                                                                                                                                                                       |
| creatorAddress                 | string | The address of the contract creator.                                                                                                                                                                            |
| ownerAddress                   | string | The string representing the CFC-721 token owner аddress to check for inventory.                                                                                                                                 |
| tokenIds                       | string | Token ID list.                                                                                                                                                                                                  |
| <p>tokenType</p><p> </p>       | string | <p>Search by token type.<br>Available values: CFC-20, CFC-721</p><p><br><br></p>                                                                                                                                |
| page                           | number | Page Number.                                                                                                                                                                                                    |
| limit                          | number | The number of entities to be given away.                                                                                                                                                                        |
| sort                           | string | <p>The sort field takes in values with or without the prefix "-" (minus) which indicates the decreasing or increasing of the specified field</p><p>Example: '-height' is descending, 'height' is ascending.</p> |

<details>

<summary>Sample Response</summary>

```json
{
  "docs": [
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "86259672042933921108750533828034886098428647589353731446404076201671430837847",
      "blockNumber": 8290098,
      "creatorAddress": "0xdbadcd5c0be764255e43467e77693f6d6c98dc50",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-02-03T10:16:49.020Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "107948749889035633804101137653889800474810990198484868044219599332006897436436",
      "blockNumber": 8289285,
      "creatorAddress": "0x2d51ee7add91c7fa2de2f11a4c6bc9052837e196",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-02-03T09:07:19.558Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "67389414631714337960914266559079967364879151081230528149006581127326232964795",
      "blockNumber": 8289229,
      "creatorAddress": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-02-03T09:02:30.386Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "10342004145284402555203276061056567166692663915491028051427057374002188629695",
      "blockNumber": 8289106,
      "creatorAddress": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-02-03T08:51:58.881Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "65620315796280350674090121011808359222324936623213947213741429252606863469299",
      "blockNumber": 8289044,
      "creatorAddress": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-02-03T08:46:40.347Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "25545973485761316460330510359994482907632646233309271214536774824048483265015",
      "blockNumber": 8239654,
      "creatorAddress": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-01-31T10:20:11.544Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "56403825734850848835751208234899110992947072782206033317882969848619018130270",
      "blockNumber": 8239526,
      "creatorAddress": "0x8f8b611b981287fde6279906947e19da90776a9e",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-01-31T10:09:15.564Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "44518249326998271361926681932926418564711054199744588070048541592954066219058",
      "blockNumber": 8239492,
      "creatorAddress": "0x8f8b611b981287fde6279906947e19da90776a9e",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-01-31T10:06:21.436Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x6751151329750939638b7953a2af44bdf5cca669",
      "tokenId": "23812235854850737159471834548686096795766308791790053552344050144343199832628",
      "blockNumber": 8208765,
      "creatorAddress": "0x8f8b611b981287fde6279906947e19da90776a9e",
      "ownerAddress": "0xf8faa02321790c3a001a77c81c3c7ccc04383c2e",
      "timestamp": "2025-01-29T14:17:26.110Z",
      "tokenType": "CFC-721",
      "tokenURI": "",
      "transferCount": 1
    },
    {
      "contractAddress": "0x53d7027dac339c04d10ac61928747185398c3774",
      "tokenId": "0",
      "blockNumber": 8208650,
      "creatorAddress": "0x8f8b611b981287fde6279906947e19da90776a9e",
      "ownerAddress": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
      "timestamp": "2025-01-29T14:07:37.926Z",
      "tokenName": "Hello",
      "tokenSymbol": "HHH",
      "tokenType": "CFC-721",
      "tokenURI": "ipfs://QmQcyawP7u62ZthkmtDFPSw2rRqd4pxkttY21CgtC9q8mZ",
      "transferCount": 2,
      "metadata": {
        "image": "https://ipfs.io/ipfs/QmUKs7T3KgHhUjRUx5mJbRTyJtjFAp2wB99bkQFyyry8bL",
        "description": "8888 Cute Chubby Pudgy Penquins sliding around on the freezing ETH blockchain.",
        "name": "Hello",
        "attributes": [
          {
            "trait_type": "Skin",
            "value": "Mint"
          },
          {
            "trait_type": "Body",
            "value": "Hoodie Pink"
          },
          {
            "trait_type": "Face",
            "value": "Winking"
          }
        ]
      },
      "xds": {
        "name": "1234",
        "address": "0xe32a8124a37d9defae9049edaa4799c8fa550b0a",
        "expires": "2025-01-31T11:20:11.000Z"
      }
    }
  ],
  "hasNext": true,
  "limit": 10,
  "page": 1
}
```

</details>

<mark style="background-color:blue;">GET</mark> [/api/1.0/token-inventory/{contractAddress}/{tokenId}](https://test.xfiscan.com/api/1.0/swagger#/token-inventory/TokenInventoryController_findOne)

Inventory availability checks at a specific address.&#x20;

**Parameters**

| Parameter                      | Type   | Description                               |
| ------------------------------ | ------ | ----------------------------------------- |
| <p>contractAddress</p><p> </p> | string | <p>Smart Contract Address.</p><p><br></p> |
| tokenId                        | string | Token ID.                                 |

<details>

<summary>Sample Response</summary>

```json
{
  "contractAddress": "0x15cdf7c319f644f2fb5de746e5793c6a58172d3a",
  "tokenId": "0",
  "blockNumber": 5838817,
  "creatorAddress": "0xcdbfae998872190feac0856f74c9c17a0a2e3d0c",
  "ownerAddress": "0x80c8644281aacd624b512523da7a8ec755e289a1",
  "timestamp": "2024-10-31T14:44:36.929Z",
  "tokenName": "Polina",
  "tokenType": "CFC-721",
  "tokenURI": "ipfs://QmdWWfkHw7VJuConCe3zgSantRRuzksGsBwr3BSe1KCv2o",
  "transferCount": 2,
  "metadata": {
    "image": "https://ipfs.io/ipfs/QmWp4rTub5FMypSRC5nM3yFHRYAbB4pmTAc1akShMCM7qP",
    "description": "Cat Kaif",
    "name": "Kaif",
    "attributes": [
      {
        "trait_type": "face",
        "value": "smile"
      },
      {
        "trait_type": "house",
        "value": "difference"
      }
    ]
  },
  "xds": {
    "name": "poli1",
    "address": "0x80c8644281aacd624b512523da7a8ec755e289a1",
    "expires": "2024-12-03T14:39:50.000Z"
  }
}
```

</details>

### search

<mark style="background-color:blue;">GET</mark> [/api/1.0/search](https://test.xfiscan.com/api/1.0/swagger#/search/SearchController_search)

Searching an address, block, transaction, or token based on a passed value.

| Parameter | Type   | Description                                            |
| --------- | ------ | ------------------------------------------------------ |
| value     | string | Address, block, transaction or token. Mandatory field. |

<details>

<summary>Sample Response</summary>

```json
{
  "contractAddress": "0x15cdf7c319f644f2fb5de746e5793c6a58172d3a",
  "tokenId": "0",
  "blockNumber": 5838817,
  "creatorAddress": "0xcdbfae998872190feac0856f74c9c17a0a2e3d0c",
  "ownerAddress": "0x80c8644281aacd624b512523da7a8ec755e289a1",
  "timestamp": "2024-10-31T14:44:36.929Z",
  "tokenName": "Polina",
  "tokenType": "CFC-721",
  "tokenURI": "ipfs://QmdWWfkHw7VJuConCe3zgSantRRuzksGsBwr3BSe1KCv2o",
  "transferCount": 2,
  "metadata": {
    "image": "https://ipfs.io/ipfs/QmWp4rTub5FMypSRC5nM3yFHRYAbB4pmTAc1akShMCM7qP",
    "description": "Cat Kaif",
    "name": "Kaif",
    "attributes": [
      {
        "trait_type": "face",
        "value": "smile"
      },
      {
        "trait_type": "house",
        "value": "difference"
      }
    ]
  },
  "xds": {
    "name": "poli1",
    "address": "0x80c8644281aacd624b512523da7a8ec755e289a1",
    "expires": "2024-12-03T14:39:50.000Z"
  }
}
```

</details>

### stream

<mark style="background-color:purple;">OPTIONS</mark> [/api/1.0/stream/new-block](https://test.xfiscan.com/api/1.0/swagger#/stream/StreamController_newBlock)\
\
Getting a data stream of new block data.\
\
<mark style="background-color:purple;">OPTIONS</mark> [/api/1.0/stream/new-tx](https://test.xfiscan.com/api/1.0/swagger#/stream/StreamController_newTxs)

Getting a data stream of new transactions.

Per socketio protocol.

**Example for js:**

```bash
const socket = io(`https://test.xfiscan.com/stream`, {path: '/api/1.0/stream'})
 
    socket.on('connect', () => {
      console.log('connect');
    })
    socket.on('disconnect', (data) => console.log(data));
    socket.on('new-block', (data) => console.log(data));
    socket.on('new-txs, (data) => console.log(data));
```

**Where:**

|                    |                                                                    |
| ------------------ | ------------------------------------------------------------------ |
| **url connection** | [https://test.xfiscan.com/stream](https://test.xfiscan.com/stream) |
| **handshake path** | /api/1.0/stream                                                    |
| **new-block**      | subscribe to receive new blocks                                    |
| **new-tx**         | subscribe to receive new transactions                              |

### Get Contract ABI for Verified Contract Source Codes

Returns the Contract Application Binary Interface ( ABI ) of a verified smart contract.

<mark style="background-color:blue;">**GET**</mark>  [**`/api/1.0/verify-contract`**](https://xfiscan.com/api/1.0/swagger#/verify-contract/VerifyContractController_get)

#### Request

```ruby
https://xfiscan.com/api/1.0/verify-contract
   ?chainid=1
   &module=contract
   &action=getabi
   &address=0xBB9bc244D798123fDe783fCc1C72d3Bb8C189413
   &apikey=YourApiKeyToken
```

**Parameters**

| Parameter | Type     | Description                                            |
| --------- | -------- | ------------------------------------------------------ |
| `address` | `string` | the `contract address` that has a verified source code |

<details>

<summary>Sample Response</summary>

```json
{
   "status":"1",
   "message":"OK",
   "result":"[{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"name\":\"proposals\",\"outputs\":[{\"name\":\"recipient\",\"type\":\"address\"},{\"name\":\"amount\",\"type\":\"uint256\"},{\"name\":\"description\",\"type\":\"string\"},{\"name\":\"votingDeadline\",\"type\":\"uint256\"},{\"name\":\"open\",\"type\":\"bool\"},{\"name\":\"proposalPassed\",\"type\":\"bool\"},{\"name\":\"proposalHash\",\"type\":\"bytes32\"},{\"name\":\"proposalDeposit\",\"type\":\"uint256\"},{\"name\":\"newCurator\",\"type\":\"bool\"},{\"name\":\"yea\",\"type\":\"uint256\"},{\"name\":\"nay\",\"type\":\"uint256\"},{\"name\":\"creator\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_spender\",\"type\":\"address\"},{\"name\":\"_amount\",\"type\":\"uint256\"}],\"name\":\"approve\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"minTokensToCreate\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"rewardAccount\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"daoCreator\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"totalSupply\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"divisor\",\"outputs\":[{\"name\":\"divisor\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"extraBalance\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_transactionData\",\"type\":\"bytes\"}],\"name\":\"executeProposal\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_from\",\"type\":\"address\"},{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transferFrom\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"unblockMe\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"totalRewardToken\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"actualBalance\",\"outputs\":[{\"name\":\"_actualBalance\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"closingTime\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"allowedRecipients\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transferWithoutReward\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"refund\",\"outputs\":[],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_recipient\",\"type\":\"address\"},{\"name\":\"_amount\",\"type\":\"uint256\"},{\"name\":\"_description\",\"type\":\"string\"},{\"name\":\"_transactionData\",\"type\":\"bytes\"},{\"name\":\"_debatingPeriod\",\"type\":\"uint256\"},{\"name\":\"_newCurator\",\"type\":\"bool\"}],\"name\":\"newProposal\",\"outputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"DAOpaidOut\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"minQuorumDivisor\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_newContract\",\"type\":\"address\"}],\"name\":\"newContract\",\"outputs\":[],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_owner\",\"type\":\"address\"}],\"name\":\"balanceOf\",\"outputs\":[{\"name\":\"balance\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_recipient\",\"type\":\"address\"},{\"name\":\"_allowed\",\"type\":\"bool\"}],\"name\":\"changeAllowedRecipients\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"halveMinQuorum\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"paidOut\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_newCurator\",\"type\":\"address\"}],\"name\":\"splitDAO\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"DAOrewardAccount\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"proposalDeposit\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"numberOfProposals\",\"outputs\":[{\"name\":\"_numberOfProposals\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"lastTimeMinQuorumMet\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_toMembers\",\"type\":\"bool\"}],\"name\":\"retrieveDAOReward\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"receiveEther\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transfer\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"isFueled\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_tokenHolder\",\"type\":\"address\"}],\"name\":\"createTokenProxy\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"}],\"name\":\"getNewDAOAddress\",\"outputs\":[{\"name\":\"_newDAO\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_supportsProposal\",\"type\":\"bool\"}],\"name\":\"vote\",\"outputs\":[{\"name\":\"_voteID\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"getMyReward\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"rewardToken\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_from\",\"type\":\"address\"},{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transferFromWithoutReward\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_owner\",\"type\":\"address\"},{\"name\":\"_spender\",\"type\":\"address\"}],\"name\":\"allowance\",\"outputs\":[{\"name\":\"remaining\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalDeposit\",\"type\":\"uint256\"}],\"name\":\"changeProposalDeposit\",\"outputs\":[],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"blocked\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"curator\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_recipient\",\"type\":\"address\"},{\"name\":\"_amount\",\"type\":\"uint256\"},{\"name\":\"_transactionData\",\"type\":\"bytes\"}],\"name\":\"checkProposalCode\",\"outputs\":[{\"name\":\"_codeChecksOut\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"privateCreation\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"inputs\":[{\"name\":\"_curator\",\"type\":\"address\"},{\"name\":\"_daoCreator\",\"type\":\"address\"},{\"name\":\"_proposalDeposit\",\"type\":\"uint256\"},{\"name\":\"_minTokensToCreate\",\"type\":\"uint256\"},{\"name\":\"_closingTime\",\"type\":\"uint256\"},{\"name\":\"_privateCreation\",\"type\":\"address\"}],\"type\":\"constructor\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_from\",\"type\":\"address\"},{\"indexed\":true,\"name\":\"_to\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"_amount\",\"type\":\"uint256\"}],\"name\":\"Transfer\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_owner\",\"type\":\"address\"},{\"indexed\":true,\"name\":\"_spender\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"_amount\",\"type\":\"uint256\"}],\"name\":\"Approval\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":false,\"name\":\"value\",\"type\":\"uint256\"}],\"name\":\"FuelingToDate\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"to\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"amount\",\"type\":\"uint256\"}],\"name\":\"CreatedToken\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"to\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"value\",\"type\":\"uint256\"}],\"name\":\"Refund\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"proposalID\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"recipient\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"amount\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"newCurator\",\"type\":\"bool\"},{\"indexed\":false,\"name\":\"description\",\"type\":\"string\"}],\"name\":\"ProposalAdded\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"proposalID\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"position\",\"type\":\"bool\"},{\"indexed\":true,\"name\":\"voter\",\"type\":\"address\"}],\"name\":\"Voted\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"proposalID\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"result\",\"type\":\"bool\"},{\"indexed\":false,\"name\":\"quorum\",\"type\":\"uint256\"}],\"name\":\"ProposalTallied\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_newCurator\",\"type\":\"address\"}],\"name\":\"NewCurator\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_recipient\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"_allowed\",\"type\":\"bool\"}],\"name\":\"AllowedRecipientChanged\",\"type\":\"event\"}]"
}
```

</details>

### Get Contract Source Code for Verified Contract Source Codes

Returns the Solidity source code of a verified smart contract.

{% hint style="info" %}
You can also download a CSV list of verified contracts addresses of which the code publishers have provided a corresponding Open Source license for redistribution.
{% endhint %}

<mark style="background-color:blue;">**GET**</mark>  [**`api/1.0/verify-contract`**](https://xfiscan.com/api/1.0/swagger#/verify-contract/VerifyContractController_get)

#### Request

```ruby
https://xfiscan.com/api/1.0/verify-contract
   ?chainid=1
   &module=contract
   &action=getsourcecode
   &address=0xBB9bc244D798123fDe783fCc1C72d3Bb8C189413
   &apikey=YourApiKeyToken
```

#### Paramenets

| Parameter | Type     | Destcrition                                            |
| --------- | -------- | ------------------------------------------------------ |
| `address` | `string` | the `contract address` that has a verified source code |

<details>

<summary>Sample Response </summary>

```json
{
   "status":"1",
   "message":"OK",
   "result":[
      {
         "SourceCode":"/*\n\n- Bytecode Verification performed was compared on second iteration -\n\nThis file is part of the DAO.\n\nThe DAO is free software: you can redistribute it and/or modify\nit under the terms of the GNU lesser General Public License as published by\nthe Free Software Foundation, either version 3 of the License, or\n(at your option) any later version.\n\nThe DAO is distributed in the hope that it will be useful,\nbut WITHOUT ANY WARRANTY; without even the implied warranty of\nMERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the\nGNU lesser General Public License for more details.\n\nYou should have received a copy of the GNU lesser General Public License\nalong with the DAO.  If not, see <http://www.gnu.org/licenses/>.\n*/\n\n\n/*\nBasic, standardized Token contract with no \"premine\". Defines the functions to\ncheck token balances, send tokens, send tokens on behalf of a 3rd party and the\ncorresponding approval process. Tokens need to be created by a derived\ncontract (e.g. TokenCreation.sol).\n\nThank you ConsenSys, this contract originated from:\nhttps://github.com/ConsenSys/Tokens/blob/master/Token_Contracts/contracts/Standard_Token.sol\nWhich is itself based on the Ethereum standardized contract APIs:\nhttps://github.com/ethereum/wiki/wiki/Standardized_Contract_APIs\n*/\n\n/// @title Standard Token Contract.\n\ncontract TokenInterface {\n    mapping (address => uint256) balances;\n    mapping (address => mapping (address => uint256)) allowed;\n\n    /// Total amount of tokens\n    uint256 public totalSupply;\n\n    /// @param _owner The address from which the balance will be retrieved\n    /// @return The balance\n    function balanceOf(address _owner) constant returns (uint256 balance);\n\n    /// @notice Send `_amount` tokens to `_to` from `msg.sender`\n    /// @param _to The address of the recipient\n    /// @param _amount The amount of tokens to be transferred\n    /// @return Whether the transfer was successful or not\n    function transfer(address _to, uint256 _amount) returns (bool success);\n\n    /// @notice Send `_amount` tokens to `_to` from `_from` on the condition it\n    /// is approved by `_from`\n    /// @param _from The address of the origin of the transfer\n    /// @param _to The address of the recipient\n    /// @param _amount The amount of tokens to be transferred\n    /// @return Whether the transfer was successful or not\n    function transferFrom(address _from, address _to, uint256 _amount) returns (bool success);\n\n    /// @notice `msg.sender` approves `_spender` to spend `_amount` tokens on\n    /// its behalf\n    /// @param _spender The address of the account able to transfer the tokens\n    /// @param _amount The amount of tokens to be approved for transfer\n    /// @return Whether the approval was successful or not\n    function approve(address _spender, uint256 _amount) returns (bool success);\n\n    /// @param _owner The address of the account owning tokens\n    /// @param _spender The address of the account able to transfer the tokens\n    /// @return Amount of remaining tokens of _owner that _spender is allowed\n    /// to spend\n    function allowance(\n        address _owner,\n        address _spender\n    ) constant returns (uint256 remaining);\n\n    event Transfer(address indexed _from, address indexed _to, uint256 _amount);\n    event Approval(\n        address indexed _owner,\n        address indexed _spender,\n        uint256 _amount\n    );\n}\n\n\ncontract Token is TokenInterface {\n    // Protects users by preventing the execution of method calls that\n    // inadvertently also transferred ether\n    modifier noEther() {if (msg.value > 0) throw; _}\n\n    function balanceOf(address _owner) constant returns (uint256 balance) {\n        return balances[_owner];\n    }\n\n    function transfer(address _to, uint256 _amount) noEther returns (bool success) {\n        if (balances[msg.sender] >= _amount && _amount > 0) {\n            balances[msg.sender] -= _amount;\n            balances[_to] += _amount;\n            Transfer(msg.sender, _to, _amount);\n            return true;\n        } else {\n           return false;\n        }\n    }\n\n    function transferFrom(\n        address _from,\n        address _to,\n        uint256 _amount\n    ) noEther returns (bool success) {\n\n        if (balances[_from] >= _amount\n            && allowed[_from][msg.sender] >= _amount\n            && _amount > 0) {\n\n            balances[_to] += _amount;\n            balances[_from] -= _amount;\n            allowed[_from][msg.sender] -= _amount;\n            Transfer(_from, _to, _amount);\n            return true;\n        } else {\n            return false;\n        }\n    }\n\n    function approve(address _spender, uint256 _amount) returns (bool success) {\n        allowed[msg.sender][_spender] = _amount;\n        Approval(msg.sender, _spender, _amount);\n        return true;\n    }\n\n    function allowance(address _owner, address _spender) constant returns (uint256 remaining) {\n        return allowed[_owner][_spender];\n    }\n}\n\n\n/*\nThis file is part of the DAO.\n\nThe DAO is free software: you can redistribute it and/or modify\nit under the terms of the GNU lesser General Public License as published by\nthe Free Software Foundation, either version 3 of the License, or\n(at your option) any later version.\n\nThe DAO is distributed in the hope that it will be useful,\nbut WITHOUT ANY WARRANTY; without even the implied warranty of\nMERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the\nGNU lesser General Public License for more details.\n\nYou should have received a copy of the GNU lesser General Public License\nalong with the DAO.  If not, see <http://www.gnu.org/licenses/>.\n*/\n\n\n/*\nBasic account, used by the DAO contract to separately manage both the rewards \nand the extraBalance accounts. \n*/\n\ncontract ManagedAccountInterface {\n    // The only address with permission to withdraw from this account\n    address public owner;\n    // If true, only the owner of the account can receive ether from it\n    bool public payOwnerOnly;\n    // The sum of ether (in wei) which has been sent to this contract\n    uint public accumulatedInput;\n\n    /// @notice Sends `_amount` of wei to _recipient\n    /// @param _amount The amount of wei to send to `_recipient`\n    /// @param _recipient The address to receive `_amount` of wei\n    /// @return True if the send completed\n    function payOut(address _recipient, uint _amount) returns (bool);\n\n    event PayOut(address indexed _recipient, uint _amount);\n}\n\n\ncontract ManagedAccount is ManagedAccountInterface{\n\n    // The constructor sets the owner of the account\n    function ManagedAccount(address _owner, bool _payOwnerOnly) {\n        owner = _owner;\n        payOwnerOnly = _payOwnerOnly;\n    }\n\n    // When the contract receives a transaction without data this is called. \n    // It counts the amount of ether it receives and stores it in \n    // accumulatedInput.\n    function() {\n        accumulatedInput += msg.value;\n    }\n\n    function payOut(address _recipient, uint _amount) returns (bool) {\n        if (msg.sender != owner || msg.value > 0 || (payOwnerOnly && _recipient != owner))\n            throw;\n        if (_recipient.call.value(_amount)()) {\n            PayOut(_recipient, _amount);\n            return true;\n        } else {\n            return false;\n        }\n    }\n}\n/*\nThis file is part of the DAO.\n\nThe DAO is free software: you can redistribute it and/or modify\nit under the terms of the GNU lesser General Public License as published by\nthe Free Software Foundation, either version 3 of the License, or\n(at your option) any later version.\n\nThe DAO is distributed in the hope that it will be useful,\nbut WITHOUT ANY WARRANTY; without even the implied warranty of\nMERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the\nGNU lesser General Public License for more details.\n\nYou should have received a copy of the GNU lesser General Public License\nalong with the DAO.  If not, see <http://www.gnu.org/licenses/>.\n*/\n\n\n/*\n * Token Creation contract, used by the DAO to create its tokens and initialize\n * its ether. Feel free to modify the divisor method to implement different\n * Token Creation parameters\n*/\n\n\ncontract TokenCreationInterface {\n\n    // End of token creation, in Unix time\n    uint public closingTime;\n    // Minimum fueling goal of the token creation, denominated in tokens to\n    // be created\n    uint public minTokensToCreate;\n    // True if the DAO reached its minimum fueling goal, false otherwise\n    bool public isFueled;\n    // For DAO splits - if privateCreation is 0, then it is a public token\n    // creation, otherwise only the address stored in privateCreation is\n    // allowed to create tokens\n    address public privateCreation;\n    // hold extra ether which has been sent after the DAO token\n    // creation rate has increased\n    ManagedAccount public extraBalance;\n    // tracks the amount of wei given from each contributor (used for refund)\n    mapping (address => uint256) weiGiven;\n\n    /// @dev Constructor setting the minimum fueling goal and the\n    /// end of the Token Creation\n    /// @param _minTokensToCreate Minimum fueling goal in number of\n    ///        Tokens to be created\n    /// @param _closingTime Date (in Unix time) of the end of the Token Creation\n    /// @param _privateCreation Zero means that the creation is public.  A\n    /// non-zero address represents the only address that can create Tokens\n    /// (the address can also create Tokens on behalf of other accounts)\n    // This is the constructor: it can not be overloaded so it is commented out\n    //  function TokenCreation(\n        //  uint _minTokensTocreate,\n        //  uint _closingTime,\n        //  address _privateCreation\n    //  );\n\n    /// @notice Create Token with `_tokenHolder` as the initial owner of the Token\n    /// @param _tokenHolder The address of the Tokens's recipient\n    /// @return Whether the token creation was successful\n    function createTokenProxy(address _tokenHolder) returns (bool success);\n\n    /// @notice Refund `msg.sender` in the case the Token Creation did\n    /// not reach its minimum fueling goal\n    function refund();\n\n    /// @return The divisor used to calculate the token creation rate during\n    /// the creation phase\n    function divisor() constant returns (uint divisor);\n\n    event FuelingToDate(uint value);\n    event CreatedToken(address indexed to, uint amount);\n    event Refund(address indexed to, uint value);\n}\n\n\ncontract TokenCreation is TokenCreationInterface, Token {\n    function TokenCreation(\n        uint _minTokensToCreate,\n        uint _closingTime,\n        address _privateCreation) {\n\n        closingTime = _closingTime;\n        minTokensToCreate = _minTokensToCreate;\n        privateCreation = _privateCreation;\n        extraBalance = new ManagedAccount(address(this), true);\n    }\n\n    function createTokenProxy(address _tokenHolder) returns (bool success) {\n        if (now < closingTime && msg.value > 0\n            && (privateCreation == 0 || privateCreation == msg.sender)) {\n\n            uint token = (msg.value * 20) / divisor();\n            extraBalance.call.value(msg.value - token)();\n            balances[_tokenHolder] += token;\n            totalSupply += token;\n            weiGiven[_tokenHolder] += msg.value;\n            CreatedToken(_tokenHolder, token);\n            if (totalSupply >= minTokensToCreate && !isFueled) {\n                isFueled = true;\n                FuelingToDate(totalSupply);\n            }\n            return true;\n        }\n        throw;\n    }\n\n    function refund() noEther {\n        if (now > closingTime && !isFueled) {\n            // Get extraBalance - will only succeed when called for the first time\n            if (extraBalance.balance >= extraBalance.accumulatedInput())\n                extraBalance.payOut(address(this), extraBalance.accumulatedInput());\n\n            // Execute refund\n            if (msg.sender.call.value(weiGiven[msg.sender])()) {\n                Refund(msg.sender, weiGiven[msg.sender]);\n                totalSupply -= balances[msg.sender];\n                balances[msg.sender] = 0;\n                weiGiven[msg.sender] = 0;\n            }\n        }\n    }\n\n    function divisor() constant returns (uint divisor) {\n        // The number of (base unit) tokens per wei is calculated\n        // as `msg.value` * 20 / `divisor`\n        // The fueling period starts with a 1:1 ratio\n        if (closingTime - 2 weeks > now) {\n            return 20;\n        // Followed by 10 days with a daily creation rate increase of 5%\n        } else if (closingTime - 4 days > now) {\n            return (20 + (now - (closingTime - 2 weeks)) / (1 days));\n        // The last 4 days there is a constant creation rate ratio of 1:1.5\n        } else {\n            return 30;\n        }\n    }\n}\n/*\nThis file is part of the DAO.\n\nThe DAO is free software: you can redistribute it and/or modify\nit under the terms of the GNU lesser General Public License as published by\nthe Free Software Foundation, either version 3 of the License, or\n(at your option) any later version.\n\nThe DAO is distributed in the hope that it will be useful,\nbut WITHOUT ANY WARRANTY; without even the implied warranty of\nMERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the\nGNU lesser General Public License for more details.\n\nYou should have received a copy of the GNU lesser General Public License\nalong with the DAO.  If not, see <http://www.gnu.org/licenses/>.\n*/\n\n\n/*\nStandard smart contract for a Decentralized Autonomous Organization (DAO)\nto automate organizational governance and decision-making.\n*/\n\n\ncontract DAOInterface {\n\n    // The amount of days for which people who try to participate in the\n    // creation by calling the fallback function will still get their ether back\n    uint constant creationGracePeriod = 40 days;\n    // The minimum debate period that a generic proposal can have\n    uint constant minProposalDebatePeriod = 2 weeks;\n    // The minimum debate period that a split proposal can have\n    uint constant minSplitDebatePeriod = 1 weeks;\n    // Period of days inside which it's possible to execute a DAO split\n    uint constant splitExecutionPeriod = 27 days;\n    // Period of time after which the minimum Quorum is halved\n    uint constant quorumHalvingPeriod = 25 weeks;\n    // Period after which a proposal is closed\n    // (used in the case `executeProposal` fails because it throws)\n    uint constant executeProposalPeriod = 10 days;\n    // Denotes the maximum proposal deposit that can be given. It is given as\n    // a fraction of total Ether spent plus balance of the DAO\n    uint constant maxDepositDivisor = 100;\n\n    // Proposals to spend the DAO's ether or to choose a new Curator\n    Proposal[] public proposals;\n    // The quorum needed for each proposal is partially calculated by\n    // totalSupply / minQuorumDivisor\n    uint public minQuorumDivisor;\n    // The unix time of the last time quorum was reached on a proposal\n    uint  public lastTimeMinQuorumMet;\n\n    // Address of the curator\n    address public curator;\n    // The whitelist: List of addresses the DAO is allowed to send ether to\n    mapping (address => bool) public allowedRecipients;\n\n    // Tracks the addresses that own Reward Tokens. Those addresses can only be\n    // DAOs that have split from the original DAO. Conceptually, Reward Tokens\n    // represent the proportion of the rewards that the DAO has the right to\n    // receive. These Reward Tokens are generated when the DAO spends ether.\n    mapping (address => uint) public rewardToken;\n    // Total supply of rewardToken\n    uint public totalRewardToken;\n\n    // The account used to manage the rewards which are to be distributed to the\n    // DAO Token Holders of this DAO\n    ManagedAccount public rewardAccount;\n\n    // The account used to manage the rewards which are to be distributed to\n    // any DAO that holds Reward Tokens\n    ManagedAccount public DAOrewardAccount;\n\n    // Amount of rewards (in wei) already paid out to a certain DAO\n    mapping (address => uint) public DAOpaidOut;\n\n    // Amount of rewards (in wei) already paid out to a certain address\n    mapping (address => uint) public paidOut;\n    // Map of addresses blocked during a vote (not allowed to transfer DAO\n    // tokens). The address points to the proposal ID.\n    mapping (address => uint) public blocked;\n\n    // The minimum deposit (in wei) required to submit any proposal that is not\n    // requesting a new Curator (no deposit is required for splits)\n    uint public proposalDeposit;\n\n    // the accumulated sum of all current proposal deposits\n    uint sumOfProposalDeposits;\n\n    // Contract that is able to create a new DAO (with the same code as\n    // this one), used for splits\n    DAO_Creator public daoCreator;\n\n    // A proposal with `newCurator == false` represents a transaction\n    // to be issued by this DAO\n    // A proposal with `newCurator == true` represents a DAO split\n    struct Proposal {\n        // The address where the `amount` will go to if the proposal is accepted\n        // or if `newCurator` is true, the proposed Curator of\n        // the new DAO).\n        address recipient;\n        // The amount to transfer to `recipient` if the proposal is accepted.\n        uint amount;\n        // A plain text description of the proposal\n        string description;\n        // A unix timestamp, denoting the end of the voting period\n        uint votingDeadline;\n        // True if the proposal's votes have yet to be counted, otherwise False\n        bool open;\n        // True if quorum has been reached, the votes have been counted, and\n        // the majority said yes\n        bool proposalPassed;\n        // A hash to check validity of a proposal\n        bytes32 proposalHash;\n        // Deposit in wei the creator added when submitting their proposal. It\n        // is taken from the msg.value of a newProposal call.\n        uint proposalDeposit;\n        // True if this proposal is to assign a new Curator\n        bool newCurator;\n        // Data needed for splitting the DAO\n        SplitData[] splitData;\n        // Number of Tokens in favor of the proposal\n        uint yea;\n        // Number of Tokens opposed to the proposal\n        uint nay;\n        // Simple mapping to check if a shareholder has voted for it\n        mapping (address => bool) votedYes;\n        // Simple mapping to check if a shareholder has voted against it\n        mapping (address => bool) votedNo;\n        // Address of the shareholder who created the proposal\n        address creator;\n    }\n\n    // Used only in the case of a newCurator proposal.\n    struct SplitData {\n        // The balance of the current DAO minus the deposit at the time of split\n        uint splitBalance;\n        // The total amount of DAO Tokens in existence at the time of split.\n        uint totalSupply;\n        // Amount of Reward Tokens owned by the DAO at the time of split.\n        uint rewardToken;\n        // The new DAO contract created at the time of split.\n        DAO newDAO;\n    }\n\n    // Used to restrict access to certain functions to only DAO Token Holders\n    modifier onlyTokenholders {}\n\n    /// @dev Constructor setting the Curator and the address\n    /// for the contract able to create another DAO as well as the parameters\n    /// for the DAO Token Creation\n    /// @param _curator The Curator\n    /// @param _daoCreator The contract able to (re)create this DAO\n    /// @param _proposalDeposit The deposit to be paid for a regular proposal\n    /// @param _minTokensToCreate Minimum required wei-equivalent tokens\n    ///        to be created for a successful DAO Token Creation\n    /// @param _closingTime Date (in Unix time) of the end of the DAO Token Creation\n    /// @param _privateCreation If zero the DAO Token Creation is open to public, a\n    /// non-zero address means that the DAO Token Creation is only for the address\n    // This is the constructor: it can not be overloaded so it is commented out\n    //  function DAO(\n        //  address _curator,\n        //  DAO_Creator _daoCreator,\n        //  uint _proposalDeposit,\n        //  uint _minTokensToCreate,\n        //  uint _closingTime,\n        //  address _privateCreation\n    //  );\n\n    /// @notice Create Token with `msg.sender` as the beneficiary\n    /// @return Whether the token creation was successful\n    function () returns (bool success);\n\n\n    /// @dev This function is used to send ether back\n    /// to the DAO, it can also be used to receive payments that should not be\n    /// counted as rewards (donations, grants, etc.)\n    /// @return Whether the DAO received the ether successfully\n    function receiveEther() returns(bool);\n\n    /// @notice `msg.sender` creates a proposal to send `_amount` Wei to\n    /// `_recipient` with the transaction data `_transactionData`. If\n    /// `_newCurator` is true, then this is a proposal that splits the\n    /// DAO and sets `_recipient` as the new DAO's Curator.\n    /// @param _recipient Address of the recipient of the proposed transaction\n    /// @param _amount Amount of wei to be sent with the proposed transaction\n    /// @param _description String describing the proposal\n    /// @param _transactionData Data of the proposed transaction\n    /// @param _debatingPeriod Time used for debating a proposal, at least 2\n    /// weeks for a regular proposal, 10 days for new Curator proposal\n    /// @param _newCurator Bool defining whether this proposal is about\n    /// a new Curator or not\n    /// @return The proposal ID. Needed for voting on the proposal\n    function newProposal(\n        address _recipient,\n        uint _amount,\n        string _description,\n        bytes _transactionData,\n        uint _debatingPeriod,\n        bool _newCurator\n    ) onlyTokenholders returns (uint _proposalID);\n\n    /// @notice Check that the proposal with the ID `_proposalID` matches the\n    /// transaction which sends `_amount` with data `_transactionData`\n    /// to `_recipient`\n    /// @param _proposalID The proposal ID\n    /// @param _recipient The recipient of the proposed transaction\n    /// @param _amount The amount of wei to be sent in the proposed transaction\n    /// @param _transactionData The data of the proposed transaction\n    /// @return Whether the proposal ID matches the transaction data or not\n    function checkProposalCode(\n        uint _proposalID,\n        address _recipient,\n        uint _amount,\n        bytes _transactionData\n    ) constant returns (bool _codeChecksOut);\n\n    /// @notice Vote on proposal `_proposalID` with `_supportsProposal`\n    /// @param _proposalID The proposal ID\n    /// @param _supportsProposal Yes/No - support of the proposal\n    /// @return The vote ID.\n    function vote(\n        uint _proposalID,\n        bool _supportsProposal\n    ) onlyTokenholders returns (uint _voteID);\n\n    /// @notice Checks whether proposal `_proposalID` with transaction data\n    /// `_transactionData` has been voted for or rejected, and executes the\n    /// transaction in the case it has been voted for.\n    /// @param _proposalID The proposal ID\n    /// @param _transactionData The data of the proposed transaction\n    /// @return Whether the proposed transaction has been executed or not\n    function executeProposal(\n        uint _proposalID,\n        bytes _transactionData\n    ) returns (bool _success);\n\n    /// @notice ATTENTION! I confirm to move my remaining ether to a new DAO\n    /// with `_newCurator` as the new Curator, as has been\n    /// proposed in proposal `_proposalID`. This will burn my tokens. This can\n    /// not be undone and will split the DAO into two DAO's, with two\n    /// different underlying tokens.\n    /// @param _proposalID The proposal ID\n    /// @param _newCurator The new Curator of the new DAO\n    /// @dev This function, when called for the first time for this proposal,\n    /// will create a new DAO and send the sender's portion of the remaining\n    /// ether and Reward Tokens to the new DAO. It will also burn the DAO Tokens\n    /// of the sender.\n    function splitDAO(\n        uint _proposalID,\n        address _newCurator\n    ) returns (bool _success);\n\n    /// @dev can only be called by the DAO itself through a proposal\n    /// updates the contract of the DAO by sending all ether and rewardTokens\n    /// to the new DAO. The new DAO needs to be approved by the Curator\n    /// @param _newContract the address of the new contract\n    function newContract(address _newContract);\n\n\n    /// @notice Add a new possible recipient `_recipient` to the whitelist so\n    /// that the DAO can send transactions to them (using proposals)\n    /// @param _recipient New recipient address\n    /// @dev Can only be called by the current Curator\n    /// @return Whether successful or not\n    function changeAllowedRecipients(address _recipient, bool _allowed) external returns (bool _success);\n\n\n    /// @notice Change the minimum deposit required to submit a proposal\n    /// @param _proposalDeposit The new proposal deposit\n    /// @dev Can only be called by this DAO (through proposals with the\n    /// recipient being this DAO itself)\n    function changeProposalDeposit(uint _proposalDeposit) external;\n\n    /// @notice Move rewards from the DAORewards managed account\n    /// @param _toMembers If true rewards are moved to the actual reward account\n    ///                   for the DAO. If not then it's moved to the DAO itself\n    /// @return Whether the call was successful\n    function retrieveDAOReward(bool _toMembers) external returns (bool _success);\n\n    /// @notice Get my portion of the reward that was sent to `rewardAccount`\n    /// @return Whether the call was successful\n    function getMyReward() returns(bool _success);\n\n    /// @notice Withdraw `_account`'s portion of the reward from `rewardAccount`\n    /// to `_account`'s balance\n    /// @return Whether the call was successful\n    function withdrawRewardFor(address _account) internal returns (bool _success);\n\n    /// @notice Send `_amount` tokens to `_to` from `msg.sender`. Prior to this\n    /// getMyReward() is called.\n    /// @param _to The address of the recipient\n    /// @param _amount The amount of tokens to be transfered\n    /// @return Whether the transfer was successful or not\n    function transferWithoutReward(address _to, uint256 _amount) returns (bool success);\n\n    /// @notice Send `_amount` tokens to `_to` from `_from` on the condition it\n    /// is approved by `_from`. Prior to this getMyReward() is called.\n    /// @param _from The address of the sender\n    /// @param _to The address of the recipient\n    /// @param _amount The amount of tokens to be transfered\n    /// @return Whether the transfer was successful or not\n    function transferFromWithoutReward(\n        address _from,\n        address _to,\n        uint256 _amount\n    ) returns (bool success);\n\n    /// @notice Doubles the 'minQuorumDivisor' in the case quorum has not been\n    /// achieved in 52 weeks\n    /// @return Whether the change was successful or not\n    function halveMinQuorum() returns (bool _success);\n\n    /// @return total number of proposals ever created\n    function numberOfProposals() constant returns (uint _numberOfProposals);\n\n    /// @param _proposalID Id of the new curator proposal\n    /// @return Address of the new DAO\n    function getNewDAOAddress(uint _proposalID) constant returns (address _newDAO);\n\n    /// @param _account The address of the account which is checked.\n    /// @return Whether the account is blocked (not allowed to transfer tokens) or not.\n    function isBlocked(address _account) internal returns (bool);\n\n    /// @notice If the caller is blocked by a proposal whose voting deadline\n    /// has exprired then unblock him.\n    /// @return Whether the account is blocked (not allowed to transfer tokens) or not.\n    function unblockMe() returns (bool);\n\n    event ProposalAdded(\n        uint indexed proposalID,\n        address recipient,\n        uint amount,\n        bool newCurator,\n        string description\n    );\n    event Voted(uint indexed proposalID, bool position, address indexed voter);\n    event ProposalTallied(uint indexed proposalID, bool result, uint quorum);\n    event NewCurator(address indexed _newCurator);\n    event AllowedRecipientChanged(address indexed _recipient, bool _allowed);\n}\n\n// The DAO contract itself\ncontract DAO is DAOInterface, Token, TokenCreation {\n\n    // Modifier that allows only shareholders to vote and create new proposals\n    modifier onlyTokenholders {\n        if (balanceOf(msg.sender) == 0) throw;\n            _\n    }\n\n    function DAO(\n        address _curator,\n        DAO_Creator _daoCreator,\n        uint _proposalDeposit,\n        uint _minTokensToCreate,\n        uint _closingTime,\n        address _privateCreation\n    ) TokenCreation(_minTokensToCreate, _closingTime, _privateCreation) {\n\n        curator = _curator;\n        daoCreator = _daoCreator;\n        proposalDeposit = _proposalDeposit;\n        rewardAccount = new ManagedAccount(address(this), false);\n        DAOrewardAccount = new ManagedAccount(address(this), false);\n        if (address(rewardAccount) == 0)\n            throw;\n        if (address(DAOrewardAccount) == 0)\n            throw;\n        lastTimeMinQuorumMet = now;\n        minQuorumDivisor = 5; // sets the minimal quorum to 20%\n        proposals.length = 1; // avoids a proposal with ID 0 because it is used\n\n        allowedRecipients[address(this)] = true;\n        allowedRecipients[curator] = true;\n    }\n\n    function () returns (bool success) {\n        if (now < closingTime + creationGracePeriod && msg.sender != address(extraBalance))\n            return createTokenProxy(msg.sender);\n        else\n            return receiveEther();\n    }\n\n\n    function receiveEther() returns (bool) {\n        return true;\n    }\n\n\n    function newProposal(\n        address _recipient,\n        uint _amount,\n        string _description,\n        bytes _transactionData,\n        uint _debatingPeriod,\n        bool _newCurator\n    ) onlyTokenholders returns (uint _proposalID) {\n\n        // Sanity check\n        if (_newCurator && (\n            _amount != 0\n            || _transactionData.length != 0\n            || _recipient == curator\n            || msg.value > 0\n            || _debatingPeriod < minSplitDebatePeriod)) {\n            throw;\n        } else if (\n            !_newCurator\n            && (!isRecipientAllowed(_recipient) || (_debatingPeriod <  minProposalDebatePeriod))\n        ) {\n            throw;\n        }\n\n        if (_debatingPeriod > 8 weeks)\n            throw;\n\n        if (!isFueled\n            || now < closingTime\n            || (msg.value < proposalDeposit && !_newCurator)) {\n\n            throw;\n        }\n\n        if (now + _debatingPeriod < now) // prevents overflow\n            throw;\n\n        // to prevent a 51% attacker to convert the ether into deposit\n        if (msg.sender == address(this))\n            throw;\n\n        _proposalID = proposals.length++;\n        Proposal p = proposals[_proposalID];\n        p.recipient = _recipient;\n        p.amount = _amount;\n        p.description = _description;\n        p.proposalHash = sha3(_recipient, _amount, _transactionData);\n        p.votingDeadline = now + _debatingPeriod;\n        p.open = true;\n        //p.proposalPassed = False; // that's default\n        p.newCurator = _newCurator;\n        if (_newCurator)\n            p.splitData.length++;\n        p.creator = msg.sender;\n        p.proposalDeposit = msg.value;\n\n        sumOfProposalDeposits += msg.value;\n\n        ProposalAdded(\n            _proposalID,\n            _recipient,\n            _amount,\n            _newCurator,\n            _description\n        );\n    }\n\n\n    function checkProposalCode(\n        uint _proposalID,\n        address _recipient,\n        uint _amount,\n        bytes _transactionData\n    ) noEther constant returns (bool _codeChecksOut) {\n        Proposal p = proposals[_proposalID];\n        return p.proposalHash == sha3(_recipient, _amount, _transactionData);\n    }\n\n\n    function vote(\n        uint _proposalID,\n        bool _supportsProposal\n    ) onlyTokenholders noEther returns (uint _voteID) {\n\n        Proposal p = proposals[_proposalID];\n        if (p.votedYes[msg.sender]\n            || p.votedNo[msg.sender]\n            || now >= p.votingDeadline) {\n\n            throw;\n        }\n\n        if (_supportsProposal) {\n            p.yea += balances[msg.sender];\n            p.votedYes[msg.sender] = true;\n        } else {\n            p.nay += balances[msg.sender];\n            p.votedNo[msg.sender] = true;\n        }\n\n        if (blocked[msg.sender] == 0) {\n            blocked[msg.sender] = _proposalID;\n        } else if (p.votingDeadline > proposals[blocked[msg.sender]].votingDeadline) {\n            // this proposal's voting deadline is further into the future than\n            // the proposal that blocks the sender so make it the blocker\n            blocked[msg.sender] = _proposalID;\n        }\n\n        Voted(_proposalID, _supportsProposal, msg.sender);\n    }\n\n\n    function executeProposal(\n        uint _proposalID,\n        bytes _transactionData\n    ) noEther returns (bool _success) {\n\n        Proposal p = proposals[_proposalID];\n\n        uint waitPeriod = p.newCurator\n            ? splitExecutionPeriod\n            : executeProposalPeriod;\n        // If we are over deadline and waiting period, assert proposal is closed\n        if (p.open && now > p.votingDeadline + waitPeriod) {\n            closeProposal(_proposalID);\n            return;\n        }\n\n        // Check if the proposal can be executed\n        if (now < p.votingDeadline  // has the voting deadline arrived?\n            // Have the votes been counted?\n            || !p.open\n            // Does the transaction code match the proposal?\n            || p.proposalHash != sha3(p.recipient, p.amount, _transactionData)) {\n\n            throw;\n        }\n\n        // If the curator removed the recipient from the whitelist, close the proposal\n        // in order to free the deposit and allow unblocking of voters\n        if (!isRecipientAllowed(p.recipient)) {\n            closeProposal(_proposalID);\n            p.creator.send(p.proposalDeposit);\n            return;\n        }\n\n        bool proposalCheck = true;\n\n        if (p.amount > actualBalance())\n            proposalCheck = false;\n\n        uint quorum = p.yea + p.nay;\n\n        // require 53% for calling newContract()\n        if (_transactionData.length >= 4 && _transactionData[0] == 0x68\n            && _transactionData[1] == 0x37 && _transactionData[2] == 0xff\n            && _transactionData[3] == 0x1e\n            && quorum < minQuorum(actualBalance() + rewardToken[address(this)])) {\n\n                proposalCheck = false;\n        }\n\n        if (quorum >= minQuorum(p.amount)) {\n            if (!p.creator.send(p.proposalDeposit))\n                throw;\n\n            lastTimeMinQuorumMet = now;\n            // set the minQuorum to 20% again, in the case it has been reached\n            if (quorum > totalSupply / 5)\n                minQuorumDivisor = 5;\n        }\n\n        // Execute result\n        if (quorum >= minQuorum(p.amount) && p.yea > p.nay && proposalCheck) {\n            if (!p.recipient.call.value(p.amount)(_transactionData))\n                throw;\n\n            p.proposalPassed = true;\n            _success = true;\n\n            // only create reward tokens when ether is not sent to the DAO itself and\n            // related addresses. Proxy addresses should be forbidden by the curator.\n            if (p.recipient != address(this) && p.recipient != address(rewardAccount)\n                && p.recipient != address(DAOrewardAccount)\n                && p.recipient != address(extraBalance)\n                && p.recipient != address(curator)) {\n\n                rewardToken[address(this)] += p.amount;\n                totalRewardToken += p.amount;\n            }\n        }\n\n        closeProposal(_proposalID);\n\n        // Initiate event\n        ProposalTallied(_proposalID, _success, quorum);\n    }\n\n\n    function closeProposal(uint _proposalID) internal {\n        Proposal p = proposals[_proposalID];\n        if (p.open)\n            sumOfProposalDeposits -= p.proposalDeposit;\n        p.open = false;\n    }\n\n    function splitDAO(\n        uint _proposalID,\n        address _newCurator\n    ) noEther onlyTokenholders returns (bool _success) {\n\n        Proposal p = proposals[_proposalID];\n\n        // Sanity check\n\n        if (now < p.votingDeadline  // has the voting deadline arrived?\n            //The request for a split expires XX days after the voting deadline\n            || now > p.votingDeadline + splitExecutionPeriod\n            // Does the new Curator address match?\n            || p.recipient != _newCurator\n            // Is it a new curator proposal?\n            || !p.newCurator\n            // Have you voted for this split?\n            || !p.votedYes[msg.sender]\n            // Did you already vote on another proposal?\n            || (blocked[msg.sender] != _proposalID && blocked[msg.sender] != 0) )  {\n\n            throw;\n        }\n\n        // If the new DAO doesn't exist yet, create the new DAO and store the\n        // current split data\n        if (address(p.splitData[0].newDAO) == 0) {\n            p.splitData[0].newDAO = createNewDAO(_newCurator);\n            // Call depth limit reached, etc.\n            if (address(p.splitData[0].newDAO) == 0)\n                throw;\n            // should never happen\n            if (this.balance < sumOfProposalDeposits)\n                throw;\n            p.splitData[0].splitBalance = actualBalance();\n            p.splitData[0].rewardToken = rewardToken[address(this)];\n            p.splitData[0].totalSupply = totalSupply;\n            p.proposalPassed = true;\n        }\n\n        // Move ether and assign new Tokens\n        uint fundsToBeMoved =\n            (balances[msg.sender] * p.splitData[0].splitBalance) /\n            p.splitData[0].totalSupply;\n        if (p.splitData[0].newDAO.createTokenProxy.value(fundsToBeMoved)(msg.sender) == false)\n            throw;\n\n\n        // Assign reward rights to new DAO\n        uint rewardTokenToBeMoved =\n            (balances[msg.sender] * p.splitData[0].rewardToken) /\n            p.splitData[0].totalSupply;\n\n        uint paidOutToBeMoved = DAOpaidOut[address(this)] * rewardTokenToBeMoved /\n            rewardToken[address(this)];\n\n        rewardToken[address(p.splitData[0].newDAO)] += rewardTokenToBeMoved;\n        if (rewardToken[address(this)] < rewardTokenToBeMoved)\n            throw;\n        rewardToken[address(this)] -= rewardTokenToBeMoved;\n\n        DAOpaidOut[address(p.splitData[0].newDAO)] += paidOutToBeMoved;\n        if (DAOpaidOut[address(this)] < paidOutToBeMoved)\n            throw;\n        DAOpaidOut[address(this)] -= paidOutToBeMoved;\n\n        // Burn DAO Tokens\n        Transfer(msg.sender, 0, balances[msg.sender]);\n        withdrawRewardFor(msg.sender); // be nice, and get his rewards\n        totalSupply -= balances[msg.sender];\n        balances[msg.sender] = 0;\n        paidOut[msg.sender] = 0;\n        return true;\n    }\n\n    function newContract(address _newContract){\n        if (msg.sender != address(this) || !allowedRecipients[_newContract]) return;\n        // move all ether\n        if (!_newContract.call.value(address(this).balance)()) {\n            throw;\n        }\n\n        //move all reward tokens\n        rewardToken[_newContract] += rewardToken[address(this)];\n        rewardToken[address(this)] = 0;\n        DAOpaidOut[_newContract] += DAOpaidOut[address(this)];\n        DAOpaidOut[address(this)] = 0;\n    }\n\n\n    function retrieveDAOReward(bool _toMembers) external noEther returns (bool _success) {\n        DAO dao = DAO(msg.sender);\n\n        if ((rewardToken[msg.sender] * DAOrewardAccount.accumulatedInput()) /\n            totalRewardToken < DAOpaidOut[msg.sender])\n            throw;\n\n        uint reward =\n            (rewardToken[msg.sender] * DAOrewardAccount.accumulatedInput()) /\n            totalRewardToken - DAOpaidOut[msg.sender];\n        if(_toMembers) {\n            if (!DAOrewardAccount.payOut(dao.rewardAccount(), reward))\n                throw;\n            }\n        else {\n            if (!DAOrewardAccount.payOut(dao, reward))\n                throw;\n        }\n        DAOpaidOut[msg.sender] += reward;\n        return true;\n    }\n\n    function getMyReward() noEther returns (bool _success) {\n        return withdrawRewardFor(msg.sender);\n    }\n\n\n    function withdrawRewardFor(address _account) noEther internal returns (bool _success) {\n        if ((balanceOf(_account) * rewardAccount.accumulatedInput()) / totalSupply < paidOut[_account])\n            throw;\n\n        uint reward =\n            (balanceOf(_account) * rewardAccount.accumulatedInput()) / totalSupply - paidOut[_account];\n        if (!rewardAccount.payOut(_account, reward))\n            throw;\n        paidOut[_account] += reward;\n        return true;\n    }\n\n\n    function transfer(address _to, uint256 _value) returns (bool success) {\n        if (isFueled\n            && now > closingTime\n            && !isBlocked(msg.sender)\n            && transferPaidOut(msg.sender, _to, _value)\n            && super.transfer(_to, _value)) {\n\n            return true;\n        } else {\n            throw;\n        }\n    }\n\n\n    function transferWithoutReward(address _to, uint256 _value) returns (bool success) {\n        if (!getMyReward())\n            throw;\n        return transfer(_to, _value);\n    }\n\n\n    function transferFrom(address _from, address _to, uint256 _value) returns (bool success) {\n        if (isFueled\n            && now > closingTime\n            && !isBlocked(_from)\n            && transferPaidOut(_from, _to, _value)\n            && super.transferFrom(_from, _to, _value)) {\n\n            return true;\n        } else {\n            throw;\n        }\n    }\n\n\n    function transferFromWithoutReward(\n        address _from,\n        address _to,\n        uint256 _value\n    ) returns (bool success) {\n\n        if (!withdrawRewardFor(_from))\n            throw;\n        return transferFrom(_from, _to, _value);\n    }\n\n\n    function transferPaidOut(\n        address _from,\n        address _to,\n        uint256 _value\n    ) internal returns (bool success) {\n\n        uint transferPaidOut = paidOut[_from] * _value / balanceOf(_from);\n        if (transferPaidOut > paidOut[_from])\n            throw;\n        paidOut[_from] -= transferPaidOut;\n        paidOut[_to] += transferPaidOut;\n        return true;\n    }\n\n\n    function changeProposalDeposit(uint _proposalDeposit) noEther external {\n        if (msg.sender != address(this) || _proposalDeposit > (actualBalance() + rewardToken[address(this)])\n            / maxDepositDivisor) {\n\n            throw;\n        }\n        proposalDeposit = _proposalDeposit;\n    }\n\n\n    function changeAllowedRecipients(address _recipient, bool _allowed) noEther external returns (bool _success) {\n        if (msg.sender != curator)\n            throw;\n        allowedRecipients[_recipient] = _allowed;\n        AllowedRecipientChanged(_recipient, _allowed);\n        return true;\n    }\n\n\n    function isRecipientAllowed(address _recipient) internal returns (bool _isAllowed) {\n        if (allowedRecipients[_recipient]\n            || (_recipient == address(extraBalance)\n                // only allowed when at least the amount held in the\n                // extraBalance account has been spent from the DAO\n                && totalRewardToken > extraBalance.accumulatedInput()))\n            return true;\n        else\n            return false;\n    }\n\n    function actualBalance() constant returns (uint _actualBalance) {\n        return this.balance - sumOfProposalDeposits;\n    }\n\n\n    function minQuorum(uint _value) internal constant returns (uint _minQuorum) {\n        // minimum of 20% and maximum of 53.33%\n        return totalSupply / minQuorumDivisor +\n            (_value * totalSupply) / (3 * (actualBalance() + rewardToken[address(this)]));\n    }\n\n\n    function halveMinQuorum() returns (bool _success) {\n        // this can only be called after `quorumHalvingPeriod` has passed or at anytime\n        // by the curator with a delay of at least `minProposalDebatePeriod` between the calls\n        if ((lastTimeMinQuorumMet < (now - quorumHalvingPeriod) || msg.sender == curator)\n            && lastTimeMinQuorumMet < (now - minProposalDebatePeriod)) {\n            lastTimeMinQuorumMet = now;\n            minQuorumDivisor *= 2;\n            return true;\n        } else {\n            return false;\n        }\n    }\n\n    function createNewDAO(address _newCurator) internal returns (DAO _newDAO) {\n        NewCurator(_newCurator);\n        return daoCreator.createDAO(_newCurator, 0, 0, now + splitExecutionPeriod);\n    }\n\n    function numberOfProposals() constant returns (uint _numberOfProposals) {\n        // Don't count index 0. It's used by isBlocked() and exists from start\n        return proposals.length - 1;\n    }\n\n    function getNewDAOAddress(uint _proposalID) constant returns (address _newDAO) {\n        return proposals[_proposalID].splitData[0].newDAO;\n    }\n\n    function isBlocked(address _account) internal returns (bool) {\n        if (blocked[_account] == 0)\n            return false;\n        Proposal p = proposals[blocked[_account]];\n        if (now > p.votingDeadline) {\n            blocked[_account] = 0;\n            return false;\n        } else {\n            return true;\n        }\n    }\n\n    function unblockMe() returns (bool) {\n        return isBlocked(msg.sender);\n    }\n}\n\ncontract DAO_Creator {\n    function createDAO(\n        address _curator,\n        uint _proposalDeposit,\n        uint _minTokensToCreate,\n        uint _closingTime\n    ) returns (DAO _newDAO) {\n\n        return new DAO(\n            _curator,\n            DAO_Creator(this),\n            _proposalDeposit,\n            _minTokensToCreate,\n            _closingTime,\n            msg.sender\n        );\n    }\n}\n",
         "ABI":"[{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"name\":\"proposals\",\"outputs\":[{\"name\":\"recipient\",\"type\":\"address\"},{\"name\":\"amount\",\"type\":\"uint256\"},{\"name\":\"description\",\"type\":\"string\"},{\"name\":\"votingDeadline\",\"type\":\"uint256\"},{\"name\":\"open\",\"type\":\"bool\"},{\"name\":\"proposalPassed\",\"type\":\"bool\"},{\"name\":\"proposalHash\",\"type\":\"bytes32\"},{\"name\":\"proposalDeposit\",\"type\":\"uint256\"},{\"name\":\"newCurator\",\"type\":\"bool\"},{\"name\":\"yea\",\"type\":\"uint256\"},{\"name\":\"nay\",\"type\":\"uint256\"},{\"name\":\"creator\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_spender\",\"type\":\"address\"},{\"name\":\"_amount\",\"type\":\"uint256\"}],\"name\":\"approve\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"minTokensToCreate\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"rewardAccount\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"daoCreator\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"totalSupply\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"divisor\",\"outputs\":[{\"name\":\"divisor\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"extraBalance\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_transactionData\",\"type\":\"bytes\"}],\"name\":\"executeProposal\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_from\",\"type\":\"address\"},{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transferFrom\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"unblockMe\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"totalRewardToken\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"actualBalance\",\"outputs\":[{\"name\":\"_actualBalance\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"closingTime\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"allowedRecipients\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transferWithoutReward\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"refund\",\"outputs\":[],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_recipient\",\"type\":\"address\"},{\"name\":\"_amount\",\"type\":\"uint256\"},{\"name\":\"_description\",\"type\":\"string\"},{\"name\":\"_transactionData\",\"type\":\"bytes\"},{\"name\":\"_debatingPeriod\",\"type\":\"uint256\"},{\"name\":\"_newCurator\",\"type\":\"bool\"}],\"name\":\"newProposal\",\"outputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"DAOpaidOut\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"minQuorumDivisor\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_newContract\",\"type\":\"address\"}],\"name\":\"newContract\",\"outputs\":[],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_owner\",\"type\":\"address\"}],\"name\":\"balanceOf\",\"outputs\":[{\"name\":\"balance\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_recipient\",\"type\":\"address\"},{\"name\":\"_allowed\",\"type\":\"bool\"}],\"name\":\"changeAllowedRecipients\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"halveMinQuorum\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"paidOut\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_newCurator\",\"type\":\"address\"}],\"name\":\"splitDAO\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"DAOrewardAccount\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"proposalDeposit\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"numberOfProposals\",\"outputs\":[{\"name\":\"_numberOfProposals\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"lastTimeMinQuorumMet\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_toMembers\",\"type\":\"bool\"}],\"name\":\"retrieveDAOReward\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"receiveEther\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transfer\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"isFueled\",\"outputs\":[{\"name\":\"\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_tokenHolder\",\"type\":\"address\"}],\"name\":\"createTokenProxy\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"}],\"name\":\"getNewDAOAddress\",\"outputs\":[{\"name\":\"_newDAO\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_supportsProposal\",\"type\":\"bool\"}],\"name\":\"vote\",\"outputs\":[{\"name\":\"_voteID\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[],\"name\":\"getMyReward\",\"outputs\":[{\"name\":\"_success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"rewardToken\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_from\",\"type\":\"address\"},{\"name\":\"_to\",\"type\":\"address\"},{\"name\":\"_value\",\"type\":\"uint256\"}],\"name\":\"transferFromWithoutReward\",\"outputs\":[{\"name\":\"success\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_owner\",\"type\":\"address\"},{\"name\":\"_spender\",\"type\":\"address\"}],\"name\":\"allowance\",\"outputs\":[{\"name\":\"remaining\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":false,\"inputs\":[{\"name\":\"_proposalDeposit\",\"type\":\"uint256\"}],\"name\":\"changeProposalDeposit\",\"outputs\":[],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"\",\"type\":\"address\"}],\"name\":\"blocked\",\"outputs\":[{\"name\":\"\",\"type\":\"uint256\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"curator\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[{\"name\":\"_proposalID\",\"type\":\"uint256\"},{\"name\":\"_recipient\",\"type\":\"address\"},{\"name\":\"_amount\",\"type\":\"uint256\"},{\"name\":\"_transactionData\",\"type\":\"bytes\"}],\"name\":\"checkProposalCode\",\"outputs\":[{\"name\":\"_codeChecksOut\",\"type\":\"bool\"}],\"type\":\"function\"},{\"constant\":true,\"inputs\":[],\"name\":\"privateCreation\",\"outputs\":[{\"name\":\"\",\"type\":\"address\"}],\"type\":\"function\"},{\"inputs\":[{\"name\":\"_curator\",\"type\":\"address\"},{\"name\":\"_daoCreator\",\"type\":\"address\"},{\"name\":\"_proposalDeposit\",\"type\":\"uint256\"},{\"name\":\"_minTokensToCreate\",\"type\":\"uint256\"},{\"name\":\"_closingTime\",\"type\":\"uint256\"},{\"name\":\"_privateCreation\",\"type\":\"address\"}],\"type\":\"constructor\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_from\",\"type\":\"address\"},{\"indexed\":true,\"name\":\"_to\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"_amount\",\"type\":\"uint256\"}],\"name\":\"Transfer\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_owner\",\"type\":\"address\"},{\"indexed\":true,\"name\":\"_spender\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"_amount\",\"type\":\"uint256\"}],\"name\":\"Approval\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":false,\"name\":\"value\",\"type\":\"uint256\"}],\"name\":\"FuelingToDate\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"to\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"amount\",\"type\":\"uint256\"}],\"name\":\"CreatedToken\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"to\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"value\",\"type\":\"uint256\"}],\"name\":\"Refund\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"proposalID\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"recipient\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"amount\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"newCurator\",\"type\":\"bool\"},{\"indexed\":false,\"name\":\"description\",\"type\":\"string\"}],\"name\":\"ProposalAdded\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"proposalID\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"position\",\"type\":\"bool\"},{\"indexed\":true,\"name\":\"voter\",\"type\":\"address\"}],\"name\":\"Voted\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"proposalID\",\"type\":\"uint256\"},{\"indexed\":false,\"name\":\"result\",\"type\":\"bool\"},{\"indexed\":false,\"name\":\"quorum\",\"type\":\"uint256\"}],\"name\":\"ProposalTallied\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_newCurator\",\"type\":\"address\"}],\"name\":\"NewCurator\",\"type\":\"event\"},{\"anonymous\":false,\"inputs\":[{\"indexed\":true,\"name\":\"_recipient\",\"type\":\"address\"},{\"indexed\":false,\"name\":\"_allowed\",\"type\":\"bool\"}],\"name\":\"AllowedRecipientChanged\",\"type\":\"event\"}]",
         "ContractName":"DAO",
         "CompilerVersion":"v0.3.1-2016-04-12-3ad5e82",
         "OptimizationUsed":"1",
         "Runs":"200",
         "ConstructorArguments":"000000000000000000000000da4a4626d3e16e094de3225a751aab7128e965260000000000000000000000004a574510c7014e4ae985403536074abe582adfc80000000000000000000000000000000000000000000000001bc16d674ec80000000000000000000000000000000000000000000000000a968163f0a57b4000000000000000000000000000000000000000000000000000000000000057495e100000000000000000000000000000000000000000000000000000000000000000",
         "EVMVersion":"Default",
         "Library":"",
         "LicenseType":"",
         "Proxy":"0",
         "Implementation":"",
         "SwarmSource":""
      }
   ]
}
```

</details>

### Get Contract Creator and Creation Tx Hash

Returns a contract's deployer address and transaction hash it was created, up to 5 at a time.

<mark style="background-color:blue;">**GET**</mark> [**`/api/1.0/verify-contract`**](https://xfiscan.com/api/1.0/swagger#/verify-contract/VerifyContractController_get)

#### Request

```ruby
https://xfiscan.com/api/1.0/verify-contract
   ?chainid=1
   &module=contract
   &action=getcontractcreation
   &contractaddresses=0xB83c27805aAcA5C7082eB45C868d955Cf04C337F,
0x68b3465833fb72A70ecDF485E0e4C7bD8665Fc45,
0xe4462eb568E2DFbb5b0cA2D3DbB1A35C9Aa98aad,
0xdAC17F958D2ee523a2206206994597C13D831ec7,
0xf5b969064b91869fBF676ecAbcCd1c5563F591d0
   &apikey=YourApiKeyToken
```

#### Parameters

| Parameter           | Type     | Destcrition                                |
| ------------------- | -------- | ------------------------------------------ |
| `contractaddresses` | `string` | The contract addresses, up to 5 at a time. |

<details>

<summary>Sample Response</summary>

```json
{ 
"status": "1", 
"message": "OK", 
"result": "Pass - Verified" - If the contract compilation fails, an error will be displayed. 
}
```

</details>

### Check Source Code Verification Status

Returns the success or error status of a contract verification request.

[<mark style="background-color:blue;">**GET**</mark> **`/api/1.0/verify-contract`**](https://xfiscan.com/api/1.0/swagger#/verify-contract/VerifyContractController_get)

#### Request

```ruby
https://xfiscan.com/api/1.0/verify-contract
  ?chainid=1
  &module=contract
  &action=checkverifystatus
  &guid=x3ryqcqr1zdknhfhkimqmizlcqpxncqc6nrvp3pgrcpfsqedqi
  &apikey=YourApiKeyToken
```

#### Parameters

| Parameter           | Type            | Description                                                                                                                                                                        |
| ------------------- | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `apikey`            | `string`        | Your API key token.                                                                                                                                                                |
| `module`            | `string`        | Contract.                                                                                                                                                                          |
| `action`            | `string`        | Verify source code. Available values: `getabi`, `getsourececode`, `getcontractcreation`, `verifysourcecode`, `checkverifystatus`, `verifyproxycontract`, `checkproxyverification`. |
| `address`           | `string`        | The contract address that has a verified source code.                                                                                                                              |
| `contractaddresses` | `array[string]` | The contract addresses, up to 5 at a time.                                                                                                                                         |
| `guid`              | `string`        | The unique GUID received from the verification request.                                                                                                                            |
| `chainid`           | `string`        | The chain to submit verification, such as 1 for mainnet.                                                                                                                           |

<details>

<summary>Sample Response </summary>

```json
{ 
"status": "1", 
"message": "OK", 
"result": "Pass - Verified" - If the contract compilation fails, an error will be displayed. 
}
```

</details>

### Verify Source Code

{% hint style="info" %}
This endpoint is limited to 100 verifications/day, regardless of API PRO tier.&#x20;
{% endhint %}

The request responsible for verifying the contract. Submits a contract source code to an explorer for verification.

<mark style="background-color:green;">**POST**</mark>[**`/api/1.0/verify-contract`**](https://xfiscan.com/api/1.0/swagger#/verify-contract/VerifyContractController_post)

#### Request

```ruby
https://xfiscan.com/api/1.0/verify-contract
  ?chainid=1
  &module=contract
  &action=verifysourcecode
  &apikey=YourApiKeyToken

{
  "apikey": "string",
  "module": "contract",
  "action": "verifysourcecode",
  "chainId": "string",
  "codeformat": "string",
  "sourceCode": "string",
  "constructorArguments": "string",
or "constructorArguements": "string",
  "contractname": "string",
  "compilerversion": "string",
  "contractaddress": "string"
}
```

| Parameter              | Type            | Description                                                                                    |
| ---------------------- | --------------- | ---------------------------------------------------------------------------------------------- |
| `chainid`              | `string`        | The chain to submit verification, such as 1 for mainnet.                                       |
| `codeformat`           | `string`        | Single file, use `solidity-single-file JSON` (recommended), or `solidity-standard-json-input`. |
| `sourceCode`           | `string`        | The Solidity source code.                                                                      |
| `constructorArguments` | `string`        | Optional, include if your contract uses constructor arguments.                                 |
| `contractaddresses`    | `array[string]` | The contract addresses, up to 5 at a time.                                                     |
| `contractname`         | `string`        | The name of your contract, such as `Contracts/Verified.sol:Verified`.                          |
| `compilerversion`      | `string`        | Compiler version used, such as `v0.8.24+commit.e11b9e09`.                                      |

### List of compiler versions

Getting a list of compiler versions.

<mark style="background-color:blue;">**GET**</mark>[**`/api/1.0/verify-contract/compiler-versions`**](https://xfiscan.com/api/1.0/swagger#/verify-contract/VerifyContractController_compilerVersions)

#### Sample Response

```json
https://xfiscan.com/api/1.0/verify-contract/compiler-versions
```

## XDS

#### <mark style="background-color:blue;">GET</mark>[/api/1.0/xds/grace-period](https://test.xfiscan.com/api/1.0/swagger#/xds/XdsController_gracePeriod)

This endpoint returns the "grace period" duration (in milliseconds), which is used for managing XDS.

#### Parameters

None

#### **Response Schema**

| Parameter     | Type   | Description                                   |
| ------------- | ------ | --------------------------------------------- |
| `gracePeriod` | number | Duration of the grace period in milliseconds. |

<details>

<summary>Sample Response</summary>

```json
{
  "gracePeriod": 7776000000
}
```

</details>

#### <mark style="background-color:blue;">GET</mark>[/api/1.0/xds/resolve/{nameOrAddress}](https://test.xfiscan.com/api/1.0/swagger#/xds/XdsController_findOneSearch)

This endpoint retrieves the details of an XDS name or address.

#### Parameters

| **Parameter**   | **Type** | **Description**                     |
| --------------- | -------- | ----------------------------------- |
| `nameOrAddress` | string   | The XDS name or address to resolve. |

<details>

<summary>Sample Response</summary>

```json
{
  "name": "babowski",
  "address": "0xd5bc963907fb8e70d8dd0d6c80f20482d210c2fe",
  "cost": 51140131949348780,
  "createDate": "2024-12-04T10:50:14.311Z",
  "expires": "2025-01-03T10:50:05.000Z",
  "id": "86474684294996161923329261405762601077011403072914365421360940037980101854682",
  "label": "0xbad8504a0fe6be57c69ebcd0d1ba0109fb50e7f356cac23eb32c96b398c370c9",
  "node": "0xbf2eefd4a853b4c1a1fe37f0ca5b27380d161873ba6c346f1a3103ad5618c5da",
  "owner": "0xd5bc963907fb8e70d8dd0d6c80f20482d210c2fe",
  "premium": 0,
  "primary": true,
  "updateDate": "2024-12-04T10:50:14.311Z",
  "ownerXds": {
    "address": "0xd5bc963907fb8e70d8dd0d6c80f20482d210c2fe",
    "name": "babowski",
    "expires": "2025-01-03T10:50:05.000Z"
  }
}
```

</details>

#### **Response Schema**

| **Parameter** | **Type**           | **Description**                                |
| ------------- | ------------------ | ---------------------------------------------- |
| `name`        | string             | Name resolved to the address.                  |
| `address`     | string             | Address associated with the XDS name.          |
| `cost`        | number             | Cost of the name in the blockchain.            |
| `createDate`  | string (date-time) | Date the XDS name was created.                 |
| `expires`     | string (date-time) | Expiration date of the XDS name.               |
| `id`          | string             | Unique ID of the name or address.              |
| `label`       | string             | Hash representation of the name's label.       |
| `node`        | string             | Hash representation of the name's node.        |
| `owner`       | string             | Address of the name's owner.                   |
| `premium`     | number             | Premium cost for the name (if any).            |
| `primary`     | boolean            | Whether the name is primary (true/false).      |
| `updateDate`  | string (date-time) | Last update date of the XDS name.              |
| `ownerXds`    | object             | Details about the owner’s XDS (nested object). |
| - `address`   | string             | Address of the XDS owner.                      |
| - `name`      | string             | Name associated with the owner’s XDS.          |
| - `expires`   | string (date-time) | Expiration date of the owner’s XDS.            |

#### <mark style="background-color:blue;">GET</mark>[/api/1.0/xds/{name}](https://test.xfiscan.com/api/1.0/swagger#/xds/XdsController_findOne)

This endpoint retrieves details about an XDS (similar to ENS) domain name.

#### Parameters&#x20;

| Parameter | Type   | Description              |
| --------- | ------ | ------------------------ |
| `name`    | string | The XDS name to look up. |

<details>

<summary>Sample Response</summary>

```json
{
  "name": "babowski",
  "address": "0xd5bc963907fb8e70d8dd0d6c80f20482d210c2fe",
  "cost": 51140131949348780,
  "createDate": "2024-12-04T10:50:14.311Z",
  "expires": "2025-01-03T10:50:05.000Z",
  "id": "86474684294996161923329261405762601077011403072914365421360940037980101854682",
  "label": "0xbad8504a0fe6be57c69ebcd0d1ba0109fb50e7f356cac23eb32c96b398c370c9",
  "node": "0xbf2eefd4a853b4c1a1fe37f0ca5b27380d161873ba6c346f1a3103ad5618c5da",
  "owner": "0xd5bc963907fb8e70d8dd0d6c80f20482d210c2fe",
  "premium": 0,
  "primary": true,
  "updateDate": "2024-12-04T10:50:14.311Z",
  "ownerXds": {
    "address": "0xd5bc963907fb8e70d8dd0d6c80f20482d210c2fe",
    "name": "babowski",
    "expires": "2025-01-03T10:50:05.000Z"
  }
}

```

</details>

#### **Response Schema**

| **Parameter** | **Type** | **Description** |
| ------------- | -------- | --------------- |

| `name` | string | The XDS domain name. |
| ------ | ------ | -------------------- |

| `address` | string | Address linked to the name. |
| --------- | ------ | --------------------------- |

| `cost` | number | The cost of the domain name in blockchain units. |
| ------ | ------ | ------------------------------------------------ |

| `createDate` | string | Date when the name was registered. |
| ------------ | ------ | ---------------------------------- |

| `expires` | string | Expiration date of the name. |
| --------- | ------ | ---------------------------- |

| `id` | string | Unique identifier of the XDS name. |
| ---- | ------ | ---------------------------------- |

| `label` | string | Label hash of the name. |
| ------- | ------ | ----------------------- |

| `node` | string | Node hash of the name. |
| ------ | ------ | ---------------------- |

| `owner` | string | Owner's address of the XDS name. |
| ------- | ------ | -------------------------------- |

| `premium` | number | Premium fee for the name (if applicable). |
| --------- | ------ | ----------------------------------------- |

| `primary` | boolean | Whether this is the primary name (true/false). |
| --------- | ------- | ---------------------------------------------- |

| `updateDate` | string | Last modification date of the XDS record. |
| ------------ | ------ | ----------------------------------------- |

| `ownerXds` | object | Details of the owner's XDS (nested object). |
| ---------- | ------ | ------------------------------------------- |

| - `address` | string | Address linked to the owner. |
| ----------- | ------ | ---------------------------- |

| - `name` | string | Name linked to the owner. |
| -------- | ------ | ------------------------- |

| - `expires` | string | Expiry date of the owner’s XDS. |
| ----------- | ------ | ------------------------------- |

#### <mark style="background-color:blue;">GET</mark>[/api/1.0/xds](https://test.xfiscan.com/api/1.0/swagger#/xds/XdsController_find)

This endpoint retrieves a paginated list of XDS names with detailed metadata.

| **Parameter** | **Type** | **Description** |
| ------------- | -------- | --------------- |

| `expires` | string (date-time) | Expiration date of the XDS name. |
| --------- | ------------------ | -------------------------------- |

| `premium` | number | Premium fee for the name (if applicable). |
| --------- | ------ | ----------------------------------------- |

| `owner` | string | Address of the owner. |
| ------- | ------ | --------------------- |

| `name` | string | XDS name to search for. |
| ------ | ------ | ----------------------- |

| `address` | string | Blockchain address associated with the name. |
| --------- | ------ | -------------------------------------------- |

| `addresses` | array\[string] | Array of multiple account addresses. |
| ----------- | -------------- | ------------------------------------ |

| `label` | string | Label hash representation of the name. |
| ------- | ------ | -------------------------------------- |

| `cost` | number | Cost of the XDS name. |
| ------ | ------ | --------------------- |

| `primary` | boolean | Whether the name is a primary identifier. |
| --------- | ------- | ----------------------------------------- |

| `searchName` | string | Name search query. |
| ------------ | ------ | ------------------ |

| `page` | number | Page number (default: 1). |
| ------ | ------ | ------------------------- |

| `limit` | number | Number of records per page (default: 10). |
| ------- | ------ | ----------------------------------------- |

| `sort` | string | Sorting field (default: `-blockNumber`). |
| ------ | ------ | ---------------------------------------- |

| `select` | string | Fields to include in the response. |
| -------- | ------ | ---------------------------------- |

<details>

<summary>Sample Response</summary>

```json
{
  "docs": [
    {
      "name": "algianm",
      "address": "0xbfe5dc3a84d728389cd132fa7b2b0fd94dc28b07",
      "cost": 117548045263474900,
      "createDate": "2024-10-15T09:13:17.043Z",
      "expires": "2025-01-23T09:13:08.000Z",
      "id": "46485682030983406595572370802244772183536596271838902013627254194517637619194",
      "label": "0xd5c59f20ea4e11ed72f9a04e2836a1263e52994cd2dd39c71e7756190ddf22db",
      "node": "0x66c5f6b1150d489daffdbba4b58c483dd8a0fe0338c72141dd09f386e5b05dfa",
      "owner": "0xbfe5dc3a84d728389cd132fa7b2b0fd94dc28b07",
      "premium": 0,
      "primary": true,
      "updatedAt": "2024-10-15T09:13:17.043Z",
      "ownerXds": {
        "name": "algianm",
        "address": "0xbfe5dc3a84d728389cd132fa7b2b0fd94dc28b07",
        "expires": "2025-01-23T09:13:08.000Z"
      }
    }
  ],
  "hasNext": true,
  "limit": 10,
  "page": 1
}

```

</details>

#### Response Schema

| **Parameter** | **Type** | **Description** |
| ------------- | -------- | --------------- |

| `name` | string | XDS domain name. |
| ------ | ------ | ---------------- |

| `address` | string | Address linked to the name. |
| --------- | ------ | --------------------------- |

| `cost` | number | Cost of the name in blockchain units. |
| ------ | ------ | ------------------------------------- |

| `createDate` | string (date-time) | Date when the name was registered. |
| ------------ | ------------------ | ---------------------------------- |

| `expires` | string (date-time) | Expiration date of the name. |
| --------- | ------------------ | ---------------------------- |

| `id` | string | Unique identifier of the XDS name. |
| ---- | ------ | ---------------------------------- |

| `label` | string | Label hash of the name. |
| ------- | ------ | ----------------------- |

| `node` | string | Node hash of the name. |
| ------ | ------ | ---------------------- |

| `owner` | string | Owner's address of the XDS name. |
| ------- | ------ | -------------------------------- |

| `premium` | number | Premium fee for the name (if applicable). |
| --------- | ------ | ----------------------------------------- |

| `primary` | boolean | Whether this is the primary name (true/false). |
| --------- | ------- | ---------------------------------------------- |

| `updateDate` | string (date-time) | Last modification date of the XDS record. |
| ------------ | ------------------ | ----------------------------------------- |

| `ownerXds` | object | Details of the owner's XDS (nested object). |
| ---------- | ------ | ------------------------------------------- |

| - `address` | string | Address linked to the owner. |
| ----------- | ------ | ---------------------------- |

| - `name` | string | Name linked to the owner. |
| -------- | ------ | ------------------------- |

| - `expires` | string (date-time) | Expiry date of the owner’s XDS. |
| ----------- | ------------------ | ------------------------------- |

| `hasNext` | boolean | Indicates if more pages exist. |
| --------- | ------- | ------------------------------ |

| `page` | number | Current page number. |
| ------ | ------ | -------------------- |

| `limit` | number | Number of records returned per page. |
| ------- | ------ | ------------------------------------ |
