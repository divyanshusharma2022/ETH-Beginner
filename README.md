
---

# MyToken Smart Contract

This repository contains the `MyToken` smart contract, a basic implementation of an ERC20-like token on the Ethereum blockchain. The contract includes functionality for minting and burning tokens and tracks the balances of token holders.

## Requirements

1. **Public Variables**
   - `tokenName`: The name of the token.
   - `tokenAbbrv`: The abbreviation or symbol of the token.
   - `totalSupply`: The total supply of tokens.

2. **Mapping**
   - `balances`: A mapping from addresses to their respective balances.

3. **Functions**
   - `mint`: Increases the total supply of tokens and updates the balance of the specified address.
   - `burn`: Decreases the total supply of tokens and updates the balance of the specified address, ensuring that the address has enough tokens to burn.

## Contract Details

### Public Variables

- `string public tokenName = "META";`
- `string public tokenAbbrv = "MTA";`
- `uint public totalSupply = 0;`

### Mapping

- `mapping (address => uint) public balances;`

### Mint Function

The `mint` function increases the total supply of the token and the balance of a given address.

```solidity
function mint (address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
```

### Burn Function

The `burn` function decreases the total supply of the token and the balance of a given address, provided that the address has enough tokens to burn.

```solidity
function burn (address _address, uint _value) public {
    if(balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```

## License



## Getting Started

To get started with this contract, you can deploy it using any Ethereum development environment like Remix, Truffle, or Hardhat.

### Prerequisites

- Solidity ^0.8.0
- Ethereum development environment (Remix, Truffle, Hardhat, etc.)

### Deploying the Contract

1. Open your preferred Ethereum development environment.
2. Copy the contract code into a new Solidity file.
3. Compile the contract.
4. Deploy the contract to your desired Ethereum network (local, testnet, or mainnet).

### Interacting with the Contract

Once deployed, you can interact with the contract's functions to mint and burn tokens and check balances. For example:

- **Mint Tokens:**

  ```solidity
  contractInstance.mint("0xYourAddress", 100);
  ```

- **Burn Tokens:**

  ```solidity
  contractInstance.burn("0xYourAddress", 50);
  ```

- **Check Balance:**

  ```solidity
  contractInstance.balances("0xYourAddress");
  ```

## Contributing

Feel free to fork this repository and make contributions. Pull requests are welcome.

---


