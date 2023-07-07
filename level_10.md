```solidity
pragma solidity ^0.8.4;

contract Solution {
    // TODO: Create event here
    event Transfer(address indexed to, uint256 amount);

    function transfer(address payable _to, uint256 _amount) public {
        require(_amount <= address(this).balance,'Insufficient balance');
        // TODO: transfer ether here
        _to.send(_amount);
        emit Transfer(_to,_amount);
        // TODO: emit event here
    }

    function getBalance(address payable _address) public payable returns (uint256) {
        return _address.balance;
    }
}

```