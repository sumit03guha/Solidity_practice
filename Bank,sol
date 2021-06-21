// SPDX-License-Identifier: SG
pragma solidity ^0.8.4;

contract Bank {
    uint private value;
    address private owner;
    //uint private amount;
    
    constructor (uint amount) {
        value = amount;
        owner = msg.sender;
    }
    
    modifier ownerFunc {
        require(owner == msg.sender);
        _;
    }
    
    function getBalance() view public returns (uint) {
        return value;
    }
    
    function checkValue(uint amount) view private returns (bool) {
        return (value >= amount);
    }
    
    function withdraw(uint amount) ownerFunc public {
        if (checkValue(amount)) {
        value -= amount;
        }
    }
    
    function deposit(uint amount) ownerFunc public {
        value += amount;
    }
    
    function loan() ownerFunc view public returns (bool) {
        return (value > 0);
    }
}

contract Identity is Bank(160) {
    string private name;
    uint private age;
    
    function setName(string memory nm) public {
        name = nm;
    }
    function setAge(uint ag) public {
        age = ag;
    }
    
    function getName() view public returns (string memory) {
        return name;
    }
    
    function getAge() view public returns (uint) {
        return age;
    }
    
}
