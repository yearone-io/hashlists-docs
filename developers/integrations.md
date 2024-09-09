# Integrate Curated Lists

### On chain and off chain

To refer to the contents of a curated list in your smart contract you can simply rely on all the methods available under [LSP8IdentifiableDigitialAsset](https://github.com/lukso-network/LIPs/blob/main/LSPs/LSP-8-IdentifiableDigitalAsset.md#interface-cheat-sheet) and its [Enumerable](https://github.com/lukso-network/lsp-smart-contracts/blob/develop/packages/lsp8-contracts/contracts/extensions/LSP8Enumerable.sol) extension, with the target address being the curated lists' address on the blockchain.

Entry ids in a curated list are stored as `bytes32` so in order to check if a particular blockchain address is an entry within a curated you'd first pad the address with 0s and then rely on the `getOperatorsOf(tokenId)` [method](https://github.com/lukso-network/LIPs/blob/main/LSPs/LSP-8-IdentifiableDigitalAsset.md#getoperatorsof).&#x20;

If you want to read all the addresses of the entries in a list, you can fetch the `totalSupply()` and then using that result and the `tokenAt(uint256 index)` [method](https://github.com/lukso-network/lsp-smart-contracts/blob/develop/packages/lsp8-contracts/contracts/extensions/LSP8Enumerable.sol#L29C14-L29C36), fetch the address for the full set.

For some possible usecases relying on curated lists please refer to: [Curated Lists & Their Use Cases](../getting-started/editor.md).
