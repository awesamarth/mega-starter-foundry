# Mega Starter

This is a starter Foundry template made for developers building on MegaETH. 

## Getting Started
Install the Mega CLI if you don't have it already
```shell
npm install -g mega-cli
#or
pnpm add -g mega-cli
#or
yarn global add mega-cli
```

Start a local blockchain node using this command:

```shell
mega dev
```


## Deploying Contracts
### Locally
Make sure you are in the root directory and run the following command: 
```shell
mega deploy src/GmegaCounter.sol:GmegaCounter --broadcast
```
This command will use the first account provided by Anvil to deploy your contract to the local blockchain. 

### On MegaETH

The recommended method is to use keystores. If you already have a dev account and want to put it in a keystore, run `mega account import`. If you want to create a new account (public-private keypair) and put it in a keystore, run `mega account create`. You can use your keystore account to deploy contracts on Mega like so:


```shell
mega deploy src/GmegaCounter.sol:GmegaCounter --account <name-of-account> --broadcast
```
This command will ask you to enter the password for the account you provided and will then deploy your contract to MegaETH Testnet

If you want to use private keys instead, Create a new `.env.local` file in the root directory based on the .env.example file. Add your private key to this file. Ensure this doesn't contain any mainnet funds, just for safety purposes.

Point your terminal to the root directory and run `source .env.local` in the terminal to load up the environment variables in the .env.local file. Once that is done, run this command:

```shell
mega deploy src/GmegaCounter.sol:GmegaCounter --private-key $DEV_PRIVATE_KEY --broadcast --testnet
```

Congratulations! Your smart contract is now deployed on MegaETH testnet!


## Foundry

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

### Gas Snapshots

```shell
$ forge snapshot
```

### Anvil

```shell
$ anvil
```

### Deploy

```shell
$ forge script script/GmegaCounter.s.sol:GmegaCounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### Cast

```shell
$ cast <subcommand>
```

### Help

```shell
$ forge --help
$ anvil --help
$ cast --help
```
