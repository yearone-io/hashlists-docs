# Protocol Architecture

<figure><img src="../.gitbook/assets/Screenshot 2024-10-11 at 4.32.51 PM.png" alt=""><figcaption></figcaption></figure>

**Overview of the Hashlists Protocol Architecture**

The Hashlists Protocol is a decentralized user-driven curation system built leveraging LUKSO Standard Proposals to create a modular framework for curating blockchain entities. This document provides a detailed overview of the architecture and its core components, focusing on the three main smart contracts involved: `HashlistsProtocolCollection.sol`, `CuratedListLibrary.sol`, and `CuratedListCollection.sol`. These contracts work together to create and manage curated lists, which are collections of blockchain entities represented as digital assets.

#### Key Components of Hashlists Protocol

1. [**HashlistsProtocolCollection.sol**](https://github.com/yearone-io/hashlists-protocol/blob/main/contracts/HashlistsProtocolCollection.sol)
   * The `HashlistsProtocolCollection.sol` contract is the main entry point for managing collections of curated lists. It extends from LSP8 standards, including `LSP8Enumerable` and `LSP8Burnable`, allowing enumeration and management of unique entries within a curated list.
   * The `mint` function allows new curated lists to be created, each represented by its own address, and emits an event to signal the creation of a new curated list.
   * The contract interacts with `CuratedListLibrary` to deploy new instances of `CuratedListCollection`. This contract is responsible for creating curated lists and managing them as unique tokens. Each curated list is represented as an individual token, providing a high-level view of all curated lists created within the protocol.
2. [**CuratedListLibrary.sol**](https://github.com/yearone-io/hashlists-protocol/blob/main/contracts/CuratedListLibrary.sol)
   * The `CuratedListLibrary.sol` contract serves as a utility library to deploy new instances of curated lists. It provides a reusable function `deployCuratedList` that can be called by other contracts or users to create a new curated list contract.
   * By using a library to deploy curated lists, the protocol maintains a clean separation between the logic for deploying new lists and the core logic for managing collections, enhancing modularity and reusability.
   * This contract abstracts the complexity of deploying new smart contracts, allowing other components of the Hashlists Protocol to focus on higher-level operations.
3. [**CuratedListCollection.sol**](https://github.com/yearone-io/hashlists-protocol/blob/main/contracts/CuratedListCollection.sol)
   * At the core of the Hashlists Protocol are the curated list contracts (`CuratedListCollection`). Each list is a self-contained contract that provides all the functions needed for managing the entries.
   * The `CuratedListCollection.sol` contract represents an individual curated list and is deployed by the `CuratedListLibrary`. It extends `LSP8Mintable`, `LSP8Burnable`, and `LSP8Enumerable`, allowing for minting, burning, and enumeration of unique entries.
   * Each `CuratedListCollection` is an independent instance that allows the curator to manage a specific set of blockchain entities, represented as LSP8 tokens. The curator can add new entries (mint new tokens) and remove existing entries (burn tokens).
   * The contract stores metadata about the curated list, including its name, symbol, and the creator, using LSP4 metadata standards. This ensures that each list is well-documented and easily identifiable within the Hashlists Protocol.
