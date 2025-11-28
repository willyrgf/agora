# DRAFT: Causal Information Preserving Decentralized Network

---

## TODO: improving writing and terminology
- permissionless p2p network 
- (schema/ontology + conforming data) -> information
- relayer: caches/redistributes as-is
- augmentor: post-processes, improves, repackages (+producer a new information)
- anti-cloning as a strategy
- "content-addressed, semantic data marketplace with composable resale and royalty routing" or "semantic/ontology-anchored information graph" or "semantic knowledge graph + data marketplace + CDN/retrieval market + built-in derived-asset royalty engine" (could improve on top of this for the tldr)
- is it correct to say that data+ontology == semantic information?
- relayer/augmentor -> distributor and transformer?
    - distributor = caches/serves as-is (filecoin retrieval miner analog)
    - transformer = produces a derived cka and earns a margin
    - cleaner mental model, closer to supply-chain economics
- avoid information cloning -> lineage-locked royalties?
    - claiming about economic capture of origin value, not perfect clone-prevention ???
- negative price -> preservation incentive
- find better term then "lineage-royalty" or "royalty"
    - augmentation chains with cascading payments
- make clearer the programmability problem and solution
- micropayments per usage (fiat??? crypto???)
- most alternatives rely on tokens/staking, not info "fitness"
- pitch: not a better storage layer, not just a marketplace, not just a knowledge graph. but a single protocol that “locks” all four into one composable unit of value.
- "the new internet of information"


## TODO: structure this ideas in the draft
- Better clear definition of the problem
- Hash partial information based on ontology/schema in a hierarchial merkle tree hashing so its easily to search and check the origin of a information
- How would the "negative price to incentive preservation of information" works? Pay only once? Pay per time?
- Clarify derived royalty mechanics based on producer/augumenter requirements such as price (it depends on their configurations, not random market numbers)
- A sketch of how "lineage-royalties" works
- Explain the causal information preserving properties by design
    - This seems to be a huge differential, must explore better
        - Bad or useless information will naturally be vanished from the network
        - Information is only spread into the network when someone have enough interest on it
        - Never pay to upload and might pay to download
