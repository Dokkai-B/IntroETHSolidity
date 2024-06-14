# MyToken Smart Contract

This Solidity program demonstrates a basic token contract with mint and burn functionalities. The purpose of this program is to provide an introduction to smart contract development on the Ethereum blockchain.

## Description

This project includes a simple ERC20-like token contract written in Solidity. The contract allows for minting new tokens, burning existing tokens, and keeping track of the total supply and balances of token holders. It serves as a practical example for those new to Solidity and blockchain development.

## Getting Started

### Executing Program

To run this program, you can use Remix, an online Solidity IDE. Follow the steps below to compile and deploy the contract:

1. Go to the Remix website at [https://remix.ethereum.org/](https://remix.ethereum.org/).

2. Create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a `.sol` extension (e.g., `MyToken.sol`). Copy and paste the following code into the file:

    ```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;

    contract MyToken {
        // Public variables to store details about the coin
        string public name = "MyToken";
        string public symbol = "MTK";
        uint256 public totalSupply;

        // Mapping from addresses to balances
        mapping(address => uint256) public balances;

        // Mint function to create new tokens
        function mint(address _to, uint256 _value) public {
            totalSupply += _value;
            balances[_to] += _value;
        }

        // Burn function to destroy tokens
        function burn(address _from, uint256 _value) public {
            require(balances[_from] >= _value, "Balance is not sufficient to burn");
            totalSupply -= _value;
            balances[_from] -= _value;
        }
    }
    ```

3. Compile the code by clicking on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile MyToken.sol" button.

4. Deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

5. Once the contract is deployed, you can interact with it by calling the `mint` and `burn` functions. For example, to mint tokens, call the `mint` function with the desired address and value. To burn tokens, call the `burn` function with the desired address and value.

## Help

For any issues or common problems, consider checking the official Solidity documentation or reaching out to the community on forums like Ethereum Stack Exchange.

```sh
solidity documentation: https://docs.soliditylang.org/en/v0.8.18/
ethereum stack exchange: https://ethereum.stackexchange.com/
