# `etherscan-python`

`etherscan-python` is a comprehensive Python API for [Etherscan.io](https://etherscan.io/).  It offers both the standard and pro endpoints for the mainnet of the Ethereum blockchain as well as that of the Kovan, Rinkeby, and Ropsten testnets. The API can be found on [PyPI](https://pypi.org/project/etherscan-python/) and is powered by the [Etherscan.io APIs](https://etherscan.io/apis#misc). 

## Requirements

### Installation

```bash
pip install etherscan-python
```

### API Key

You need to get an API key from [Etherscan.io](https://etherscan.io/apis#misc). The API key is required for all requests.

## Sample Data

You can find sample data in [data/sample_etherscan.json](../data/sample_etherscan.json). The following lists an item of the sample data.

```json
{
  "blockNumber": "1000000",
  "timeStamp": "1455404053",
  "blockMiner": "0x2a65aca4d5fc5b5c859090a6c34d164135398226",
  "blockReward": "5003614887722000000",
  "uncles": [],
  "uncleInclusionReward": "0"
}
```

| Field                | Description                 |
| -------------------- | --------------------------- |
| blockNumber          | The block number.           |
| timeStamp            | The timestamp of the block. |
| blockMiner           | The address of the miner.   |
| blockReward          | The block reward.           |
| uncles               | The list of uncle hashes.   |
| uncleInclusionReward | The uncle inclusion reward. |

## Usage

```python
# Import the Etherscan and pandas libraries
from etherscan import Etherscan
import pandas as pd

# Import the tqdm library for progress bar display
from tqdm import tqdm

# Initialize the Etherscan object with your API key
eth = Etherscan(api_key='<your api key>')

# Get the block rewards for 100 blocks, with a progress bar display
rewards = [eth.get_block_reward_by_block_number(
    x) for x in tqdm(range(1000000, 1000100))]

# Create a pandas dataframe from the rewards list
df_blocks = pd.DataFrame(rewards)

# Display the dataframe
df_blocks.show()
```

The example initializes an Etherscan object with an API key, and then retrieves the block rewards for 100 blocks (from block 1000000 to 1000100) using the get_block_reward_by_block_number method of the Etherscan object. The block rewards are stored in a list, which is then converted into a pandas dataframe. The dataframe is then displayed.

