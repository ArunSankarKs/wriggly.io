```solidity
pragma solidity ^0.8.4;

contract Voting {

    string[] public proposals;
    mapping(uint256 => uint256) public votes;
    mapping(address => bool) public voted;

    constructor() {
        proposals = ["Proposal 1", "Proposal 2"];
    }

    function vote(uint256 proposal) public {
      require(!voted[msg.sender],"Already voted");
      require(proposal < proposals.length,"Invalid porposal");
        voted[msg.sender]=true;
        votes[proposal]++;
    }

    function getProposal(uint256 proposal) public view returns (string memory) {
       return proposals[proposal];
    }

    function getVotes(uint256 proposal) public view returns (uint256) {
        return votes[proposal];
    }
    
}

```