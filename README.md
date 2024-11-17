# Ethereum Onchain Analysis
Example for Ethereum Onchain Analysis. In this example, we demonstrate how ETH exchange addresses can be classified utilizing machine learning.

## Dataset
[Chartalist Dataset [1]](https://chartalist.org/eth/TaskTypePrediction.html)

- On chain-transactions from 2016-2020.
- 49 DEX addresses and 247 CEX addresses.

[1] Kiarash Shamsi, Friedhelm Victor, Murat Kantarcioglu, Yulia R. Gel, and Cuneyt G. Akcora. 2024. Chartalist: labeled graph datasets for UTXO and account-based blockchains. In Proceedings of the 36th International Conference on Neural Information Processing Systems (NIPS '22). Curran Associates Inc., Red Hook, NY, USA, Article 2531, 34926–34939.

## Data Preparations
- [Download](https://chartalist.org/eth/TaskTypePrediction.html) data and place it into data directory.
- We perform a 60-40 split to obtain exchange labels for training and test datasets.
- We also included 1,000 randomly sampled negative examples (non-exchange) addresses.
- Notebook to generate train and test data: [00_data_preparation.ipynb](00_data_preparation.ipynb)

## Classify Ethereum Exchange Addresses
- Classical machine learning: [01_classify_exchange_tree.ipynb](01_classify_exchange_tree.ipynb)

## Limitations of Chartalist Dataset
- Missing timestamp data: Dataset does not incliude transaction timestamp
- Missing wallet balance: Dataset does not contain wallet balance. Only contain transactions.
- 'Dead' exchanges: Some exchanges may not be available (e.g. FTX).
- Varying decimal places: Different tokens have different decimal places (e.g. $10^{18}$ for one wei for WETH vs $10^8$ for HEX)

