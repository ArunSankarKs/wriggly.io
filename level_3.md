 ``` solidity
 pragma solidity ^0.8.4;

contract Solution {
    struct Item {
        string name;
        uint256 price;
    }

    Item[] public inventory;
    address public owner;

    constructor() {
        owner = msg.sender;
    }

    function addItemToInventory(
        string memory _name,
        uint256 _price
    ) public onlyOwner {
       Item memory newItem = Item(_name, _price);
       inventory.push(newItem);
    }

    modifier onlyOwner() {
        _;
    }

    function getInventory() public view returns (Item[] memory) {
        return inventory;
    }

    function clearInventory() private onlyOwner {
        delete inventory;
    }
}

```