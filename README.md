# BitVault Pro

**Revolutionary Bitcoin-backed synthetic asset protocol for the Stacks ecosystem.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Clarity](https://img.shields.io/badge/Language-Clarity-blue.svg)](https://clarity-lang.org/)
[![Stacks](https://img.shields.io/badge/Built%20on-Stacks-purple.svg)](https://www.stacks.co/)

## Overview

BitVault Pro transforms dormant Bitcoin into productive capital through intelligent over-collateralization mechanics, autonomous liquidation systems, and dynamic interest rate optimization. Built exclusively for the Stacks blockchain, this protocol enables Bitcoin holders to unlock liquidity without selling their digital gold.

Through sophisticated risk management algorithms, real-time oracle integration, and battle-tested collateralization ratios, BitVault Pro ensures maximum capital efficiency while maintaining ironclad security standards.

## 🚀 Features

- **🔄 Adaptive Interest Rates**: Responds to market conditions for optimal capital efficiency
- **🛡️ Multi-Tier Liquidation Protection**: Robust mechanisms to safeguard collateral
- **📊 Oracle-Driven Pricing**: Real-time BTC/USD price feeds ensure accurate valuations
- **⚡ Autonomous Interest Accrual**: Protocol automatically compounds yields
- **🔒 Battle-Tested Collateralization**: Ironclad security and risk management
- **🔗 Seamless Stacks Integration**: Native Bitcoin Layer 2 functionality

## 🏗️ Protocol Architecture

### Core Components

- **Vaults**: Users deposit BTC as collateral and mint synthetic USD (bitvault-usd)
- **Collateralization**: Minimum 150% ratio enforced, liquidation triggered at 120%
- **Interest Accrual**: Debt positions accrue ~10% APY, compounding protocol revenue
- **Liquidation Engine**: Under-collateralized vaults liquidated with 10% bonus
- **Emergency Controls**: Admin pause functionality for critical scenarios

### Key Constants

```clarity
MIN-COLLATERAL-RATIO: 150%    ; Minimum safety threshold
LIQUIDATION-THRESHOLD: 120%   ; Liquidation trigger point
LIQUIDATION-BONUS: 10%        ; Liquidator incentive
MIN-DEBT-AMOUNT: 100 tokens   ; Minimum debt position
INTEREST-RATE-PER-BLOCK: 0.0005% ; ~10% APY
```

## 📋 Prerequisites

- [Clarinet](https://docs.stacks.co/docs/clarity/clarinet) - Stacks development environment
- [Node.js](https://nodejs.org/) - For running tests
- [TypeScript](https://www.typescriptlang.org/) - Test environment

## 🛠️ Installation & Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/idarag/bitvault.git
   cd bitvault
   ```

2. **Install dependencies:**

   ```bash
   npm install
   ```

3. **Verify contract integrity:**

   ```bash
   clarinet check
   ```

4. **Run comprehensive tests:**

   ```bash
   npm test
   ```

## 🔧 Development Commands

```bash
# Check contract syntax and types
clarinet check

# Run test suite
npm test

# Start local development console
clarinet console

# Deploy to testnet
clarinet deploy --testnet
```

## 📖 Usage Guide

### Opening a Vault

```clarity
;; Deposit 1 BTC (100M satoshis) as collateral, mint 50,000 USD
(contract-call? .bitvault open-vault u100000000 u5000000000000)
```

### Managing Your Position

```clarity
;; Add more collateral
(contract-call? .bitvault deposit-collateral u50000000)

;; Repay debt
(contract-call? .bitvault repay-debt u1000000000000)

;; Withdraw excess collateral
(contract-call? .bitvault withdraw-collateral u25000000)
```

### Liquidation Opportunities

```clarity
;; Liquidate an under-collateralized vault
(contract-call? .bitvault liquidate-vault 'SP1HTBVD3JG9C05J7HBJTHGR0GGW7KXW28M5JS8QE)
```

### Querying Protocol State

```clarity
;; Get vault details
(contract-call? .bitvault get-vault-details tx-sender)

;; Check collateral ratio
(contract-call? .bitvault get-collateral-ratio tx-sender)

;; View protocol metrics
(contract-call? .bitvault get-protocol-metrics)
```

## 🔍 Contract Structure

```
contracts/
├── bitvault.clar           # Main protocol contract
tests/
├── bitvault.test.ts        # Comprehensive test suite
settings/
├── Devnet.toml            # Local development config
├── Testnet.toml           # Testnet deployment config
└── Mainnet.toml           # Production deployment config
```

## 🛡️ Security Features

- **Strict Collateralization**: Enforced minimum ratios prevent undercollateralization
- **Oracle Price Validation**: 24-hour freshness checks prevent stale price exploitation
- **Emergency Pause Mechanism**: Admin controls for critical situation response
- **Comprehensive Error Handling**: Detailed error codes for all failure scenarios
- **Interest Accrual Protection**: Automated compounding prevents debt manipulation

## 🧪 Testing

The protocol includes extensive test coverage:

```bash
npm test
```

Tests cover:

- Vault creation and management
- Collateral deposit/withdrawal
- Debt repayment scenarios
- Liquidation mechanics
- Interest accrual calculations
- Oracle price feed validation
- Emergency pause functionality

## 📊 Protocol Metrics

Real-time protocol statistics available via read-only functions:

- Total debt outstanding
- Total collateral locked
- Protocol revenue pool
- Current BTC price feed
- Last interest accrual block

## 🚨 Risk Disclosure

BitVault Pro is experimental DeFi infrastructure. Users should:

- Understand liquidation risks
- Monitor collateral ratios actively  
- Be aware of oracle dependency
- Consider smart contract risks
- Only invest what you can afford to lose

## 🤝 Contributing

We welcome contributions! Please:

1. Fork the repository
2. Create a feature branch
3. Add comprehensive tests
4. Ensure all checks pass
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Links

- [Stacks Documentation](https://docs.stacks.co/)
- [Clarity Language Guide](https://docs.stacks.co/docs/clarity/)
- [Clarinet Documentation](https://docs.stacks.co/docs/clarity/clarinet)

---

**Perfect for institutions, DeFi protocols, and sophisticated Bitcoin holders seeking to maximize their Bitcoin's productive potential in the emerging Stacks ecosystem.**