- Required to have schema + data + ontology (see https://chatgpt.com/share/6925a6c3-999c-8012-a4a2-489de36d3e9c) 
    - Research on how to do it for non text data format
    - Current solutions connecting and visualizing schema, data and ontology: https://grok.com/share/c2hhcmQtMg_43318bdc-137c-4e2b-a469-f76d3792f1b9


## TODO: problems in the draft that must be solve
- "Hashing semantics (ontology/schemas) prevents cloning"
    - Problems:
        - Someone could reshuffle the structure keeping the information and meaning
    - Conjectures:
        - Hashing partial information based on ontology/schema fields in a hierarchial merkle tree; check proximity of per field hash not equality of full schema hash
- "Download once and serve millions"
    - Problems:
        - What if the AdTube downloaded a content once and played it for millions of people? Would AdTube capture all the value?
    - Conjectures:
        - Might enable composable monetization outside of the network???
        - Wouldn't people always be able to download once and take it off from the network and reproduce it for millions of people/times???
        - Could a producer of a content create a rule that it only streams the content? In a way that it never leaves the content in the node?
        - We could probably have it encrypted in the customer node and it pay per play
- Discover layer scalability
    - Problems:
        - Flood replicating metadata if every "active node" (producer/augumenter) is responsible to keep and serve it
        - Possible spam and/or scale problems
    - Conjectures:
        - A new role in the network for discoverability (need to figure out correct incentives)
- On incentive systems
    - Problems:
        - From where one mine/mint/buy the first tokens?
        - Do we need token to keep a incentive system well rounded?
    - Conjectures:
        - Tokens can be bought from DAO
        - Tokens are mined based on amount of data uploaded and its deepeness/relationness with the network


## What is novel in this idea?
- Protocol-level lineage royalty based on semantic/ontology hashing
    - Closest thing to check: NFT/EIP-2981
- Explicit Augumentor/Relayer/Reseller role with automatic fee composition
    - Ocean allows new listings and datatokens, Filecoin allows retrieval markets, The Graph allows indexer earnings.  But none of these make derived data resale + auto-split payments a first-class, default path
    - “Information assets” can be forked, improved, and resold while keeping original producers paid. This is your cleanest novelty claim
- Negative price as a preservation/spread incentive enforcement for a information
- "Causal power" as a protocol principle: Only information that someone wants to pay for it will persist and be preserved by the network
    

---

## Problem 1
The Internet as a decentralized information network has scatered unorganized data around the world into little pockets behind centralized platforms, data providers, paywalls or non standardized accessibility. When accessible, this data is usually unstructured and meaningless. By this definition, there's no uniform, unified way to transform this unorganized, unstructured data into a organized, structured, meaningful information unifiedly accessible for people, organizations and programs.

## Conjecture 1
An open trustless distributed network composed by nodes, which each node can: (1) as a producer, freely upload information as scheme (structure/ontology) and data (data that conforms into the structure/ontology) and set conditions and price for accessing this information; (2) as consumer, according to the producer specific requirements, download and store information for its own usage; (3) as a relayer or augmentor, relay downloaded and/or post-processed information to another node including it's own conditions and price. 

All information uploaded to the network is hashed and connected to the producer, so the payments for that information can be redirected to the correct node.

For relayer or augmentor of a pre-existing information in the network, when a node request information for it, the requester would pay the producer for the information and the relayer/augmentor for the service, each of them according their settings.

A producer could upload certain information with specific conditions and negative price, which would mean that the producer is paying to make this information spread across the network, preserving it.

This should produce the correct incentives for the network participants to tend to keep the information with causal power, better ontology, structure and quality, slowly spurging or not even distributing simple data or bad information.

For all information produced, a discovery algorithm extract searchable metadata from the data ontology and structure and distribute it across the producers, relayers and augmentors making this metadata information discoverable from any active node of the network.

### Avoid information cloning
To address the problem of a bad actor downloading information from a information-producer and reuploading it in a new node as a bad-actor-new-producer: use the ontology and structure of the information to generate hashes associating the information with its producer, redirecting the payments for this information to the correct producer independently of who last uploaded that information into the network. The only way around this would be modifying the information so it generates new hashes, with would tamper with the information quality and accuracy making it naturally less valuable, less causal, less preserved onto the network.

### Information discoverability 
Every active node (producer, relayer and augmentor) must be available to receive discoverable metadata from others active node, and server this information via a searchable endpoint to eventual consumers.
<!-- CHECK: might be a good idea to add a neutral network node for metadata/searchability/discoverability -->

### Examples
#### Market Information
Its simple to get the price of an asset right now like BTC as a human. But it's actually challenging to get the price of BTC in 5 min window for the last 10 years. It's way more challenging to do this for a collection of assets in different time windows.
Although these information exist in many internal databases of companies, you can't easily access and download it in a programmatically way. It seems a obvious good candidate of data to be organize as information, uploaded and distributed in this network.
1. CoinMarket.com:
A data market company called CoinMarket collects price information for multiple time windows for all widely traded cryptocurrencies in exchanges, decentralized and centralized ones, they sell a monthly paid subscription to access the API that has this data available. The business doesn't go so well for a few reasons: a paywall with multiple monthly plans to decide, the monthly/annually lock-in, and human required setup for access the information, not many ways to compose and reuse the data.
So the company decide to pivot and start to publish the data into this network: It now has the information in a free and open market with standardize accessibility and payment method, payment by demand, no month or annual lock in, other nodes (augumenters) can improve this information and resell it, before with only the price, now with volume and volatility. A third node, also augumenter, could improve on it and attach technical analysis information, reselling compensing each one of the tree with what they required as price per information. 

#### Content Creator: Freedom and Monetization
Once a certain content is uploaded to the network, by a producer, it's available for any customer node to be downloaded following the conditions of the producer, like price for example.
Usually a end customer, like someone that watches YouTube won't set up a node and a wallet to pay the producer for the content to then download it and watch locally in its machine.
But we can envisage a few possible scenarios that a open network enables even better accessibility and freedom of choice for the customer. Also enabling different models of monezation for the content creator.

Four different third-party companies build specific frontend for the end customers:
1. AdTube.com:
A advertisement monetization model-based video player frontend that enables end customers to watch videos for free, they just need to watch some advertisements before and during the watching experience.
2. SigTube.com:
A monthly-based signatured monetization model video player frontend that enables end customers to watch videos in full HD, high quality, high speed for a cheap monthly payment.
3. FreeTube.com:
A freedom-of-speech-first censorship-resistance video player frontend that enables end customers to watch ANY sort of videos available.
4. SafeTube.com:
A politically-correct-safe-oriented video player frontend that enables the end customers to watch diverse content.

All of these four new platforms could coexist on top of the same network distributing (or not) the same content, monetizing in their own way to pay the content.

