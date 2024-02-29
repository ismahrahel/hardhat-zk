# hardhat-zksync

Hardhat plugin for zksync Developers.

## Features

zksyncScan Contract Verification

## Prerequisites

Before the installation steps you need to have your hardhat project initialized using the command

```bash
npx hardhat init
```

Make sure to have dependencies installed!

## Installation

Use the following command to install

```bash
npm i hardhat-zksync --save-dev
```

Import the plugin in your `hardhat.config.js`:

```js
require("hardhat-zksync");
```

Or if you are using TypeScript, in your `hardhat.config.ts`:

```ts
import "hardhat-zksync";
```

Remove / Comment the import for `@nomicfoundation/hardhat-toolbox`

Add the following configuration to the `config` object in `hardhat.config.js`.

```js
networks: {
        zksyncGoerli: {
            // can be replaced with the RPC url of your choice.
            url: "https://goerli-rollup.zksync.io/rpc",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        },
        zksyncOne: {
            url: "https://arb1.zksync.io/rpc",
            accounts: [
                "<YOUR_PRIVATE_KEY>"
            ],
        }
    },
    etherscan: {
        apiKey: {
            zksyncGoerli: "<OPTIMISMSCAN_API_KEY>",
            zksyncOne: "<OPTIMISMSCAN_API_KEY>"
        },
    },
```

Verify your contracts using the following command (Make sure your contracts are compiled before verification)

zksync Goerli Testnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network zksyncGoerli
```

zksync Mainnet

```bash
npx hardhat verify <CONTRACT_ADDRESS> <CONSTRUCTOR_ARGS> --network zksyncOne
```
