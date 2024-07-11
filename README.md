# ERC20-Contract

# ERC20 Token Contract

This is a simple ERC20 token contract implemented in Solidity. The contract allows for the creation, transfer, and burning of tokens. It includes basic functionality such as minting and burning tokens.

## Contract Details

- **Name**: Configurable upon deployment
- **Symbol**: Configurable upon deployment
- **Decimals**: Configurable upon deployment
- **Total Supply**: Dynamic based on minting and burning

## Functions

### `constructor(string memory _name, string memory _symbol, uint8 _decimals)`

Initializes the contract with the provided name, symbol, and decimals.

### `function _transfer(address sender, address recipient, uint256 amount) internal virtual`

Internal function to transfer tokens from one address to another. Emits a `Transfer` event.

### `function _mint(address account, uint256 amount) internal virtual`

Internal function to mint new tokens to the specified account. Emits a `Transfer` event with the `from` address set to the zero address.

### `function _burn(address account, uint256 amount) internal virtual`

Internal function to burn tokens from the specified account. Emits a `Transfer` event with the `to` address set to the zero address.

### `function mint(address to, uint256 amount) external virtual`

Mints new tokens to the specified address. Can be called externally.

### `function burn(uint256 amount) external virtual`

Burns tokens from the caller's address. Can be called externally.

## Events

### `event Transfer(address indexed from, address indexed to, uint256 value)`

Emitted when tokens are transferred, including zero value transfers, as well as minting and burning.

## Usage

1. **Deploy the contract**: Deploy the contract with the desired name, symbol, and decimals.
2. **Minting tokens**: Use the `mint` function to create new tokens and assign them to a specific address.
3. **Transferring tokens**: Transfer tokens from one address to another using the internal `_transfer` function.
4. **Burning tokens**: Use the `burn` function to destroy tokens from the caller's address.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
