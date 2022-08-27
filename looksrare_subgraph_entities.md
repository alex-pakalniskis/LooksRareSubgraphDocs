# Subgraph Entities

- [Collection](#collection)
- [ExecutionStrategy](#executionstrategy)
- [User](#user)
- [CollectionDailyData](#collectiondailydata)
- [ExchangeDailyData](#exchangedailydata)
- [ExecutionStrategyDailyData](#executionstrategydailydata)
- [UserDailyData](#userdailydata)
- [RoyaltyTransfer](#royaltytransfer)
- [Transaction](#transaction)

## Collection

| Field                     | Type                                         | Description                                                    |
| ------------------------- | -------------------------------------------- | -------------------------------------------------------------- |
| id                        | ID!                                          |                                                                |
| totalTransactions         | BigInt!                                      | Total transactions for the Collection                          |
| totalTakerBidTransactions | BigInt!                                      | Total transactions where the taker accepted a listed NFT       |
| totalTakerAskTransactions | BigInt!                                      | Total transactions where the taker accepted an offer on an NFT |
| totalVolume               | BigDecimal!                                  | Total ETH Volume for the Collection                            |
| totalTakerBidVolume       | BigDecimal!                                  | Total ETH Volume where the taker accepted a listed NFT         |
| totalTakerAskVolume       | BigDecimal!                                  | Total ETH Volume where the taker accepted an offer on an NFT   |
| totalRoyaltyPaid          | BigDecimal!                                  | Total Royalties paid to the collection                         |
| dayData                   | [CollectionDailyData!](#collectiondailydata) | Daily metrics for the collection                               |
| royaltyTransfers          | [RoyaltyTransfer!](#royaltytransfer)         | Royalty transfers to the collection                            |
| transactions              | [Transaction!](#transaction)                 | Transactions for the collection                                |

## ExecutionStrategy

| Field                     | Type                                                       | Description                            |
| ------------------------- | ---------------------------------------------------------- | -------------------------------------- |
| id                        | ID!                                                        | ...                                    |
| protocolFee               | BigInt!                                                    | Protocol fee (e.g., 500 --> 5%)        |
| totalTransactions         | BigInt!                                                    | Total number of transactions           |
| totalTakerBidTransactions | BigInt!                                                    | Total number of taker bid transactions |
| totalTakerAskTransactions | BigInt!                                                    | Total number of taker ask transactions |
| totalVolume               | BigDecimal!                                                | Total volume (in ETH)                  |
| totalTakerBidVolume       | BigDecimal!                                                | Total taker bid volume (in ETH)        |
| totalTakerAskVolume       | BigDecimal!                                                | Total taker ask volume (in ETH)        |
| dayData                   | [ExecutionStrategyDailyData!](#executionstrategydailydata) | Daily history for execution strategy   |
| transactions              | [Transaction!](#transaction)                               | Transactions for execution strategy    |

## User

| Field                 | Type                                 | Description                               |
| --------------------- | ------------------------------------ | ----------------------------------------- |
| id                    | ID!                                  | ...                                       |
| totalTransactions     | BigInt!                              | Total transactions for a user             |
| totalAskVolume        | BigDecimal!                          | Total volume where the user sold an NFT   |
| totalBidVolume        | BigDecimal!                          | Total volume where the user bought an NFT |
| totalMakerVolume      | BigDecimal!                          | Total volume where the user was the maker |
| totalTakerVolume      | BigDecimal!                          | Total volume where the user was the taker |
| totalVolume           | BigDecimal!                          | Total volume for the user                 |
| totalRoyaltyCollected | BigDecimal!                          | Total royalties collected by the user     |
| dayData               | [UserDailyData!](#userdailydata)     | Users daily metrics                       |
| makerTransactions     | [Transaction!](#transaction)         | Users maker transactions                  |
| takerTransactions     | [Transaction!](#transaction)         | Users taker transactions                  |
| royaltyPayments       | [RoyaltyTransfer!](#royaltytransfer) | Users royalty transactions                |

## CollectionDailyData

| Field                       | Type                       | Description                                       |
| --------------------------- | -------------------------- | ------------------------------------------------- |
| id                          | ID!                        | ...                                               |
| date                        | BigInt!                    | Start date (timestamp)                            |
| collection                  | [Collection!](#collection) | Collection info                                   |
| dailyTransactions           | BigInt!                    | Daily unique transactions                         |
| dailyTakerBidTransactions   | BigInt!                    | Daily unique taker bid transactions               |
| dailyTakerAskTransactions   | BigInt!                    | Daily unique taker ask transactions               |
| dailyVolume                 | BigDecimal!                | Total volume for the day (in ETH)                 |
| dailyTakerBidVolume         | BigDecimal!                | Daily taker bid volume (in ETH)                   |
| dailyTakerAskVolume         | BigDecimal!                | Daily taker ask volume (in ETH)                   |
| dailyVolumeExcludingZeroFee | BigDecimal!                | Daily volume (in ETH) excluding zero-fee strategy |
| dailyRoyalty                | BigDecimal!                | Royalty payment (in ETH)                          |

## ExchangeDailyData

| Field                       | Type        | Description                                       |
| --------------------------- | ----------- | ------------------------------------------------- |
| id                          | ID!         | ...                                               |
| date                        | BigInt!     | Start date (timestamp)                            |
| dailyUsers                  | BigInt!     | Daily unique users                                |
| dailyCollections            | BigInt!     | Daily unique collections traded                   |
| dailyTransactions           | BigInt!     | Daily unique transactions                         |
| dailyTakerBidTransactions   | BigInt!     | Daily taker ask transactions                      |
| dailyTakerAskTransactions   | BigInt!     | Daily taker ask transactions                      |
| dailyVolume                 | BigDecimal! | Daily volume (in ETH)                             |
| dailyTakerBidVolume         | BigDecimal! | Daily taker bid volume (in ETH)                   |
| dailyTakerAskVolume         | BigDecimal! | Daily taker ask volume (in ETH)                   |
| dailyVolumeExcludingZeroFee | BigDecimal! | Daily volume (in ETH) excluding zero-fee strategy |

## ExecutionStrategyDailyData

| Field                     | Type                                     | Description                         |
| ------------------------- | ---------------------------------------- | ----------------------------------- |
| id                        | ID!                                      | ...                                 |
| strategy                  | [ExecutionStrategy!](#executionstrategy) | Execution strategy                  |
| date                      | BigInt!                                  | Start date (timestamp)              |
| dailyTransactions         | BigInt!                                  | Daily unique transactions           |
| dailyTakerBidTransactions | BigInt!                                  | Daily unique taker bid transactions |
| dailyTakerAskTransactions | BigInt!                                  | Daily unique taker bid transactions |
| dailyVolume               | BigDecimal!                              | Daily volume (in ETH)               |
| dailyTakerBidVolume       | BigDecimal!                              | Daily taker bid volume (in ETH)     |
| dailyTakerAskVolume       | BigDecimal!                              | Daily taker ask volume (in ETH)     |

## UserDailyData

| Field                       | Type           | Description                                       |
| --------------------------- | -------------- | ------------------------------------------------- |
| id                          | ID!            | ID                                                |
| date                        | BigInt!        | Start date (timestamp)                            |
| user                        | [User!](#user) | User                                              |
| dailyTransactions           | BigInt!        | Daily unique transactions                         |
| dailyVolume                 | BigDecimal!    | Daily volume (in ETH)                             |
| dailyVolumeExcludingZeroFee | BigDecimal!    | Daily volume (in ETH) excluding zero-fee strategy |

## RoyaltyTransfer

| Field      | Type                       | Description                   |
| ---------- | -------------------------- | ----------------------------- |
| id         | ID!                        | ID                            |
| date       | BigInt!                    | Timestamp of Royalty Transfer |
| block      | BigInt!                    | Block number                  |
| collection | [Collection!](#collection) | Collection                    |
| tokenId    | BigInt!                    | Token Identifier              |
| user       | [User!](#user)             | User                          |
| amount     | BigDecimal!                | Amount received (in ETH)      |

## Transaction

| Field      | Type                                     | Description                           |
| ---------- | ---------------------------------------- | ------------------------------------- |
| id         | ID!                                      | ID                                    |
| date       | BigInt!                                  | Date (timestamp)                      |
| block      | BigInt!                                  | Block number                          |
| collection | [Collection!](#collection)               | Collection                            |
| isTakerAsk | Boolean!                                 | Whether the transaction is a takerAsk |
| strategy   | [ExecutionStrategy!](#executionstrategy) | Execution strategy                    |
| tokenId    | BigInt!                                  | Token Identifier                      |
| price      | BigDecimal!                              | Price (in ETH)                        |
| maker      | [User!](#user)                           | Maker user                            |
| taker      | [User!](#user)                           | Taker user                            |
