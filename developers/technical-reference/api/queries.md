# Queries

The subgraph can be queried to retrieve important information about Litedex, pairs, tokens, transactions, and more. This page will provide examples for common queries.

To try these queries and run your own visit the [subgraph sandbox](https://thegraph.com/hosted-service/subgraph/jieeevest/litedex-data).

#### Global Data[​](https://docs.uniswap.org/contracts/v2/reference/API/queries#global-data) <a href="#global-data" id="global-data"></a>

To query global data you can pass in the Litedex Factory address and select from available fields.

**Global Stats**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#global-stats)

All time volume in USD, total liquidity in USD, all time transaction count.

```
{
  prodFactory(id: "0x716d94d0b70f5a50133a61c12d37309dad93bab4") {
    totalVolumeUSD
   	totalLiquidityUSD
   	totalTransactions
  }
}
```

#### Pair Data[​](https://docs.uniswap.org/contracts/v2/reference/API/queries#pair-data) <a href="#pair-data" id="pair-data"></a>

**Pair Overview**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#pair-overview)

Fetch a snapshot of the current state of the pair with common values. This example fetches the LDX/BUSD pair.

```
{
 pair(id: "0x07150f8394d5d533700758f081db1cdf519052dc"){
     token0 {
       id
       symbol
       name
       derivedUSD
     }
     token1 {
       id
       symbol
       name
       derivedUSD
     }
     reserve0
     reserve1
     reserveUSD
     trackedReserveBNB
     token0Price
     token1Price
     volumeUSD
     totalTransactions
 }
}
```

**All pairs in Litedex**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#all-pairs-in-uniswap)

The Graph limits entity return amounts to 1000 per query as of now. To get all pairs on Uniswap use a loop and graphql skip query to fetch multiple chunks of 1000 pairs. The query would look like this (where skip is some incrementing variable passed into your query).

```
{
 query pairs($skip: Int!) {
   pairs(first: 1000, skip: $skip) {
     id
   }
 }
}
```

**Most liquid pairs**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#most-liquid-pairs)

Order by liquidity to get the most liquid pairs in Uniswap.

```
{
 pairs(first: 1000, orderBy: reserveUSD, orderDirection: desc) {
   id
 }
}
```

**Recent Swaps within a Pair**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#recent-swaps-within-a-pair)

Get the last 100 swaps on a pair by fetching Swap events and passing in the pair address. You'll often want token information as well.

```
{
swaps(orderBy: timestamp, orderDirection: desc, where:
 { pair: "0x07150f8394d5d533700758f081db1cdf519052dc" }
) {
     pair {
       token0 {
         symbol
       }
       token1 {
         symbol
       }
     }
     amount0In
     amount0Out
     amount1In
     amount1Out
     amountUSD
     to
 }
}
```

**Pair Daily Aggregated**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#pair-daily-aggregated)

Day data is useful for building charts and historical views around entities. To get stats about a pair in daily buckets query for day entities bounded by timestamps. This query gets the first 100 days after the given unix timestamp on the LDX/BUSD pair.

```
{
 pairDayDatas(first: 100, orderBy: date, orderDirection: asc,
   where: {
     pairAddress: "0x07150f8394d5d533700758f081db1cdf519052dc",
     date_gt: 1669939100
   }
 ) {
     date
     dailyVolumeToken0
     dailyVolumeToken1
     dailyVolumeUSD
     reserveUSD
 }
}
```

#### Token Data[​](https://docs.uniswap.org/contracts/v2/reference/API/queries#token-data) <a href="#token-data" id="token-data"></a>

Token data can be fetched using the token contract address as an ID. Token data is aggregated across all pairs the token is included in. Any token that is included in some pair in Litedex can be queried.

**Token Overview**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#token-overview)

Get a snapshot of the current stats on a token in Litedex. This query fetches current stats on LDX. The allPairs field gets the first 200 pairs LDX is included in sorted by liquidity in derived USD.

```
{
 token(id: "0x8286387174b8667ae5222306a27e9ab5189b503b"){
   name
   symbol
   decimals
   derivedUSD
   tradeVolumeUSD
   totalLiquidity
 }
}
```

**All Tokens in Litedex**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#all-tokens-in-uniswap)

Similar to fetching all pairs (see above), you can query all tokens in Litedex. Because The Graph service limits return size to 1000 entities use GraphQL skip query. (Note this query will not work in the graph sandbox and more resembles the structure of a query you'd pass to some GraphQL middleware like [Apollo](https://www.apollographql.com/)).

```
{
 query tokens($skip: Int!) {
   tokens(first: 1000, skip: $skip) {
     id
     name
     symbol
   }
 }
}
```

**Token Transactions**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#token-transactions)

To get transactions that include a token you'll need to first fetch an array of pairs that the token is included in (this can be done with the allPairs field on the Token entity.) Once you have an array of pairs the token is included in, filter on that in the transaction lookup.

This query fetches the latest 30 mints, swaps, and burns involving LDX. The allPairs array could look something like this where we include the LDX/BUSD pair address.

```
allPairs = [
 "0x07150f8394d5d533700758f081db1cdf519052dc"
]
```

```
query($allPairs: [String!]) {
 mints(first: 30, where: { pair_in: $allPairs }, orderBy: timestamp, orderDirection: desc) {
   transaction {
     id
     timestamp
   }
   to
   liquidity
   amount0
   amount1
   amountUSD
 }
 burns(first: 30, where: { pair_in: $allPairs }, orderBy: timestamp, orderDirection: desc) {
   transaction {
     id
     timestamp
   }
   to
   liquidity
   amount0
   amount1
   amountUSD
 }
 swaps(first: 30, where: { pair_in: $allPairs }, orderBy: timestamp, orderDirection: desc) {
   transaction {
     id
     timestamp
   }
   amount0In
   amount0Out
   amount1In
   amount1Out
   amountUSD
   to
 }
}
```

**Token Daily Aggregated**[**​**](https://docs.uniswap.org/contracts/v2/reference/API/queries#token-daily-aggregated)

Like pair and global daily lookups, tokens have daily entities that can be queries as well. This query gets daily information for LDX. Note that you may want to sort in ascending order to receive your days from oldest to most recent in the return array.

```
{
 tokenDayDatas(orderBy: date, orderDirection: asc,
  where: {
    token: "0x8286387174b8667ae5222306a27e9ab5189b503b"
  }
 ) {
    id
    date
    priceUSD
    totalLiquidityToken
    totalLiquidityUSD
    totalLiquidityBNB
    dailyVolumeBNB
    dailyVolumeToken
    dailyVolumeUSD
 }
}
```

#### BNB Price[​](https://docs.uniswap.org/contracts/v2/reference/API/queries#eth-price) <a href="#eth-price" id="eth-price"></a>

You can use the Bundle entity to query current USD price of BNB in Litedex based on a weighted average of stablecoins.

```
{
 bundle(id: "1" ) {
   bnbPrice
 }
}
```
