# Assessment-3

This repository contains the source code for the Oni Token (0T), an ERC-20 compliant token on the Ethereum blockchain. The token is created using the OpenZeppelin ERC-20 implementation and includes functionalities for minting and burning tokens.
## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has multiple functions. Namely mint and burn. Mint adds to the total supply depending on the account indicated and burn destroys the token depending on the amount specified.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. 
Save the file with a .sol extension. Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT 
pragma solidity ^0.8.23;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol"; 

contract oniToken is ERC20 {
    // Constructor to initialize the ERC-20 token with a name and symbol,
    // and mint an initial supply to the contract deployer.
    constructor() ERC20("Oni Token", "0T") {
        _mint(msg.sender, 1000000 * 10**decimals());
    }

    // Function to allow the contract owner to mint new tokens and assign them to a specified address.
    // This function is public, allowing anyone to call it.
    function mint(address to, uint256 amount) public {
        _mint(to, amount);
    }

    // Function to allow the burning (destruction) of tokens by the token holder.
    // The amount parameter specifies the number of tokens to be burned.
    // This function is public, allowing anyone to burn their own tokens.
    function burn(uint256 amount) public {
        _burn(msg.sender, amount);
    }
}

```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18" (or another compatible version), and then click on the "Compile reqasrev.sol" button. 

The button name can vary depending on the file name that you designated when creating the file of the code.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the contract with the same name of the file you have just compiled (e.g if your file has the name "HelloWorld.sol" the option to click should be "HelloWorld") from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn functions. 

Automatically there will be 100,000 with 18 0's following behind it as the overall balance.

To create more specify the address that will be minted to and the amount in the mint function.

To see the total amount you have all you would need to click on is balance.

To destroy or burn token specify the amount and burn the tokens by clicking burn.

Additional functions are the decimals, name, symbol, and total supply. 
In order these do the following: show the amount of decimals, show the name of the token, show the symbol of the token, show off the total supply.

## Authors

Contributors names and contact info
Gavinno Othello C. Angeles
email me at: 201911104@fit.edu.ph


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
