# Protocol Architecture

#### Leveraging the LSP8 Identifiable Digital Asset standard

The **LUKSO Standard Proposal 8 Identifiable Digital Asset** lends itself quite nicely to serving as the foundation for the Hashlists Curation Protocol. LSP8 was designed for creating unique, non-fungible tokens (NFTs). It allows for precise control over individual assets, making it an ideal choice for implementing curated lists, as each entity on the list is represented by its unique token ID, which can itself be mapped to a unique blockchain address. The properties Curated Hashlists inherit from LSP8 are:

1. **Uniqueness of Assets**: Every entry in a curated list is unique. LSP8 provides a way to tokenize and manage these unique assets, representing anything from NFTs to smart contracts to digital profiles.
2. **Trackable Provenance**: By using LSP8, curators can ensure that their lists are verifiable and tamper-proof. Each curated list’s origin, changes, and endorsements are transparent, traceable on the blockchain, and publicly verifiable.
3. **Interoperability**: LSP8 assets can interact seamlessly with other LUKSO standards, such as LSP3 (profile metadata) and LSP9 (vaults), expanding the range of possible interactions within the ecosystem. For instance, curated lists could be integrated into other decentralized applications (dApps), social platforms, or even serve as modules in larger protocols.
4. **Censorship Resistance**: Unlike centralized platforms where curated content can be manipulated or restricted, on-chain curated lists using LSP8 cannot be censored. This ensures that lists remain true to the curator's intent without interference.
5. **Decentralized Ownership and Control**: Curated lists created via LSP8 allow full ownership and control by the individual curator. The list itself becomes a tokenized asset that can be transferred, sold, or shared, giving curators autonomy and direct rewards for their efforts.
