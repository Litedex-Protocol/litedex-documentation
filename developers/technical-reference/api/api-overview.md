# API Overview

This section explains the Litedex Subgraph and how to interact with it. The Litedex subgraph indexes data from the Litedex contracts over time. It organizes data about pairs, tokens, Litedex as a whole, and more. The subgraph updates any time a transaction is made on Litedex. The subgraph runs on [The Graph](https://thegraph.com/) protocol's hosted service and can be openly queried.

### Resources[​](https://docs.uniswap.org/contracts/v2/reference/API/overview#resources) <a href="#resources" id="resources"></a>

``[`Subgraph Explorer`](https://thegraph.com/hosted-service/subgraph/jieeevest/litedex-data) - sandbox for querying data and endpoints for developers.

``[`Litedex Subgraph`](https://api.thegraph.com/subgraphs/name/jieeevest/litedex-data) - endpoint for deployed subgraph.

### Usage[​](https://docs.uniswap.org/contracts/v2/reference/API/overview#usage) <a href="#usage" id="usage"></a>

The subgraph provides a snapshot of the current state of Litedex and also tracks historical data. It will be used to power [`Litedex info`](https://info.litedex.io). **It is not intended to be used as a data source for structuring transactions (contracts should be referenced directly for the most reliable live data).**

### Making Queries[​](https://docs.uniswap.org/contracts/v2/reference/API/overview#making-queries) <a href="#making-queries" id="making-queries"></a>

To learn more about querying a subgraph refer to [The Graph's documentation](https://thegraph.com/docs/about/introduction).
