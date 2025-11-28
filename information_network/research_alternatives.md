# Researching Alternatives

What are the current alternative solutions available? How they are different from the current draft? Why aren't they fulfilling the market and social needs of such a network? Why aren't they solve all the problems described in the draft?


---

## OriginTrail Decentralized Knowledge Graph (DKG)
- Publishes "Knowledge Assets"
    - RDF/JSON-LD (ontologies/schemas)
- Emphasis on structured, discoverable and verifiable information
    - bad/inaccurate data gets rejected by the graph's consensus: if discrepancies or contradictions between nodes, the data is flagged and rejected 
- Pay to publish data, not to access or discover it
- No market composability (redistribution/augumentation)
- No lineage-royalty mechanics
- https://origintrail.io/technology/decentralized-knowledge-graph

### 1. Main problem it’s trying to solve
- Need for verifiable, structured knowledge that spans organizations and blockchains (supply chains, credentials, AI inputs)
- Traditional knowledge graphs are siloed, mutable, and lack cryptographic provenance
- DKG is meant to be a shared, multi-stakeholder knowledge layer where “knowledge assets” are:
  - Linked by ontologies
  - Anchored on chain for provenance and tamper evidence

### 2. Did it solve the problem?
- It offers a working decentralized knowledge graph with real deployments (supply chain, Web3/AI, etc.)
- It improves provenance and discoverability for structured data in those contexts
- It does not yet function as a global, default knowledge backbone for AI or the Web:
  - Adoption is modest compared to centralized KGs and vector DBs
  - Fighting misinformation / “cloned” or low-quality information is only partially addressed via provenance and reputation, not magical truth consensus

### 3. Main pain points
- Building and maintaining good ontologies and knowledge graphs is hard even centrally; DKG adds multi-chain + token economics on top
- Incentive structure and node economics need to stay attractive; otherwise decentralization and data availability suffer
- Limited integration with mainstream AI toolchains (most devs use Neo4j, graph DBs, or vector stores)
- Conceptual complexity: devs must understand credentials, KGs, and cryptoeconomics, which slows adoption
- No built-in royalty/lineage market; focuses on verifiability, not economic composability of derived knowledge


---

## Ocean Protocol
- Permissionless publishing of datasets
- Privacy-preserving data sharing
- Services: compute services, algorithms, AI models, or web services that can be tokenized and accessed via the protocol
- Data monetization per access or computation executed using data
- Compute-to-data: pay to run code on data without receive the data itself
- All data stay internal private on the protocol
- No derivation/augmentation of data

### 1. Main problem it’s trying to solve
- Data is locked in private silos and hard to share/monetize safely
- AI/analytics teams struggle to discover, license, and use high-value datasets without breaking privacy or regulation
- Ocean tries to create a permissionless, privacy-preserving data & AI service marketplace: tokenized datasets/algorithms and “compute-to-data” instead of moving raw data

### 2. Did it solve the problem?
- Technically: It provides working primitives (data tokens, marketplaces, compute-to-data, Ocean Market, Ocean Nodes)
- In practice: It hasn’t achieved large-scale data liquidity:
  - Enterprise-grade, high-value datasets are still mostly shared via private contracts, not public data token markets
  - Network effects (enough quality suppliers + enough demand) are still weak
- So it partially solves the technical problem but not the adoption/market-structure problem

### 3. Main pain points
- Marketplace cold-start and data quality; many listings are low-value or poorly described
- Integration complexity with real-world governance, compliance, and data pipelines
- Unclear mapping between immutable control layers and regulations like GDPR’s “right to be forgotten”
- Token, governance, and ecosystem fragmentation (e.g., overlap with other AI+data projects)
- Strong competition from centralized data brokers and vertical AI platforms

---

## IPFS + Filecoin
- Content-addressed data identified by hashes
    - Data is chucked, merkleized and identified by Content Identifiers (CID)
- On IPFS network, free to storage and retrieve (if someone is hosting the data)
- On IPFS+Filecoin, both upload and retrieve are paid with guarantees on data availability
    - Prices are supply-demand driven, retrieval miners compete on latency/bandwidth
- Support relayers/caches economically (retrieval miners)
- IPFS is completely declouped from Filecoin; but they both use same formats of data, so they're interchangeable at data level
- No ontology/schema of data (only blobs)
- No market composability (redistribution/augumentation)
- *Only way to find a data into the network is by having its CID*
- https://docs.filecoin.io/basics/how-storage-works/filecoin-and-ipfs
- https://docs.ipfs.tech/concepts/ipni/

### 1. Main problem it’s trying to solve
- IPFS: make content distribution location-independent and peer-to-peer instead of server-centric URLs
- Filecoin: add a cryptoeconomic storage market so content can be persisted long-term with verifiable proofs (replication, spacetime)
- IPNI solves discovery: quickly find which providers host a given CID

