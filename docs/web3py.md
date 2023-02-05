# `web3.py`

Web3.py is a Python library that allows interaction with Ethereum, typically used in decentralized apps. It offers functionality for sending transactions, working with smart contracts, retrieving block information and more. The library's API was initially based on Web3.js (Javascript), but has been adapted to better suit the needs of Python developers. For further information, refer to the official documentation at https://web3py.readthedocs.io/en/stable/.

## Requirements

### Local Environment

`web3.py` requries Python 3.6 or higher.

### Ethereum Endpoint

<!-- endpoint? -->

Collecting on-chain data using `web3.py` requires an Ethereum endpoint. Best way is to use remote node provider, like [Infura](https://infura.io/), [Alchemy](https://www.alchemy.com/), or [QuickNode](https://www.quicknode.com/). [This document](https://ethereum.org/en/developers/docs/nodes-and-clients/run-a-node/) explains how to run a local node or get a remote node.

<!-- API Type? -->
<!-- Customization? -->

## Sample Data

You can find sample data in [data/sample_web3py.json](data/sample_web3py.json). The following lists an item of the sample data.

```json
{
  "difficulty": 598426820912,
  "extraData": "0x476574682f76312e302e302f77696e646f77732f676f312e342e32",
  "gasLimit": 5000,
  "gasUsed": 0,
  "hash": "0xdc2d938e4cd0a149681e9e04352953ef5ab399d59bcd5b0357f6c0797470a524",
  "logsBloom": "0x00000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000",
  "miner": "0xBf71642d7CBae8FaF1CFdc6C1C48fcB45b15eD22",
  "mixHash": "0xc6bf383db032101cc2101543db260602b709e5d9e38444bb71b680777185448b",
  "nonce": "0xb75e5f372524d34c",
  "number": 10000,
  "parentHash": "0xb9ecd2df84ee2687efc0886f5177f6674bad9aeb73de9323e254e15c5a34fc93",
  "receiptsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
  "sha3Uncles": "0x1dcc4de8dec75d7aab85b567b6ccd41ad312451b948a7413f0a142fd40d49347",
  "size": 541,
  "stateRoot": "0x4de830f589266773eae1a1caa88d75def3f3a321fbd9aeb89570a57c6e7f3dbb",
  "timestamp": 1438334627,
  "totalDifficulty": 2303762395359969,
  "transactions": [],
  "transactionsRoot": "0x56e81f171bcc55a6ff8345e692c0f86e5b48e01b996cadc001622fb5e363b421",
  "uncles": []
}
```

| Field            | Description                                                                                        |
| ---------------- | -------------------------------------------------------------------------------------------------- |
| difficulty       | The difficulty for this block                                                                      |
| extraData        | The "extra data" field of this block                                                               |
| gasLimit         | The maximum gas allowed in this block                                                              |
| gasUsed          | The total used gas by all transactions in this block                                               |
| hash             | The block hash                                                                                     |
| logsBloom        | The bloom filter for the logs of the block                                                         |
| miner            | The address of the beneficiary to whom the mining rewards were given                               |
| mixHash          | Hash of the generated proof-of-work                                                                |
| nonce            | The nonce of the block                                                                             |
| number           | The block number                                                                                   |
| parentHash       | The hash of the parent block                                                                       |
| receiptsRoot     | The root of the receipts trie of the block                                                         |
| sha3Uncles       | The SHA3 of the uncles data in the block                                                           |
| size             | The size of this block in bytes                                                                    |
| stateRoot        | The root of the final state trie of the block                                                      |
| timestamp        | The unix timestamp for when the block was collated                                                 |
| totalDifficulty  | The total difficulty of the chain until this block                                                 |
| transactions     | Array of transaction objects, or 32 Bytes transaction hashes depending on the last given parameter |
| transactionsRoot | The root of the transaction trie of the block                                                      |
| uncles           | Array of uncle hashes                                                                              |

## Usage

Here is a simple example of how to use `web3.py` to get the latest block number and details of a block.

```python
import web3

# Connect to a remote Ethereum node
w3 = Web3(Web3.WebsocketProvider('<your-node-address>'))

# Check if connected to Ethereum node
if w3.isConnected():
    print("Connected to Ethereum node")
else:
    print("Not connected to Ethereum node")

# Get the latest block number
block_number = w3.eth.blockNumber
print("Latest block number:", block_number)

# Get details of a block
block = w3.eth.getBlock(block_number)
print("Block details:", block)

# Get the balance of an Ethereum address
address = "0x742d35Cc6634C0532925a3b844Bc454e4438f44e"
balance = w3.eth.getBalance(address)
print("Balance of address", address, ":", balance)
```

This code connects to a local Ethereum node using the WebsocketProvider and checks if it is connected. Then, it retrieves the latest block number, retrieves the details of that block, and gets the balance of a specific Ethereum address.

More example usage of `web3.py` can be found in the [examples](../examples/web3py.ipynb)

