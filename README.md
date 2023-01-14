# eth-data-collection
Collection of Ethereum Blockchain Data Sources

This repo collects some open source data sources for Ether, and gives a brief introduction to their usage and data formats. It is worth noting that this repo is not a complete data source, but a collection of data sources, so if you want to get the complete data, you need to implement the data collection by yourself. And, for the sake of generality, the repo only includes data sources with Python as the main development language and some web API. Other data sources will be added in subsequent updates.

**Environment**

This repo is developed and tested on the following environment:
- `Python`, version 3.10.8
- `pipenv`, version 2022.11.11

The `Pipfile` includes all the dependencies of the repo, so you can use `pipenv` to install them. More instruction can be found in [official documentation](https://pipenv.pypa.io/en/latest/).

## `Web3py`

Web3.py is a Python Ether API that can be used to connect to Ether nodes and get blockchain data. Its usage can be found in [official documentation](https://web3py.readthedocs.io/en/stable/).

[Usage](docs/web3py.md)

## `ethereum-etl`

ethereum-etl is a Python Ether data collection tool that can be used to collect Ether data from the blockchain. Its usage can be found in [official documentation](https://ethereum-etl.readthedocs.io/en/latest/).

[Usage](docs/ethereum-etl.md)

## `ethereum2-etl`

ethereum2-etl is a Python Ethereum 2.0 data collection tool that can be used to collect Ethereum 2.0 data from the blockchain. Its usage can be found in [official documentation](https://ethereum2-etl.readthedocs.io/en/latest/).

[Usage](docs/ethereum2-etl.md)

## `etherscan-python`

etherscan-python is a Python wrapper that can be used to connect to Etherscan and get Ether data. Its usage can be found in [official documentation](https://pypi.org/project/etherscan/)

[Usage](docs/etherscan-python.md)

## `bitquery`

bitquery is a GraphQL API that can be used to get Ether data. Its usage can be found in [official documentation](https://graphql.bitquery.io/)

[Usage](docs/bitquery.md)