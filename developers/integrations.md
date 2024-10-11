# Integrate Curated Lists

### On chain and off chain

To refer to the contents of a curated list in your smart contract you can simply rely on all the methods available under [LSP8IdentifiableDigitialAsset](https://github.com/lukso-network/LIPs/blob/main/LSPs/LSP-8-IdentifiableDigitalAsset.md#interface-cheat-sheet) and its [Enumerable](https://github.com/lukso-network/lsp-smart-contracts/blob/develop/packages/lsp8-contracts/contracts/extensions/LSP8Enumerable.sol) extension, with the target address being the curated lists' address on the blockchain.

Entry ids in a curated list are stored as `bytes32` so in order to check if a particular blockchain address is an entry within a curated you'd first pad the address with 0s and then rely on the `getOperatorsOf(tokenId)` [method](https://github.com/lukso-network/LIPs/blob/main/LSPs/LSP-8-IdentifiableDigitalAsset.md#getoperatorsof).&#x20;

If you want to read all the addresses of the entries in a list, you can fetch the `totalSupply()` and then using that result and the `tokenAt(uint256 index)` [method](https://github.com/lukso-network/lsp-smart-contracts/blob/develop/packages/lsp8-contracts/contracts/extensions/LSP8Enumerable.sol#L29C14-L29C36), fetch the address for the full set.

For some possible usecases relying on curated lists please refer to: [Curated Lists & Their Use Cases](../getting-started/editor.md).

#### Solidity Example

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

// Example Solidity contract to integrate with a curated list
import {LSP8Enumerable} from "@lukso/lsp-smart-contracts/contracts/LSP8IdentifiableDigitalAsset/extensions/LSP8Enumerable.sol";

contract IntegrateCuratedList {
    function isAddressInCuratedList(address curatedListAddress, address targetAddress) public view returns (bool) {
        // Pad the target address with zeros to create the token ID
        bytes32 tokenId = bytes32(uint256(uint160(targetAddress)));
        
        // Instantiate the curated list contract instance
        LSP8Enumerable curatedList = LSP8Enumerable(curatedListAddress);
        
        // Check if the target address is an operator of the token ID
        address[] memory operators = curatedList.getOperatorsOf(tokenId);
        return operators.length > 0;
    }

    function getAllEntries(address curatedListAddress) public view returns (address[] memory) {
        // Instantiate the curated list contract instance
        LSP8Enumerable curatedList = LSP8Enumerable(curatedListAddress);
        
        // Get total number of entries in the list
        uint256 totalEntries = curatedList.totalSupply();
        
        // Initialize an array to hold all addresses
        address[] memory entries = new address[](totalEntries);
        
        // Fetch all addresses using tokenAt method
        for (uint256 i = 0; i < totalEntries; i++) {
            bytes32 tokenId = curatedList.tokenAt(i);
            entries[i] = address(uint160(uint256(tokenId)));
        }
        return entries;
    }
}
```

#### JS/Typescript Example

```typescript
// Example TypeScript calls to interact with curated lists
import { ethers } from "ethers";
import LSP8Enumerable from '@lukso/lsp8-contracts/artifacts/LSP8Enumerable.json';

// Instantiate provider and signer
const provider = new ethers.providers.JsonRpcProvider("<RPC_URL>");
const signer = provider.getSigner();

// Function to check if an address is in a curated list
async function isAddressInCuratedList(curatedListAddress: string, targetAddress: string): Promise<boolean> {
  const curatedListContract = new ethers.Contract(curatedListAddress, LSP8EnumerableABI, provider);
  const tokenId = ethers.utils.hexZeroPad(targetAddress, 32);
  const operators = await curatedListContract.getOperatorsOf(tokenId);
  return operators.length > 0;
}

// Function to get all entries from a curated list
async function getAllEntries(curatedListAddress: string): Promise<string[]> {
  const curatedListContract = new ethers.Contract(curatedListAddress, LSP8EnumerableABI, provider);
  const totalSupply = await curatedListContract.totalSupply();

  const entries: string[] = [];
  for (let i = 0; i < totalSupply; i++) {
    const tokenId = await curatedListContract.tokenAt(i);
    const entryAddress = ethers.utils.getAddress(tokenId.slice(0, 42));
    entries.push(entryAddress);
  }
  return entries;
}
```
