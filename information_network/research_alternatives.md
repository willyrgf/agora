# Researching Alternatives

What are the current alternative solutions available? How they are different from the current draft? Why aren't they fulfilling the market and social needs of such a network? Why aren't they solve all the problems described in the draft?

## Ocean Protocol
- Permissionless publishing of datasets
- Services ???
- Data monetization, not only storage ???
- Compute-to-data: pay to run code on data without receive the data itself
- No derivation/augmentation of data

## OriginTrail Decentralized Knowledge Graph (DKG)
- Publishes "Knowledge Assets" ???
    - RDF/JSON-LD (ontologies/schemas) ???
- Emphasis on structured, discoverable and verifiable information ***
    - bad/inaccurate data gets rejected by the graph's consensus ???
- No market composability (redistribution/augumentation)
- No lineage-royalty mechanics
- Q: Do they try to solve the cloning information problem?
- https://origintrail.io/technology/decentralized-knowledge-graph?utm_source=chatgpt.com

## IPFS + Filecoin
- Content-addressed data identified by hashes
    - Data is chucked, merkleized and identified by Content Identifiers (CID)
- Open market for storage (and retrieval payment ???) by Filecoin
    - Prices are supply-demand driven, retrieval miners compete on latency/bandwidth
- Support relayers/caches economically (retrieval miners)
- No ontology/schema of data (only blobs)
- No market composability (redistribution/augumentation)
- Q: How does Filecoin adds the incentive layer? Can't it be tampered?
- Q: IPFS IPNI (Network Indexer), why is that such a big thing for them?
- https://docs.filecoin.io/basics/how-storage-works/filecoin-and-ipfs?utm_source=chatgpt.com
- https://docs.ipfs.tech/concepts/ipni/?utm_source=chatgpt.com

## Arweave / Permaweb
- Permanent storage (pay once store forever)
- Optional pay-on-access (P3) ***
- No ontology/schema of data (only blobs)
- No market composability (redistribution/augumentation)
- No discoverability

## Ceramic / ComposeDB
- Schemas and models define structured documents ***
- Data is signed and composable across apps ***
- Data + ontology as first-class aspect ***
- No marketplace or payment mechanics
- Replication/pinning economics are external ???
- https://developers.ceramic.network/docs/composedb/core-concepts?utm_source=chatgpt.com

## The Graph
- Network-level metadata extraction for searchable APIs
- Economics incentives for indexers/curators
- Read-only ???
- No arbitrary data/information (restricted on blockchain data)
- No marketplace or lineage-royalty mechanics
- https://messari.io/report/state-of-the-graph-q1-2025?utm_source=chatgpt.com

## Streamr
- Producer/consumer roles ***
- P2P relay network
- Monetized access to data streams ***
    - Use of $DATA token
    - Earn via sponsorship ???
    - Incentives for quality via staking yields ???
- No persistent semantic information (restricted to live streams)
- No ontology-based anti-cloning royalty routing

## AnyLog
- Research prototype, not fully market-deployed
- Decentralized publishing + querying structured data (focus on IoT)
- Publishers upload with custom schemas
- Contractors store/query in SQL ***
- Uses blockchain for metadata ???
- Discoverability from metadata ???
- Payment per query/token shared among producers/contractors
- Incentive reward data that participates in queries (favouring high-quality composable schemas) ***
- Hashing and signatures prevent tamper ***
- No relayers/augumentors
- No preserve incentive via negative price or other mechs
- Paper from 2019, why not implemented? https://www.cidrdb.org/cidr2020/papers/p9-abadi-cidr20.pdf
    - https://chatgpt.com/share/69245725-e4d4-8012-9fdf-3e9467adacd9

## Nevermined (AI-Focused Extension of Ocean)
- Monetizing AI agents APIs/data
- Chained interactions with agents augment/trade data autonomosly
- Micropayments per usage (fiat/crypto)
- No ontology/schema (API only???)


---

## Contrast with nearest alternatives
- OriginTrail (semantic + discovery) + Ocean (market) but no native derivative chain. 
- Filecoin/Arweave (persistence) + The Graph (indexing) but no schema-first information market.

