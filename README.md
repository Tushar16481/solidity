#MyToken

This Solidity program is a simple token contract that demonstrates basic token functionality, such as minting and burning tokens. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how token contracts work.

##Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract allows users to mint new tokens and burn existing tokens. It keeps track of token balances and the total supply. This program serves as a straightforward introduction to token contract programming and can be used as a stepping stone for more complex projects in the future.



##Getting Started

###Executing Program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at Remix IDE.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:



// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract MyToken {
    // Public variables to store the token details 
    string public tokenName = "gold";
    string public tokenAbbrv = "coin";
    uint256 public totalSupply;

    // Mapping from address to balance
    mapping(address => uint256) public balances;

    // Event for minting tokens
    event Mint(address indexed to, uint256 value);

    // Event for burning tokens
    event Burn(address indexed from, uint256 value);

    // Mint function to create new tokens
    function mint(address _to, uint256 _value) public {
        require(_to != address(0), "Cannot mint to zero address");
        totalSupply += _value;
        balances[_to] += _value;
        emit Mint(_to, _value);
    }

    // Burn function to destroy tokens
    function burn(address _from, uint256 _value) public {
        require(balances[_from] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_from] -= _value;
        emit Burn(_from, _value);
    }
}


  
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the mint and burn functions. Click on the "MyToken" contract in the left-hand sidebar, and then you can interact with the functions. For example, to mint tokens, enter the address and amount, and click on the "mint" button. Similarly, to burn tokens, enter the address and amount, and click on the "burn" button.

##Authors

Metacrafter Tushar

@Tushar_16481

##License

This project is licensed under the MIT License.
