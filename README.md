# FalconX
FalconX Assignment!

Method 1

Using BitQuery and Bloxy

- Bloxy is a bitquery platform. Bloxy gives a better access into the DEX pools, with a wide range of options to choose from, as well choosing the exact nature of analysis demanded by the user.
- For this project, I made use of the 'DEX Trade' functionality, which gives access to the trades for all ERC-20 tokens on a DEX based protocol. I have chosen to use the UNISWAP (UNI) protocol. The question asked for the UNI/WETH comparison, hence the data has been filtered out to remove the extra pairs. The data spans over 6 months, from 01-01-2021.
- All the trades are concerned with the Uniswap v2 pool protocol. Other statistical markers such as volume and liquidity and presented in a separate dataframe.

Details

1. The file concerned with this method is the BitQuery.ipynb.

2. In the first methodology adopted, I have used Bitqueries inbuilt method of querying data. Bitquery uses the GraphQL format, however the schema used is a little different. In Bitquery, the data can be accessed simply by typing the name of platform/currency concerned and its related attributed. Since the project is concerned with WETH, the querying is done with ethereum{......}. The API key for bitquery can be obtained after logging in on - https://graphql.bitquery.io/ide#. The IDE is also useful for testing and studying the queried data. Bitquery clearly distinguishes the query areas, such as DEX exchanges or Contract based querying. The protocol being used is Uniswap-v2.

3. The data is pulled for 1000 trades on the platform, with the trade data upto 2021-06-22.

4. The second methodology adopted uses a Bitquery platform, called Bloxy (https://bloxy.info). Bloxy gives a better access to statistical data surrounding trade orders, purchases and pool information. The trial period account gives 50 free API calls accross the services selected, such as Token Pair Statistics, DEX status etc. 

5. I was interested in the DEX trades from the UNISWAP protocol, so I went ahead with the DEX trade option, and gave in the uniswap token as a parameter, 0x1f9840a85d5af5bf1d1762f925bdaddc4201f984, ensuring only uniswap protocol trades were being queried. The data spans over 6 months, starting from 2021-01-01. 

6. I pulled the data in the project through Pandas and Requests. UNI/WETH data has been selected and hence the filters are applied on the DataFrame (https://bloxy.info/api_method_calls/dex?method=trades). Owing to the sheer number of trades, I have chosen to perform the analysis on the first 1000 trade orders. 

7. The project also mentioned the need for volume and liquidity, which is obtained by selecting the ' Statistics of Token DEX Trades at DEX' option, and entering the Uniswap token.




Method 2 - Simple and Tutorial Based

External Packages used - 
1. gql - To access the GraphQL Api's
2. Numpy
3. Pandas
4. Matplotlib
5. Graphene - Interating with GraphQL on Python.

To install the packages used, run pip/pip3 install -r requirments.txt

Getting Started

1. The data pulled in this project is from the Uniswap-V2 Pool. As instructred, the project is concerned about the UNI/WETH pair of tokens,hence the concerned pool.
Given that the data is being pulled through the aid of an api, the url being used is - https://api.thegraph.com/subgraphs/name/uniswap/uniswap-v2 and the program estabilishes the connection a maximum of 5 times if the connection is not estabilished earlier.

2. Preliminary queries and related commands can be worked on the site - https://thegraph.com/explorer/subgraph/uniswap/uniswap-v2. Unlike SQL, GraphQL retrieves objects when their sizing is defined. The gql package in the project is useful for running these commands in the Python Script. The different queries and the meanings of their objects can be studied from - https://uniswap.org/docs/v2/API/entities/

3. It is important to refer to the right token values. Owing to the sheer number of token pairs, the right id of the token pairs needs to be used in order to get the relevant information. For testing purpose, and if there exists some ambiguity with regards to the tokens being used, the GraphQL query object 'Pair', with its reference to symbol can be used to see the pair of tokens in actions. Token pairs can be retrieved from - https://tokenlists.org/token-list?url=https://raw.githubusercontent.com/jab416171/uniswap-pairtokens/master/uniswap_pair_tokens.json

0xa47ea5b74b6879c52250794376443eebd8a17bb3 - UNI/WETH pair.

4. Once the data has been queried, it needs to be passed through the JSON normalise function of pandas in order to split it into the relevant columns. Initally the data retrieved is in the 'String' format, which can be changed into the numeric format using pd_numerical function.

5. Since the project is built around historical data, for quering the token pair, I have made use of the swaps query method (as suggested in the tutorial), wheras the Poolside uses the uniswap-factory method of querying the data. 

6. Research work with regards to the above project is in the file titled 'Research.pdf'.

7. The 'MainFile' is concerned with the token pair, while 'PoolSide' is concerned with the uniswap pool.

8. If the goal is to estabilish a full scale crypto-trading or poolside analytics platform, capable of adding liquidity, carrying out purchase orders and communicate effectively with token pools, the package uniswap-python can be used, with reference to https://uniswap-python.com/api.html#uniswap.Uniswap. Connections are estabilished using environment variables, using either Infura_url or w3, with the address and private keys being provided by the user. However the limitation with Uniswap-Python is that the Pool functions and Liquidity Methods are supported only by Uniswap-V1. This project is built on the V2 pool.
Uniswap-Python's true potential is realised with the connection to a wallet.

Observations

1. CryptoCurrencies are location specific, there is a huge emphasis on the position of a transaction on the chain or the block being referred to while making an analysis. As compared to the stock trading, which traditionally takes the aid of platforms such as Quandl and is a more 'macro-focus' in its approach, crypto's are about every intricate transaction of the chain being considered, Ethereum in our case.

2. Given GraphQL's unique approach, data extraction is not achieved through primitive api referencing, instead the code must incorporate the query commands.

Note - Unless you're using a virtual environment, the requirements.txt file can be generated from the 'pigar' package. Run pip3 install pigar, and then pigar.

