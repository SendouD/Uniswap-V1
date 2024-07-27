## Uniswap v1

Uniswap V1, is a decentralized exchange (DEX) built on the Ethereum blockchain. It allows users to trade ERC-20 tokens directly from their wallets without the need for a centralized intermediary.

Uniswap V1 employs an Automated Market Maker (AMM) model, specifically the Constant Product Market Maker (CPMM). In this model, liquidity providers (LPs) supply equal values of two tokens into a liquidity pool. The product of the quantities of these two tokens remains constant, meaning if one token's quantity increases, the other's must decrease to maintain the balance.

The price of the tokens in the pool is determined by the ratio of their quantities. The formula used is:
x⋅y=k
where 𝑥 and y are the quantities of the two tokens in the pool, and 𝑘is a constant. This ensures liquidity at any price level, but can lead to large price slippage for substantial trades.

we mint a token for ourself to check this out 
Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### .env file 

Create a .env file in the foundry-app folder and add the following lines. Follow the instructions below:

Go to Quicknode and sign up for an account. If you already have an account, log in. Quicknode is a node provider that lets you connect to various different blockchains. We will be using it to deploy our contract through Foundry. After creating an account, Create an endpoint on Quicknode, select Ethereum, and then select the Sepolia network. Click Continue in the bottom right and then click on Create Endpoint. Copy the link given to you in HTTP Provider and add it to the .env file below for QUICKNODE_HTTP_URL.

NOTE: If you previously set up a Sepolia endpoint, you can keep using that one. If you have any other endpoints from the past, you need to delete it to create a new one.

To get your private key, you need to export it from your wallet.MAKE SURE YOU ARE USING A TEST ACCOUNT THAT DOES NOT HAVE MAINNET FUNDS FOR THIS. Add this Private Key below in your .env file for PRIVATE_KEY variable.

### Compile

```shell
$ forge compile
```

### Deploy
```shell
$forge create --rpc-url $QUICKNODE_RPC_URL --private-key $PRIVATE_KEY --etherscan-api-key $ETHERSCAN_API_KEY --verify src/Token.sol:Token

```

```shell
$forge create --rpc-url $QUICKNODE_RPC_URL --private-key $PRIVATE_KEY --constructor-args <address of the token contract you just deployed> --etherscan-api-key $ETHERSCAN_API_KEY --verify src/Exchange.sol:Exchange

```


### Usage 
Go to sepolia etherium website and search for the address you got after deploying and go to contract.write and read the requirements from there  
