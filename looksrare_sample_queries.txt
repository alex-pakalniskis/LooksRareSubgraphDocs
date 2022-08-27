---
sidebar_position: 3
title: Sample Queries
---

## Sample Queries

Below are some sample queries you can use to gather information from the LooksRare Exchange contract.

You can build your own queries using a [GraphQL Explorer](https://graphiql-online.com/graphiql) and enter your endpoint to limit your queries to the exact data desired.

### Collection Totals

Description: Get the collections total stats

```graphql
query collectionTotals($Collection: String = "0x23581767a106ae21c074b2276d25e5c3e136a68b") {
  collection(id: $Collection) {
    id
    totalVolume
    totalRoyaltyPaid
    totalTransactions
  }
}
```

### Collection Transactions

Description: Get the 10 most recent transactions for a collection.

```graphql
query collectionTransactions($Collection: String = "0x23581767a106ae21c074b2276d25e5c3e136a68b") {
  transactions(
    where: {collection: $Collection}
    , orderBy: block
    , orderDirection: desc
    , first: 10) {
    block
    date
    isTakerAsk
    price
    tokenId
    taker {id}
    maker {id}
  }
}
```

### Collection Daily Stats

Description: Get the collection's daily metrics for the last 7 trading days (days will skip if no trades occur)

```graphql
query collectionDailyStats($Collection: String = "0x23581767a106ae21c074b2276d25e5c3e136a68b") {
  collectionDailyDatas(
    where: {collection: $Collection}
    , orderBy: date
    , orderDirection: desc
    , first: 7) {
    dailyRoyalty
    dailyVolume
    dailyTransactions
    collection {
      id
    }
  }
}

```

### Collection Royalties

Description: Get the 10 most recent royalty payments to a collection.

```graphql
query collectionRoyalties ($Collection: String = "0x23581767a106ae21c074b2276d25e5c3e136a68b") {
  royaltyTransfers(
    where: {collection: $Collection}
    , first: 10
    , orderBy: block
    , orderDirection: desc) {
    tokenId
    block
    amount
    id
  }
}
```
