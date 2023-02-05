# `ethereum2-etl`

Ethereum 2.0 ETL enables the transformation of blockchain information into user-friendly formats, such as CSV and relational databases. With over 700 likes on Github, Ethereum ETL is the most highly-regarded open source project for Ethereum data. Ethereum 2.0 ETL is a fork of Ethereum ETL that adds support for Ethereum 2.0 data. For more information, please visit the [official documentation](https://ethereum2-etl.readthedocs.io/en/latest/).

## Requirements

### Installation

Install Ethereum 2.0 ETL:

```shell
pip install ethereum2-etl
```

## Sample Data

You can find sample data in [data/sample_ethereum_etl_2.json](../data/sample_ethereum_etl_2.json). The following lists an item of the sample data.

```json
{
  "item_type": "beacon_block",
  "block_slot": 4680002,
  "block_epoch": 146250,
  "block_timestamp": "2022-09-12T12:00:47Z",
  "proposer_index": 373276,
  "skipped": false,
  "block_root": null,
  "parent_root": "0xe9442499af2b521c7b53ff476d01436c967ffa956278dbe7baed5cff34d4a555",
  "state_root": "0x490ba5390836bd6e956c62e19e3421185d6bff689a81fd2f2d4dde5384e12ea7",
  "randao_reveal": "0x902597f35320a2ae53e99a8fac3fd1d414e8070d18255a5d6c1fd0785f8384648f1ab5502818564431dfd128eae2d561001f7521e242e281d003f4f6d3f53c73a16ca45a91cda7e25edc0856b22403706e3eda50af4091c705084c58b709a545",
  "graffiti": "0x4c69676874686f7573652f76332e312e302d6161303232663400000000000000",
  "eth1_block_hash": "0x9a14d9a48d6ccdc215ddbf1103e91b20a3bb0513614efe9da49871ccc84da23d",
  "eth1_deposit_root": "0x309bd2edaa17edf01b0f6423ef04ff932770509e4ac8d92272a72d5b203e7be0",
  "eth1_deposit_count": 434383,
  "signature": null,
  "attestations": [
    {
      "item_type": "attestation",
      "aggregation_bits": "1111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111",
      "slot": 4680001,
      "index": 10,
      "beacon_block_root": "0xe9442499af2b521c7b53ff476d01436c967ffa956278dbe7baed5cff34d4a555",
      "source_epoch": 146249,
      "source_root": "0x13a52c9d5322d0492d9842bad66748d9773779d6697fd55f9eb1b261b24908dc",
      "target_epoch": 146250,
      "target_root": "0xd899e67eec06d604933d83815f89a7b7daa92098b8f0f8a2808070baf186f5b9",
      "signature": "0x87cae57a4887d7187393ab6946a5c99e288fc90346011f71e04451b909855a712a7fa8c8905087717eb8a254a52130621758ff9e623e77315b3f8c6219d9fddd1b16233c8ea39d8625e780e7478cc690eff03cf096c4280f292e917836b40139"
    },
    {
      "item_type": "attestation",
      "aggregation_bits": "0000000000000000000000000000000000000000000000000000000000000000000000000100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000010000000000000000000000000000000000000",
      "slot": 4680000,
      "index": 13,
      "beacon_block_root": "0x4489d44916f6e2208f6432f83c327f2955135d476f5ad44a85c941837a0ec2fa",
      "source_epoch": 146249,
      "source_root": "0x13a52c9d5322d0492d9842bad66748d9773779d6697fd55f9eb1b261b24908dc",
      "target_epoch": 146250,
      "target_root": "0x4489d44916f6e2208f6432f83c327f2955135d476f5ad44a85c941837a0ec2fa",
      "signature": "0x869a899e24c340ff672b05d4857b9719e228b442b20db931554bee3cbc547202c3e59a7aa5b373b48e09f2d50fee5cd10bcb5c0b8100032509f98c64286842a3230606b83f079518f277e2b88c6920abd66cce30dc716d3d52094ceb1bb5b014"
    }
  ],
  "deposits": [],
  "proposer_slashings": [],
  "attester_slashings": [],
  "voluntary_exits": []
}
```

| Field              | Description                          |
| :----------------- | :----------------------------------- |
| item_type          | The type of the item.                |
| block_slot         | The slot of the block.               |
| block_epoch        | The epoch of the block.              |
| block_timestamp    | The timestamp of the block.          |
| proposer_index     | The index of the proposer.           |
| skipped            | Whether the block is skipped.        |
| block_root         | The root of the block.               |
| parent_root        | The root of the parent block.        |
| state_root         | The root of the state.               |
| randao_reveal      | The randao reveal.                   |
| graffiti           | The graffiti.                        |
| eth1_block_hash    | The hash of the eth1 block.          |
| eth1_deposit_root  | The root of the eth1 deposit.        |
| eth1_deposit_count | The count of the eth1 deposit.       |
| signature          | The signature of the block.          |
| attestations       | The attestations of the block.       |
| deposits           | The deposits of the block.           |
| proposer_slashings | The proposer slashings of the block. |
| attester_slashings | The attester slashings of the block. |
| voluntary_exits    | The voluntary exits of the block.    |

### Infura Endpoint

Sync your own node or request access to node on [Infura](https://blog.infura.io/checking-your-eth-2-0-validator-balance/). [This article](https://blog.infura.io/post/getting-started-with-infura-28e41844cc89) provides a good introduction to setup Infura endpoints.

## Usage

This example shows how to export beacon blocks, attestations, deposits, proposer slashings, attester slashings, and voluntary exits.

```shell
ethereum2etl export_beacon_blocks --start-block 0 --end-block 200 \
--output-dir output --output-format json \
--provider-uri https://projectid:secret@medalla.infura.io
```

You can find more usage examples and some visualization in [Example](../examples/ethereum2-etl.ipynb)
