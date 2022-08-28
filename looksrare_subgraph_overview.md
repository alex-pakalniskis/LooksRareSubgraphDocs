---
sidebar_position: 1
title: Subgraph Introduction
---

# Subgraph

[LooksRare](https://looksrare.org/) uses [The Graph](https://thegraph.com/) to load data from LooksRare contracts without directly querying the blockchain.

[To learn more about the LooksRareExchange contract, please read this documentation.](https://docs.looksrare.org/developers/exchange/LooksRareExchange)


| Name        | Status                                                                                                            | Description                                                                    |
| ----------- | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------ |
| exchange | [?](?) | Tracks volume, royalties for collections, execution strategies, and users of the [LooksRare Exchange](https://docs.looksrare.org/developers/looksrare-exchange-overview). |
| looks-distribution | [?](?)  | Tracks LOOKS and WETH distribution for all users of the LooksRare ecosystem.   |
| royalty-fee-registry | [?](?) | Tracks changes of royalty fee information from the RoyaltyFeeRegistry smart contract.|

<br/>

:::note Querying the subgraph
**The LooksRare subgraph schema is the same on all networks**, and can be found on the following page. For information on structuring Graph queries, read the [Graph docs](https://thegraph.com/docs/en/querying/querying-the-graph/).
:::

## Avoid Rate-Limiting

To use the mainnet Juicebox subgraph without being rate-limited:

1. Create your API key on [Subgraph Studio API Keys](https://thegraph.com/studio/apikeys/).
2. Fund your billing balance on [Subgraph Studio Billing](https://thegraph.com/studio/billing/).
3. Query the mainnet LooksRare subgraph using `https://gateway.thegraph.com/api/<your-api-key>/subgraphs/id/QmQyfYsGcnbjKKBCCatM7LcY6P2PwHANyaeBuxSiRa22TC`.

You can also follow the [Video Tutorial](https://www.youtube.com/watch?v=UrfIpm-Vlgs).

*For more info on Graph query billing, visit [Billing on the Subgraph Studio - The Graph Docs](https://thegraph.com/docs/en/querying/billing/) and [Managing your API Key & Setting your indexer preferences](https://thegraph.com/docs/en/studio/managing-api-keys/).*
