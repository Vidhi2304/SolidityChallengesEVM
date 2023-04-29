# Create a Token

Hi everybody, here I have created a solidity smart contract that creates a token for us using the mint and burn function.

## Description

The solidity code is a very simple one, it contains three public variables of string and uint data type. Then we have mapped addresses to unsigned integer. After this we have two functions, mint, that mints tokens. And burn function, that burns tokens. We can set how many tokens we want to mint or burn using the value argumnt.

### Executing program

This program can be executed in the REMIX IDE very easily. We just copy the code from here and paste in the editor. After that, we compile the code, and just deploy it. After that our smart contract will have been deployed. We'll be able to see all the functionalities as explained in the video there.

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
    string public tokenname = "VIDHI"; 
    string public tokenAbbrv = "VID"; 
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value; 
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public { 
        if (balances[_address] >= _value) {
            totalSupply -= _value; 
            balances[_address] -= _value;
        }
    }
}
```

## License

This project is licensed under the MIT License
