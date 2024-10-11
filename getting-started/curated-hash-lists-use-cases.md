# Curated (Hash)Lists Use Cases

A **curated (hash)list** is a collection of entities or assets, identifiable through blockchain addresses, selected and organized by an individual or group based on specific criteria. Curators make choices that reflect their preferences, expertise, or purpose, allowing them to filter and highlight content for others. This concept can be applied both on-chain (relevant to other on-chain protocols/contracts) and off-chain (relevant to user interfaces and applications without requiring on-chain transactions), with a broad range of uses depending on the context.

***

#### **On-Chain Uses:**

On-chain uses involve the Hashlists Protocol being directly referenced and utilized by other smart contracts and blockchain protocols. These interactions occur entirely on the blockchain, enabling automated, trustless, and verifiable operations without off-chain dependencies.

1. **Access Control and Permissions:**
   * **Example:** A decentralized application (DApp) smart contract references a curated hashlist to manage access to premium features or restricted areas within the DApp. Only addresses included in the hashlist can invoke certain functions or access specific data.
   * **Purpose:** To enforce permissions and roles directly within smart contracts, ensuring that only authorized users can perform certain actions.
2. **Protocol-Level Whitelisting:**
   * **Example:** A DeFi protocol uses a hashlist to whitelist tokens or contracts that are considered safe and audited. Before allowing interactions with any external token or contract, the protocol checks if the address is included in the hashlist.
   * **Purpose:** To enhance security by preventing interactions with unauthorized or potentially malicious contracts.
3. **Automated Compliance and Regulatory Adherence:**
   * **Example:** A compliance-focused smart contract references a hashlist of sanctioned or blacklisted addresses. The contract automatically blocks transactions involving these addresses to comply with regulatory requirements.
   * **Purpose:** To embed compliance checks directly into smart contract logic, reducing the need for manual oversight.
4. **Governance and Voting Systems:**
   * **Example:** A DAO (Decentralized Autonomous Organization) uses a hashlist to define eligible voters. Only addresses listed in the hashlist can participate in governance decisions, ensuring that only recognized members have a say in the organization's direction.
   * **Purpose:** To manage membership and voting rights within the DAO transparently and efficiently.
5. **Reward Distribution and Incentive Programs:**
   * **Example:** A smart contract distributing staking rewards references a hashlist of qualified stakers. The contract automatically calculates and distributes rewards only to addresses included in the hashlist.
   * **Purpose:** To streamline reward mechanisms by automating eligibility checks and distributions.

***

#### **Off-Chain Uses:**

Off-chain uses pertain to applications and user interfaces that utilize the data from the Hashlists Protocol without requiring on-chain transactions. These uses are especially relevant for enhancing user experiences, providing personalization, and aggregating data for analysis or display purposes.

1. **User Interface Personalization:**
   * **Example:** A wallet application reads hashlists to highlight or prioritize contacts and addresses that are part of specific curated lists, such as trusted traders or frequent transaction partners.
   * **Purpose:** To improve user experience by making interactions with important contacts more accessible.
2. **Content Curation and Discovery:**
   * **Example:** A decentralized social media platform's UI uses hashlists to curate content feeds. Users can choose to see posts only from addresses included in certain hashlists, such as verified creators or topic-specific contributors.
   * **Purpose:** To filter and personalize content without needing on-chain transactions for each interaction.
3. **Reputation Indicators:**
   * **Example:** An NFT marketplace displays badges or trust scores next to sellers' profiles based on their inclusion in reputable hashlists, such as verified artists or certified collectors.
   * **Purpose:** To build trust among users by providing visual indicators of reputation and credibility.
4. **Analytics and Market Research:**
   * **Example:** Data analytics platforms aggregate and analyze hashlists to provide insights into market trends, such as the growth of active addresses in a particular sector or the engagement levels of certain communities.
   * **Purpose:** To inform businesses and users with valuable market data without interacting with the blockchain for each query.
5. **Cross-Platform Identity Verification:**
   * **Example:** A service that requires identity verification checks if a user's Universal Profile is included in specific hashlists recognized as verified identities.
   * **Purpose:** To streamline verification processes by leveraging existing curated lists of verified users.

***

**Examples of Existing Curated (Hash)lists:**

*   **LUKSO Builders Hashlist:**

    * **Description:** A curated list of Universal Profile addresses belonging to builders in the LUKSO community.
    * **Potential On-Chain Use:** Smart contracts can reference this hashlist to grant builders exclusive access to beta features, participate in testnets, or receive special rewards for their contributions, etc.
    * **Potential Off-Chain Use:** Applications and websites can display this list to promote collaboration, highlight community contributions, and facilitate networking without requiring users to perform on-chain transactions.



<figure><img src="../.gitbook/assets/Screenshot 2024-10-11 at 5.16.49 PM.png" alt="" width="375"><figcaption><p><a href="https://hashlists.xyz/curated-lists/42/0x7ccfa17e6a23965ab77a6257418129127e6cfbbe">View Curated List</a></p></figcaption></figure>

* **Gitcoin Grants Community Round Contributors Hashlist:**
  * **Description:** A hashlist of contributors' addresses to the Gitcoin Grants Community round that supported the development of the hashlists protocol.
  * **Potential On-Chain Use:** Gift airdrops, early access to certain features, governance.
  * **Potential Off-Chain Use:** Projects can acknowledge supporters on their websites or applications by referencing this hashlist, fostering a sense of community and transparency.

<figure><img src="../.gitbook/assets/image.png" alt="" width="345"><figcaption><p><a href="https://hashlists.xyz/curated-lists/42/0x3f8742f39bb84c711806e1594e213907ed47f4b2">View Curated List</a></p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (2).png" alt="" width="353"><figcaption><p><a href="https://hashlists.xyz/curated-lists/42161/0x65c15b177ca89c37ffb3933e486b3a7fa75e58f3">View Curated List</a></p></figcaption></figure>

***

In summary we can see that the Hashlists Protocol offers versatile application integration possibilities:

* **On-Chain Uses:** Directly integrate with smart contracts and protocols to automate processes, enforce permissions, and enhance security. These uses involve transactions and interactions that occur entirely on the blockchain.
* **Off-Chain Uses:** Enhance user interfaces and applications by utilizing hashlist data for personalization, reputation management, and content curation without the need for on-chain interactions. This approach avoids transaction costs and latency associated with blockchain operations.
