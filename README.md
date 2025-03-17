# Veltis Smart Contracts

Smart Contracts for Veltis - Biotech IP Tokenization Platform

## Overview

This repository contains the smart contracts for the Veltis platform, which enables users to create, fractionalize, list, and trade IP NFTs (Intellectual Property Non-Fungible Tokens) in a decentralized marketplace.

## Tech Stack

- Solidity (v0.8.9+)
- Hardhat development framework
- OpenZeppelin contracts
- Ethers.js for testing and deployment

## Prerequisites

- Node.js (v16 or higher)
- npm or yarn
- A Web3 wallet like MetaMask

## Development Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/Veltiscapital/veltis-contracts.git
   cd veltis-contracts
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file with the following environment variables:
   ```
   PRIVATE_KEY=your_private_key
   POLYGON_AMOY_RPC_URL=your_polygon_amoy_rpc_url
   POLYGON_MAINNET_RPC_URL=your_polygon_mainnet_rpc_url
   POLYGONSCAN_API_KEY=your_polygonscan_api_key
   ```

4. Compile the contracts:
   ```bash
   npx hardhat compile
   ```

5. Run tests:
   ```bash
   npx hardhat test
   ```

## Smart Contracts

### IPNFTRegistry

The main contract for creating and managing IP NFTs. It extends the ERC721 standard and adds functionality for storing metadata URIs.

Key features:
- Mint IP NFTs with metadata
- Transfer ownership
- View metadata

### SimpleIPNFTRegistry

A simplified version of the IP NFT registry for basic use cases.

Key features:
- Streamlined minting process
- Lower gas costs
- Basic metadata support

### FractionalizationFactory

Creates and manages fractionalized tokens from IP NFTs.

Key features:
- Create fractionalized tokens from IP NFTs
- Set initial token supply and distribution
- Configure royalty parameters

### Marketplace

Facilitates the buying and selling of IP NFTs and fractionalized tokens.

Key features:
- List IP NFTs and fractionalized tokens for sale
- Make offers
- Complete transactions
- Collect platform fees

## Deployment

### Polygon Amoy Testnet

To deploy to the Polygon Amoy Testnet:

```bash
npx hardhat run scripts/deploy.js --network polygonAmoy
```

### Polygon Mainnet

To deploy to the Polygon Mainnet:

```bash
npx hardhat run scripts/deploy.js --network polygon
```

### Verify Contracts

To verify the contracts on PolygonScan:

```bash
npx hardhat verify --network polygonAmoy DEPLOYED_CONTRACT_ADDRESS constructor_argument1 constructor_argument2
```

## Project Structure

```
├── contracts/           # Smart contract source code
│   ├── interfaces/      # Contract interfaces
│   └── test/            # Test contracts
├── scripts/             # Deployment scripts
├── test/                # Test scripts
├── hardhat.config.js    # Hardhat configuration
└── .env.example         # Example environment variables
```

## Security

**Note:** These contracts have not been audited. Use at your own risk.

## License

This project is licensed under the MIT License - see the LICENSE file for details.