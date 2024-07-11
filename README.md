# ERC20-Contract

# ERC20 Token Contract

This is a simple ERC20 token contract written in Solidity. It includes basic functionalities such as transferring tokens, minting new tokens, and burning existing tokens. The contract is designed to be deployed on the Ethereum blockchain and is compatible with the Remix IDE for easy deployment and testing.

## Features

- **Transfer tokens:** Allows users to transfer tokens to other addresses.
- **Mint tokens:** Allows the creation of new tokens.
- **Burn tokens:** Allows the destruction of tokens.
- **ERC20 standard compliance:** Implements essential ERC20 functionalities.

## Prerequisites

- **Solidity compiler version:** ^0.8.24
- **Remix IDE:** Recommended for deploying and testing the contract.

## Contract Details

### Variables

- `totalSupply`: The total supply of the token.
- `balanceOf`: A mapping that keeps track of each address's token balance.
- `name`: The name of the token.
- `symbol`: The symbol of the token.
- `decimals`: The number of decimals the token uses.

### Events

- `Transfer(address indexed from, address indexed to, uint256 value)`: Emitted when tokens are transferred, minted, or burned.

### Functions

- `constructor(string memory _name, string memory _symbol, uint8 _decimals)`: Initializes the contract with the token name, symbol, and decimals.
- `_transfer(address sender, address recipient, uint256 amount)`: Internal function to handle token transfers.
- `_mint(address account, uint256 amount)`: Internal function to mint new tokens.
- `_burn(address account, uint256 amount)`: Internal function to burn tokens.
- `mint(address to, uint256 amount)`: External function to mint new tokens.
- `burn(uint256 amount)`: External function to burn tokens from the caller's account.

## Usage

1. **Deploying the Contract:**

   - Open the Remix IDE.
   - Copy and paste the contract code into a new Solidity file.
   - Compile the contract with the Solidity compiler version ^0.8.24.
   - Deploy the contract, providing the required constructor parameters (`name`, `symbol`, and `decimals`).

2. **Minting Tokens:**

   - Call the `mint` function with the recipient address and the amount of tokens to be minted.

3. **Burning Tokens:**

   - Call the `burn` function with the amount of tokens to be burned from the caller's account.

4. **Transferring Tokens:**

   - Tokens can be transferred between accounts using the `_transfer` function internally. The contract emits a `Transfer` event on successful transfers.

## Example

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.24;

contract MyToken is ERC20 {
    constructor() ERC20("MyToken", "MTK", 18) {
        // Mint initial supply
        _mint(msg.sender, 1000000 * 10 ** uint256(decimals));
    }
}
```

Deploying the `MyToken` contract will create a new ERC20 token with the name "MyToken", symbol "MTK", and 18 decimals. It will also mint an initial supply of 1,000,000 tokens to the deployer's address.

## License

This project is licensed under the MIT License.
