# Solana-Dex-Protocol
This repository contains an Automated Market Maker (AMM) DEX smart contract built using Anchor Framework for the Solana blockchain.

## Overview

This DEX implements a constant product formula AMM (x * y = k) similar to Uniswap v2. The protocol supports:

- **Liquidity Pool Creation**: Create token pairs for trading
- **Liquidity Provision**: Add and remove liquidity with fair share distribution
- **Token Swapping**: Trade between token pairs with configurable fees
- **Decentralized Architecture**: Fully on-chain, permissionless trading

### Key Components

- **DexConfiguration**: Stores global protocol parameters like trading fees
- **LiquidityPool**: Manages token pairs, reserves, and total supply
- **LiquidityProvider**: Tracks user-specific shares in liquidity pools

### Protocol Operations

1. **Initialize DEX**: Set up the global DEX configuration with custom fees
2. **Create Liquidity Pool**: Create a new token pair for trading
3. **Add Liquidity**: Provide tokens to pools and receive LP shares
4. **Remove Liquidity**: Burn LP shares to withdraw tokens
5. **Swap**: Exchange tokens with price determined by constant product formula

### Program ID

```
HHtpy5cez4guhvwoXVCZzo8EUce6ouJyXaxZ7r9CVR24
```

## Prerequisites

Before you begin, ensure you have the following tools installed:

### Install Rust (v1.79.0)

Rust is required to compile programs written in Rust:

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# Follow the on-screen instructions
source $HOME/.cargo/env
rustup default stable
rustup update stable
# Verify installation
rustup --version
# Make sure you have version 1.79.0
rustc --version
```

### Install Solana CLI (v1.17.0)

Solana CLI is needed to interact with the Solana blockchain:

```bash
sh -c "$(curl -sSfL https://release.solana.com/v1.17.0/install)"
# Add Solana to your PATH
export PATH="$HOME/.local/share/solana/install/active_release/bin:$PATH"
# Verify installation
solana --version
# Should output: solana-cli 1.17.0
```

### Install Anchor Framework (v0.29.0)

Anchor is the framework used for Solana smart contract development:

```bash
# Install Anchor CLI
npm install -g @coral-xyz/anchor-cli@0.29.0
# Or using cargo
cargo install --git https://github.com/coral-xyz/anchor --tag v0.29.0 anchor-cli --locked

# Verify installation
anchor --version
# Should output: anchor-cli 0.29.0
```

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Solana-Dex-Protocol.git
   cd Solana-Dex-Protocol
   ```

2. Build the program:
   ```bash
   anchor build
   ```

3. Deploy to localnet:
   ```bash
   anchor deploy
   ```

4. Run tests:
   ```bash
   anchor test
   ```

## Usage

The DEX protocol can be interacted with using Anchor client or directly through the Solana RPC API. Key operations include:

- Initialize the DEX with fees
- Create a liquidity pool for a token pair
- Add liquidity to a pool to earn fees
- Swap tokens using the AMM mechanism
- Remove liquidity to withdraw tokens

Refer to the source code in `/programs/dex/src/instructions` for implementation details of each operation.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
