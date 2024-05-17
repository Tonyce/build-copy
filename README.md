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
$ forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
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

## Deploy
    
```shell
❯ forge create --rpc-url https://base-sepolia.g.alchemy.com/v2/mwGPVe9op8x1I6WTVgDo2qjRbbEmQbSV \                                                                                                    ─╯
   --constructor-args build-copy bc 10000000000 0x3ae6c93C96e0366b899bEe8e286a6946a9DAd52b  \
  --private-key $PRIVATE_KEY --etherscan-api-key $PRIVATE_KEY --verify \
  src/GovernableToken.sol:GovernableERC20
[⠆] Compiling...
No files changed, compilation skipped
Deployer: 0x3ae6c93C96e0366b899bEe8e286a6946a9DAd52b
Deployed to: 0x0e6C43c2ef6cd5FF413d906E32f3A55c5b993c56
Transaction hash: 0x2fd4705f8c9da7edcf46fea3d2afda317560308ba272bd0c324cbf5fa188087b
Starting contract verification...
Waiting for etherscan to detect contract deployment...
Start verifying contract `0x0e6C43c2ef6cd5FF413d906E32f3A55c5b993c56` deployed on base-sepolia

Submitting verification for [src/GovernableToken.sol:GovernableERC20] 0x0e6C43c2ef6cd5FF413d906E32f3A55c5b993c56.
Encountered an error verifying this contract:
Response: `NOTOK`
Details: `Invalid API Key`

# verify contract on etherscan
❯ forge verify-contract --chain-id 84532 \                                                                                                                                                           ─╯
  --watch \
  --etherscan-api-key $ETHERSCAN_API_KEY \
  0x0e6C43c2ef6cd5FF413d906E32f3A55c5b993c56 \
  src/GovernableToken.sol:GovernableERC20 --constructor-args $(cast abi-encode "constructor(string, string, uint256, address)"  "build-copy" "bc" 10000000000 0x3ae6c93C96e0366b899bEe8e286a6946a9DAd52b)
Start verifying contract `0x0e6C43c2ef6cd5FF413d906E32f3A55c5b993c56` deployed on base-sepolia

Submitting verification for [src/GovernableToken.sol:GovernableERC20] 0x0e6C43c2ef6cd5FF413d906E32f3A55c5b993c56.
Submitted contract for verification:
        Response: `OK`
        GUID: `ddy3tfwflcvy9uesbfkgqzp1cmyix7ncdlxritzzhezqxcimxd`
        URL: https://sepolia.basescan.org/address/0x0e6c43c2ef6cd5ff413d906e32f3a55c5b993c56
Contract verification status:
Response: `NOTOK`
Details: `Pending in queue`
Contract verification status:
Response: `OK`
Details: `Pass - Verified`
Contract successfully verified
```