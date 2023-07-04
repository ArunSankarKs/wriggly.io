 ```solidity
 pragma solidity ^0.8.4;

contract Gas {
    uint public c = 1;

    function calculateGas() external returns(uint _gasUsed) {
        uint gas = gasleft();
        ++c;
      return gas - gasleft();
    }
}
 ```