### 2. Did it solve the problem?
- It does provide a widely-used decentralized storage substrate (NFT assets, DWeb content, many dApps)
- But it doesn’t fully replace S3/CDNs for:
  - Guaranteed persistence without pinning contracts
  - Low-latency, highly predictable retrieval across the globe
- It solves the basic technical problem of verifiable, incentivized storage, but not the operational “just works like a cloud provider” problem

### 3. Main pain points
- Persistence is not guaranteed unless someone keeps paying or pinning; data can disappear if all pinning stops
- Retrieval latency and reliability vary by gateway, pinning setup, and network topology
- Operating a Filecoin storage provider is hardware-intensive and protocol-complex (sealing, proofs, collateral)
- Abuse and moderation: content addressing + replication make illegal/harmful content hard to remove; responsibility is unclear
- No built-in semantics; everything is opaque blobs. Higher-level meaning needs separate layers

---

## Ceramic / ComposeDB
- Schemas and models define structured documents
- Data is signed and composable across apps
- Data + ontology as first-class aspect
- No marketplace or payment mechanics
- Replication/pinning economics are external ???
- https://developers.ceramic.network/docs/composedb/core-concepts

### 1. Main problem it’s trying to solve
- Web3 apps still silo user data in their own databases, just like Web2
- Ceramic + ComposeDB aim to provide:
  - A decentralized, append-only data layer with verifiable streams
  - GraphQL-queryable, schema-driven composable app data that multiple apps can reuse
  - DID-based identities that own their data across applications

### 2. Did it solve the problem?
- It provides a credible, working stack for decentralized structured data (schemas, DIDs, GraphQL queries)
- Some projects use Ceramic for identity, profiles, and attestations
- But most Web3 apps still rely on centralized DBs + on-chain state:
  - The “global composable app data” vision is only partially realized
  - Network effects (many apps sharing models) are still weak

### 3. Main pain points
- Developer complexity: new mental model (streams, anchoring, indexes) and tooling vs familiar SQL/NoSQL
- Performance and consistency characteristics differ from traditional DBs; not always a good fit for latency-sensitive use cases
- No native payment/marketplace layer; requires external economics if you want a data market
- Replication/pinning economics are external (nodes must be incentivized or operated by app teams)
- Ecosystem still small; value of composability is limited until many apps share the same models

---

## The Graph
- Network-level metadata extraction for searchable APIs
- Economics incentives for indexers/curators
- Read-only from user perspective
- No arbitrary data/information (restricted on blockchain data)
- No marketplace or lineage-royalty mechanics
- https://messari.io/report/state-of-the-graph-q1-2025

### 1. Main problem it’s trying to solve
- Raw blockchain nodes are bad for complex queries and analytics
- The Graph:
  - Lets developers specify subgraphs (what to index, how to derive entities)
  - Incentivizes a network of indexers and curators to maintain and serve those indexes
- It is effectively a decentralized “read layer” / query infra for on-chain data

### 2. Did it solve the problem?
- For blockchain data querying, it’s close to “yes”:
  - Many DeFi, NFT, DAO apps rely on The Graph to power their APIs
- But:
  - The centralized hosted service is still widely used and can be a single point of failure
  - Full decentralization with smooth economics and UX is still in progress

### 3. Main pain points
- Developer and economic complexity: writing subgraphs, understanding curation, query fee markets, and rewards is non-trivial
- Reliance on centralized hosted services in practice reduces the decentralization benefits and introduces outage risk
- Indexing economics can be inefficient (lots of redundant indexing, coordination issues)
- Limited to blockchain-origin data; arbitrary off-chain data needs separate infrastructure
- No built-in derivative/lineage royalty mechanics; it focuses on indexing, not economic composition of information

---


## Streamr
- Producer/consumer roles
- P2P relay network
- Monetized access to data streams
    - Use of $DATA token
    - Operators earn for delivering data reliable (sponsorship)
    - Publishers can sell the data (API monetization model)
- No persistent semantic information (restricted to live streams)
- No ontology-based anti-cloning royalty routing

### 1. Main problem it’s trying to solve
- Real-time data (IoT, DePIN, live feeds) usually flows through centralized brokers (Kafka, cloud pub/sub)
- Streamr offers:
  - A P2P pub/sub network where each stream has its own overlay network
  - A marketplace for monetizing access to real-time streams using the DATA token and sponsorships

### 2. Did it solve the problem?
- It does provide decentralized real-time data delivery and monetization for some use cases
- It has not displaced centralized brokers as the default solution:
  - Enterprises still prefer proven systems with strong tooling and SLAs
  - The network and economics are still evolving; many deployments are experimental or niche

