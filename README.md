# Mytoken.sol
In this video, I will explain the second project for Solidity beginners. The project focuses on building a token and covers topics such as creating public variables for storing coin details, using string variables for token name and abbreviation, and assigning a total supply. I will also demonstrate how to create a mint function to generate tokens and a burn function to decrease token amounts. Throughout the video, I will provide examples and explanations to help you understand the concepts. No action is required from you, this video is for educational purposes only.
Introduction
Creating Public Variables
Assigning Token Name and Abbreviation Assigning Total Supply
Creating a Mapping of Addresses
Implementing the Mint Function
Increasing Total Supply and Balance
Implementing the Burn Function
Conclusion

CODE
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
    string public tokenName = "META";
    string public tokenAbbruv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn (address _address, uint _value) public{
        if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances [_address] -=_value;
    }
}
}
