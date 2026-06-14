# Foundation GraphQL API

## Description

Foundation was a creator-focused NFT marketplace built on Ethereum that enabled digital artists to mint, showcase, and auction unique digital artworks. The platform exposed a GraphQL API via The Graph protocol, indexing all on-chain activity from Foundation smart contracts on Ethereum mainnet. Foundation shut down its marketplace in April 2026, but the subgraph continued indexing historical on-chain data and may remain accessible for historical queries.

## Endpoint

- **Subgraph endpoint**: `https://api.thegraph.com/subgraphs/name/f8n/fnd`
- **Explorer**: https://thegraph.com/hosted-service/subgraph/f8n/fnd

## Documentation

- GitHub organization: https://github.com/f8n
- Protocol repository: https://github.com/f8n/fnd-protocol
- Schema source: https://github.com/f8n/fnd-protocol/blob/main/subgraph/schema.graphql
- Examples repository: https://github.com/f8n/fnd-protocol-examples

## GraphQL Support

Foundation's GraphQL API is a subgraph deployed on The Graph's hosted service. It provides read-only query access to all indexed Foundation marketplace activity including:

- NFT minting, transfers, and ownership
- Auction creation, bidding, and finalization
- Buy-now listings and acceptances
- Offers (made, accepted, canceled, expired)
- Private sales
- Fixed-price sale drops and mints
- Percent split revenue sharing contracts
- FETH (Foundation ETH) escrow balances
- Full event history per NFT via NftHistory

The schema uses entity types following The Graph's subgraph conventions. All monetary values are denominated in ETH as `BigDecimal`. Timestamps are Unix epoch seconds as `BigInt`. Relationships use `@derivedFrom` for reverse lookups.

## Notes

- Foundation shut down its marketplace in April 2026; historical subgraph data remains queryable
- The subgraph was maintained in the `f8n/fnd-protocol` monorepo under `subgraph/`
- Smart contracts remain deployed on Ethereum mainnet and are accessible via RPC
- No authentication is required to query the subgraph endpoint