### 3. Main pain points
- Network maturity and stability: protocol and infra are evolving, which can deter conservative users
- Dependence on EVM chains for payments introduces gas costs and latency for economic actions
- Competes with extremely mature centralized infra (Kafka, Kinesis, Pub/Sub, etc.) that have rich ecosystem tooling
- Incentive model for brokers and quality of service depends on token economics, which are volatile
- No persistent, semantic layer or royalty routing for derived streams; focus is on transport + basic monetization

---

## AnyLog
- Decentralized publishing + querying structured data (focus on IoT)
- Publishers upload with custom schemas
- Contractors store/query in SQL
- Uses blockchain for metadata and use this metadata for discoverability
- Dont pay for publish
- Payment per query/token shared among producers/contractors
    - Incentive reward data that participates in queries (favouring high-quality composable schemas)
- Hashing and signatures prevent tamper
- No relayers/augumentors
- No preserve incentive via negative price or other mechs
- Not permissionless
- Paper from 2019, why not implemented? https://www.cidrdb.org/cidr2020/papers/p9-abadi-cidr20.pdf
    - https://chatgpt.com/share/69245725-e4d4-8012-9fdf-3e9467adacd9

### 1. Main problem it’s trying to solve
- IoT/edge data is fragmented across many devices and organizations; centralizing everything in the cloud is expensive and often impractical
- AnyLog proposes a virtual, decentralized data lake at the edge:
  - Publishers expose data with schemas
  - Contractors store and query data
  - Applications see a logically centralized SQL interface

### 2. Did it solve the problem?
- The research and prototype show that such an architecture is feasible
- However, it has not become a widely adopted standard:
  - Most IoT deployments use centralized cloud services (AWS, Azure, GCP)
  - AnyLog is more of a specialized system with limited production footprint

### 3. Main pain points
- Adoption: mostly a single-vendor + research ecosystem, so perceived risk is high for large enterprises
- Operational complexity of coordinating security, schemas, and performance across heterogeneous edge nodes
- Competition from cloud IoT services that are deeply integrated with existing analytics stacks
- Economic model is more traditional (contracts, licensing) vs open token incentives, which may limit global, permissionless participation
- No built-in support for relayers/augmentors or rich derivative/royalty mechanics

---

## Arweave / Permaweb
- Permanent storage (pay once store forever)
- Optional pay-on-access (P3)
- No ontology/schema of data (only blobs)
- No market composability (redistribution/augumentation)
- No discoverability

### 1. Main problem it’s trying to solve
- Long-term preservation of important content (apps, archives, legal records, NFTs) without trusting a single provider
- Provide a “permanent web” where content and dApp frontends are immutable and always retrievable
- Optional P3 layer adds monetized pay-per-access on top

### 2. Did it solve the problem?
- Technically: yes, it offers an immutable, permanent storage layer that is widely used in some ecosystems (e.g., Solana NFTs, archival projects)
- Economically: “pay once, store forever” is debated; long-term sustainability depends on:
  - AR token price
  - Future storage cost curves
  - Miner incentives over decades
- It is very strong on permanence, weaker on economic certainty and ethical/regulatory handling of immutable data

### 3. Main pain points
- Potential mismatch between one-time fees and the actual long-term cost to store data forever (unfunded liabilities risk)
- Immutability conflicts with privacy laws (e.g., right to be forgotten) and takedown obligations for harmful content
- No native schema or semantic layer; discoverability and composition require external indexing (The Graph-style, search engines, etc.)
- Throughput and UX for writes can be awkward; bundling layers improve this but add complexity
- Miner concentration and long-term incentive alignment remain open questions

---

## Cross-cutting observations
A few patterns that show up across almost all of these projects:
1. They mostly solve the technical problem, not the social/economic one
    - IPFS, Filecoin, Arweave, Ocean, The Graph, Ceramic, Streamr, AnyLog, and Nevermined all have credible protocol designs and implementations
    - The harder part is: getting enough participants to use them, aligning incentives, and fitting into existing legal and enterprise workflows
2. Decentralization vs usability trade-offs
    - The more decentralized and trustless the system, the more you tend to pay in:
      - Developer complexity (subgraphs, ComposeDB schemas, node ops)
      - Operational overhead (pinning, retrievability strategies, incentive tuning)
3. Token economics are both an enabler and a source of fragility
    - Filecoin’s miner economics, Arweave’s “unfunded liabilities”, TRAC staking, GRT curation, DATA bounties, OCEAN tokens: all make these systems possible, but also expose them to volatility, governance fights, and sometimes misaligned incentives
4. Interoperability with mainstream stacks is key
    - Projects that ship good SDKs, GraphQL/SQL interfaces, and clean cloud integrations (e.g., The Graph’s GraphQL, AnyLog’s SQL, Ceramic’s GraphQL via ComposeDB) have an advantage over those that expect devs to work directly with low-level protocols

---

## Contrast with nearest alternatives
- OriginTrail (semantic + discovery) + Ocean (market) but no native derivative chain
- Filecoin/Arweave (persistence) + The Graph (indexing) but no schema-first information market

