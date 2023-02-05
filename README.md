# eth-data-collection
Collection of Ethereum Blockchain Data Sources

This repo collects some open source data sources for Ether, and gives a brief introduction to their usage and data formats. It is worth noting that this repo is not a complete data source, but a collection of data sources, so if you want to get the complete data, you need to implement the data collection by yourself. And, for the sake of generality, the repo only includes data sources with Python as the main development language and some web API. Other data sources will be added in subsequent updates.

## `Web3py`

Web3.py is a Python library that allows interaction with Ethereum, typically used in decentralized apps. It offers functionality for sending transactions, working with smart contracts, retrieving block information and more. The library's API was initially based on Web3.js (Javascript), but has been adapted to better suit the needs of Python developers. More information can be found in [official documentation](https://web3py.readthedocs.io/en/stable/).

[Detail](docs/web3py.md)

## `ethereum2-etl`

Ethereum 2.0 ETL enables the transformation of blockchain information into user-friendly formats, such as CSV and relational databases. With over 700 likes on Github, Ethereum ETL is the most highly-regarded open source project for Ethereum data. Ethereum 2.0 ETL is a fork of Ethereum ETL that adds support for Ethereum 2.0 data. For more information, please visit the [official documentation](https://ethereum2-etl.readthedocs.io/en/latest/).

[Detail](docs/ethereum2-etl.md)

## `etherscan-python`

`etherscan-python` is a comprehensive Python API for [Etherscan.io](https://etherscan.io/) that is minimal yet complete. It offers all of the standard and pro endpoints, and also supports the Kovan, Rinkeby, and Ropsten testnets. The API can be found on [PyPI](https://pypi.org/project/etherscan-python/) and is powered by the [Etherscan.io APIs](https://etherscan.io/apis#misc). More information can be found in [official documentation](https://github.com/pcko1/etherscan-python).

[Detail](docs/etherscan-python.md)

## `bitquery`

Bitquery is a GraphQL API that provides a flexible and efficient way to access and analyze blockchain data. By using GraphQL, Bitquery enables users to query only the data they need, rather than receiving a large amount of unneeded data. This results in faster, more streamlined access to blockchain data, and improved performance overall. More information can be found in the [official documentation](https://bitquery.io/)

[Detail](docs/bitquery.md)