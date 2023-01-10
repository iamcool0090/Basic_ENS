# Basic_ENS

Note:This contract was fully written by Me
You can compare the bytecode of this contract

This is a smart contract written in the Solidity programming language for a simple name service (SNS) system on the Ethereum blockchain. The contract allows users to register domain names with the ".uwu" top-level domain (TLD) and pay a set price (in gwei) to do so. It also allows users to resolve registered domain names to their corresponding Ethereum address and transfer ownership of those domain names to other Ethereum addresses.

When a user wants to register a new domain name, they can call the SelfregisterDom() function and pass in the desired domain name as a string. The function then checks that the domain name ends with ".uwu" and contains only one period. If these conditions are not met, the function reverts with an appropriate error message. The function also checks if the domain name is already taken by another user by looking for a matching hashed version of the domain name in the contract's storage. If the domain name is available, the function checks that the user has sent enough value (in gwei) with their transaction to pay the set price and if so, it adds the user's Ethereum address and the hashed version of the domain name to the contract's storage.

Users can resolve a domain name to an Ethereum address by calling the resolve() function and passing in the domain name as a string. The function will check that the domain name ends with ".uwu" and again contain only one period. If these conditions are not met, the function reverts with an appropriate error message. It then looks for a matching hashed version of the domain name in the contract's storage and if found, it returns the corresponding Ethereum address. If no match is found, the function reverts with an error message.

The withdraw() function allows the owner of the contract (as determined by the address that deployed the contract) to withdraw all ether in the contract's balance. The transfer_ownership() function allows the current owner to transfer ownership of the contract to a different Ethereum address. The transfer_domain() function allows a user to transfer ownership of a registered domain name they own to a different Ethereum address. If the domain name is not found, or if the user calling the function is not the current owner of the domain name, the function reverts with an appropriate error message.

It's worth noting that this is an undocumented version, and that the version is using single resolver, where the different smart contract could be used for different things and a different resolver to handle it. There's also a commented out v=0.0.1 which could imply that this is a very early version of the smart contract.
It is also worth noting that the contract is not sharding and depending on the use case and scale of the project, it could create performance issues with the system as it grows.
