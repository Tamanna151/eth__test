# My token smart contract
MyToken is a simple ERC-20 like token implemented in Solidity. The contract includes functionalities to mint and burn tokens. It also maintains a mapping of addresses to their respective balances
 # Description
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
  # # Getting Started
  ### Execting program
 // SPDX-License-Identifier: MIT
pragma solidity >=0.6.12 <0.9.0;

contract My Token {

    // public variables here
    string public tokenName = "Tamanna";
    string public tokenAbbrv = "Singh";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;


    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
     function burn(address _address, uint _value) public {
        if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }
    

}
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file // SPDX-License-Identifier: MIT pragma solidity >=0.6.12 <0.9.0;
Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "TOKEN" contract from the dropdown menu, and then click on the "Deploy" button.
