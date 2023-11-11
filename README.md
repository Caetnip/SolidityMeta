# Solidity Project

The "MyToken" smart contract is a fundamental example of a cryptocurrency token in Solidity. It showcases the essential features of token creation, including minting to increase the total supply and user balances, and burning to reduce the total supply while maintaining balance integrity. This contract is an excellent starting point for those exploring token development in Solidity.

## Description

This project consists of a simple Ethereum smart contract written in Solidity. The contract represents a basic cryptocurrency token and includes functionality for minting and burning tokens. Additionally, it stores token details such as the token name, abbreviation, and total supply.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public toeknName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public{
        if (balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
        
    }

}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18", and then click on the "Compile SolidityProject.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Next is click on "Deploy" and go to "Deployed Contracts" and run the code first copy "Account" and paste it on the address so when minting and burning the token it will diplay it.
## Help

Any advise for common problems or issues.
```
command to run if program contains helper info
```

## Authors

Jan Miguel A. Pinlac @Caetnip


## License

This project is licensed under the [Jan Miguel A. Pinlac] License - see the LICENSE.md file for details
