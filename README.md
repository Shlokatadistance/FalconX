# FalconX
FalconX Assignment!

External Packages used - 
1. gql - To access the GraphQL Api's
2. Numpy
3. Pandas
4. Matplotlib
5. Graphene

To install the packages used, run pip/pip3 install -r requirments.txt

Getting Started

1. The data pulled in this project is from the Uniswap-V2 Pool. As instructred, the project is concerned about the UNI/WETH pair of tokens.
Given that the data is being pulled through the aid of an api, the url being used is - https://api.thegraph.com/subgraphs/name/uniswap/uniswap-v2 and the program estabilishes the connection a maximum of 5 times if the connection is not estabilished earlier.

2. Preliminary queries and related commands can be worked on the site - https://thegraph.com/explorer/subgraph/uniswap/uniswap-v2. Unlike SQL, GraphQL retrieves objects when their sizing is defined. The gql package in the project is useful for running these commands in the Python Script. The different queries and the meanings of their objects can be studied from - https://uniswap.org/docs/v2/API/entities/

3. It is important to refer to the right token values. Owing to the sheer number of token pairs, the right id of the token pairs needs to be used in order to get the relevant information. For testing purpose, and if there exists some ambiguity with regards to the tokens being used, the GraphQL query object 'Pair', with its reference to symbol can be used to see the pair of tokens in actions. Token pairs can be retrieved from - https://tokenlists.org/token-list?url=https://raw.githubusercontent.com/jab416171/uniswap-pairtokens/master/uniswap_pair_tokens.json

0xa47ea5b74b6879c52250794376443eebd8a17bb3 - UNI/WETH pair.

4. Once the data has been queried, it needs to be passed through the JSON normalise function of pandas in order to split it into the relevant columns. Initally the data retrieved is in the 'String' format, which can be changed into the numeric format using pd_numerical function.

5. Research work with regards to the above project is in the file titled 'Research.pdf'.

6. The 'MainFile' is concerned with the token pair, while 'PoolSide' is concerned with the uniswap pool.

7. If the goal is to estabilish a full scale crypto-trading or poolside analytics platform, capable of adding liquidity, carrying out purchase orders and communicate effectively with token pools, the package uniswap-python can be used, with reference to https://uniswap-python.com/api.html#uniswap.Uniswap. Connections are estabilished using environment variables, using either Infura_url or w3, with the address and private keys being provided by the user.


Observations

1. CryptoCurrencies are location specific, there is a huge emphasis on the location of a transaction on the chain or the block being referred to while making an analysis. As compared to the stock trading, which traditionally takes the aid of platforms such as Quandl and is a more 'macro-focus' in its approach, crypto's are about every intricate transaction of the chain being considered, Ethereum in our case.

2. Given GraphQL's unique approach, data extraction is not achieved through primitive api referencing, instead the code must incorporate the query commands.
