Smart Contract for Land Registry

Overview

The LandRegistry smart contract is built on the Ethereum blockchain using Solidity. It provides a system to register, transfer, and manage land ownership records securely and transparently.

Features

• Register new land parcels with unique identifiers.

• Transfer ownership of land to another address.

• Query land details by ID.

• Emit events for registration and ownership transfer.


Contract Structure

Data Structures

• struct Land: Represents a land parcel with the following properties:

• id: Unique identifier for the land.

• location: Description of the land's location.

• area: Area of the land in square meters.

• owner: Address of the current owner.

• registered: Boolean indicating if the land is registered.



Mappings

• mapping(uint256 => Land) public lands: Stores land details by ID.


Events

• LandRegistered(uint256 landId, string location, uint256 area, address owner): Emitted when a new land is registered.

• LandOwnershipTransferred(uint256 landId, address previousOwner, address newOwner): Emitted when ownership is transferred.


Functions

• registerLand(uint256 _id, string memory _location, uint256 _area): Registers new land. Only callable by the current owner.

• transferOwnership(uint256 _id, address _newOwner): Transfers ownership to another address. Only the current owner can transfer.

• getLandDetails(uint256 _id) public view returns (Land memory): Retrieves details of a specific land parcel.


Usage

1. Register Land:

registerLand(1, "123 Blockchain St.", 500);


2. Transfer Ownership:

transferOwnership(1, 0xNewOwnerAddress);


3. Query Land Details:

getLandDetails(1);



Prerequisites

• Solidity ^0.8.0

• Ethereum-compatible environment (e.g., Remix, Truffle)


License

This project is licensed under the MIT License.
