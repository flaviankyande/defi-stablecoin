# DeFi Stablecoin Project

A decentralized stablecoin implementation built with Solidity, featuring algorithmic stability mechanisms and crypto collateral backing.

## Overview

This project implements a decentralized stablecoin with the following key features:

1. **Price Stability**: Pegged to $1.00 USD through:
   - Chainlink Price Feed integration for reliable price data
   - ETH/BTC to USD conversion functionality

2. **Decentralized Minting**:
   - Algorithmic stability mechanism
   - Collateral-backed minting system
   - Automated verification of collateral requirements

3. **Supported Collateral**:
   - wETH (Wrapped Ethereum)
   - wBTC (Wrapped Bitcoin)

## Prerequisites

Before you begin, ensure you have the following installed:
- [Git](https://git-scm.com/)
- [Foundry](https://getfoundry.sh/)
- [Rust](https://www.rust-lang.org/tools/install)
- A compatible Web3 wallet (e.g., MetaMask)

## Installation

1. Clone the repository:
```shell
git clone <repository-url-above>
cd defi-stablecoin
```

2. Install dependencies:
```shell
forge install
```

3. Build the project:
```shell
forge build
```

## Testing

Run the test suite:
```shell
forge test
```

For detailed test output:
```shell
forge test -vv
```

For gas optimization tests:
```shell
forge snapshot
```

## Local Development

1. Start a local node:
```shell
anvil
```

2. Deploy to local network:
```shell
forge script script/DeployDSC.s.sol:DeployDSC --rpc-url http://localhost:8545 --private-key <your-private-key>
```

## Deployment to Testnet/Mainnet

1. Set up your environment variables:
```shell
export RPC_URL=<your_rpc_url>
export PRIVATE_KEY=<your_private_key>
```

2. Deploy to your chosen network:
```shell
forge script script/DeployDSC.s.sol:DeployDSC --rpc-url $RPC_URL --private-key $PRIVATE_KEY --broadcast
```

## Smart Contract Architecture

### Core Components

1. **StableCoin.sol**: Main stablecoin implementation
   - ERC20 compliant
   - Minting/burning mechanics
   - Price stability controls

2. **CollateralManager.sol**: Handles collateral deposits and withdrawals
   - Supports wETH and wBTC
   - Manages collateralization ratios
   - Liquidation mechanisms

3. **PriceOracle.sol**: Price feed integration
   - Chainlink integration
   - Price update mechanisms
   - Fallback price sources

## Development Tools

This project uses Foundry's development tools:

- **Forge**: Ethereum testing framework
- **Cast**: Contract interaction tool
- **Anvil**: Local Ethereum node
- **Chisel**: Solidity REPL

For detailed documentation on Foundry tools, visit: https://book.getfoundry.sh/

## Additional Commands

Format code:
```shell
forge fmt
```

Get help on commands:
```shell
forge --help
anvil --help
cast --help
```

## Security Considerations

- Ensure proper collateralization ratios when deploying
- Regular price feed validation
- Implement emergency shutdown mechanisms
- Consider rate limiting for large transactions

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

MIT