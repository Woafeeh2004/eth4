# eth4
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract Voting {
    mapping(string => uint256) public votes;
    mapping(address => bool) public hasVoted;

    function vote(string memory candidate) public {
        require(!hasVoted[msg.sender], "Already voted");
        votes[candidate]++;
        hasVoted[msg.sender] = true;
    }
}
