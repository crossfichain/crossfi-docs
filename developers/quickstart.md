# Quickstart

In this guide, you will learn how to deploy a smart contract to the CrossFi Chain. We will create a simple contract, test the contract and, then deploy it. This guide can be used later when you are deploying more complex contracts as the steps will be similiar.&#x20;

## Requirements&#x20;

* [Node.js  ](https://nodejs.org/en/download/prebuilt-binaries)
* Basic understanding of [Solidity](https://soliditylang.org/)&#x20;
* Tesnet XFI Coins (the faucets are in the [test XFI Console](https://test.xficonsole.com/cosmos-wallet))&#x20;

## Installing Foundry (Required)

In this guide, we will use [Foundry](https://getfoundry.sh/) to test and deploy our smart contract. Foundry lets us do this all within one tool set and using the command line (CLI).&#x20;

First, we will make a file directory for our project and then install Foundry. **If you already Foundry installed, you can skip this step.**&#x20;

### Creating the Project&#x20;

In your terminal, run the following command to make a folder and initialize npm.

```bash
mkdir crossfi_quickstart && cd crossfi_quickstart && npm init -y
```

### Downloading and Installing Foundry&#x20;

The below command will download the latest version of Foundry:&#x20;

```bash
curl -L https://foundry.paradigm.xyz | bash
```

After the download is complete, run the `foundryup` command in your terminal:&#x20;

```bash
foundryup
```

{% hint style="warning" %}
If using MacOS , you may receive the following error:&#x20;

dyld\[32719]: Library not loaded: /usr/local/opt/libusb/lib/libusb-1.0.0.dylib

To fix this run **brew install libusb** (Requires Homebrew)&#x20;
{% endhint %}

## Create the Contract&#x20;

Now we will create the contract file and supporting files by using the below command:&#x20;

```bash
forge init counter_contract
```

You can now open up your code editor at the location of  the newly  created `counter_contract`. A folder structure like below should be created:&#x20;

```
--lib
--script
--src
--test
--README.md
--foundry.toml
```

Don't worry if you are not sure what all these folders are for now as we will use them throughout this guide.&#x20;

### Reviewing the Counter Smart Contract&#x20;

In your code editor, open up the Counter.sol file that is located in `/src/Counter.sol.` The code should be the same as below with potentially a different Solidity version:&#x20;

```solidity
// SPDX-License-Identifier: UNLICENSED
pragma solidity ^0.8.13;

contract Counter {
    uint256 public number;

    function setNumber(uint256 newNumber) public {
        number = newNumber;
    }

    function increment() public {
        number++;
    }
}
```



This contract includes:&#x20;

**number** -  A number variable that is assigned as an unsigned integer with 256 bits.&#x20;

**setNumber**  - A public function that can be called to set the number variable&#x20;

**increment** - A public function that increments the number variable by 1&#x20;

## Compile the Contract&#x20;

Now we need to compile the contract. This is a necessary step to verify that our smart contract doesn't have any logical coding errors. It is not a test of the security of the smart contract.&#x20;

We can do this by running the below command:&#x20;

```bash
forge build
```

If successful, this will create a folder named `out` that contains the ABI of our smart contract in the form of a JSON file named **Counter.json.**

## Testing the Contract&#x20;

For this guide, we will not have to create our tests as they are provided to us in the `/test/Counter.t.sol` file. The code should look like this:&#x20;

```solidity
// SPDX-License-Identifier: UNLICENSED
pragma solidity ^0.8.13;

import {Test, console} from "forge-std/Test.sol";
import {Counter} from "../src/Counter.sol";

contract CounterTest is Test {
    Counter public counter;

    function setUp() public {
        counter = new Counter();
        counter.setNumber(0);
    }

    function test_Increment() public {
        counter.increment();
        assertEq(counter.number(), 1);
    }

    function testFuzz_SetNumber(uint256 x) public {
        counter.setNumber(x);
        assertEq(counter.number(), x);
    }
}
```

We can then execute the test code by running the following command:&#x20;

```bash
forge test 
```

After running this command, you should see that 2 tests passed as well as a gas amount for the `Increment` function:&#x20;

```bash
Ran 2 tests for test/Counter.t.sol:CounterTest
[PASS] testFuzz_SetNumber(uint256) (runs: 256, μ: 30066, ~: 31310)
[PASS] test_Increment() (gas: 31325)
Suite result: ok. 2 passed; 0 failed; 0 skipped; finished in 9.45ms (5.75ms CPU time)
```

## Deploying the Contract

Now it is time to deploy our smart contract on the testnet CrossFi chain. We can do this in a single command by using **forge create.**

You will need to use a private key that is connected to your wallet with XFI testnet tokens.&#x20;

```bash
forge create --rpc-url https://rpc.testnet.ms \
--private-key YOUR_PRIVATE_KEY \
src/Counter.sol:Counter 
```

&#x20;If the deployment is successful, you should see your contract address under the "**Deployed to"** in your terminal.&#x20;

```bash
Deployer: 0x85Ec95865AD3F912213f105d4f44e132B381f719
Deployed to: 0xE785D511Fa79B4D3C0c5C4182090EA8D89F32FF4
Transaction hash: 0x26ec2881d45dbb0eda13e2cd7df165d6ff8ff15a49af0196b45c5e7f34291d69
```

You can verify that your contract has been deployed to the CrossFi testnet by searching for its address using the [test XFI Scan](https://test.xfiscan.com/dashboard).

## Interacting with the Contract

In the final step of this guide, we will interact with our contract by calling the public functions.  We can do this by using Foundry and the following commands:&#x20;

### Setting the Number&#x20;

To use the `setNumber` function to set the new number, you can use the following command:&#x20;

```bash
cast send YOUR_CONTRACT_ADDRESS "setNumber(uint256)" 5 --rpc-url https://rpc.testnet.ms --private-key YOUR_PRIVATE_KEY
```

If successful, you will see the `blockHash` and other transaction data.&#x20;

### Reading the Number

To read the current value of the number variable,  you can use the following command:&#x20;

```bash
cast call YOUR_CONTRACT_ADDRESS "number()" --rpc-url https://rpc.testnet.ms
```

### Incrementing the Number&#x20;

To use the `increment` **function** to increment the number by 1, you can use the following command:&#x20;

```bash
cast send YOUR_CONTRACT_ADDRESS "increment()" --rpc-url https://rpc.testnet.ms --private-key YOUR_PRIVATE_KEY
```

## Conclusion&#x20;

Congrats, you have now tested, compiled and, deployed a smart contract to the CrossFi Testnet!&#x20;

The steps you completed in this guide are the same steps you can take as you continue [building on CrossFi](integrating-developer-tools.md).&#x20;
