# Fundable Protocol

[![GitHub Workflow Status](https://github.com/username/fundable/workflows/tests/badge.svg)](https://github.com/username/fundable/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A decentralized finance protocol built on StarkNet that combines token distribution and payment streaming capabilities. Fundable enables both bulk token distributions and continuous, real-time token streaming with advanced management features.

## Overview

Fundable Protocol provides two main functionalities:

1. **Token Distribution**: Efficiently distribute tokens to multiple recipients in either:
   - Equal amounts across all recipients
   - Custom weighted amounts per recipient

2. **Payment Streaming**: Create and manage token streams that automatically distribute tokens over time with features like:
   - Linear token streaming
   - Stream management (pause, restart, cancel)
   - Partial withdrawals
   - Stream status tracking

## 🏗️ Architecture

The protocol consists of two main components:

### Distributor Contract
- Handles bulk token distributions
- Manages token allowances and transfers
- Emits distribution events
- Supports both equal and weighted distributions

### PaymentStream Contract
- Manages stream creation and lifecycle
- Handles withdrawals and stream modifications
- Tracks stream states and balances
- Provides stream query functions

## 📦 Installation

### Prerequisites

- [Scarb](https://docs.swmansion.com/scarb/docs.html) v2.8.5
- [StarkNet Foundry](https://foundry-rs.github.io/starknet-foundry/) v0.31.0
- [Cairo](https://www.cairo-lang.org/docs/quickstart.html) v2.8.3

### Setup

1. Clone the repository
```bash
git clone https://github.com/fundable-protocol/fundable.git
cd fundable
```

2. Install dependencies
```bash
scarb build
```

## 🧪 Testing

Run the test suite:
```bash
snforge test
```

For verbose output:
```bash
scarb test -v
```

## 🚀 Usage

### Token Distribution Example

```cairo
use fundable::distributor::Distributor;

// Create a distribution with equal amounts
let recipients = array![addr1, addr2, addr3];
distributor.distribute_equal(token, total_amount, recipients);

// Create a weighted distribution
let amounts = array![100, 200, 300];
distributor.distribute_weighted(token, recipients, amounts);
```

### Payment Streaming Example

```cairo
use fundable::payment_stream::PaymentStream;

// Create a new stream
let stream = payment_stream.create_stream(
    recipient,
    total_amount,
    start_time,
    end_time,
    token
);

// Withdraw from stream
payment_stream.withdraw(stream_id, amount);

// Pause stream
payment_stream.pause_stream(stream_id);
```

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Make your changes and write tests to ensure your changes are working as expected
4. Run tests (`snforge test`)
5. Commit your changes (`git commit -m 'feat: add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

### Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/). Examples:

- `feat: add new streaming feature`
- `fix: handle edge case in calculation`
- `docs: update installation instructions`
- `test: add test for edge case`
- `chore: update dependencies`

### Code Style

- Use `snake_case` for functions and variables
- Use `PascalCase` for types and traits
- Use `SCREAMING_SNAKE_CASE` for constants
- Add documentation comments (`///`) for public interfaces
- Follow [Cairo code style guidelines](https://book.cairo-lang.org/ch02-00-common-programming-concepts.html)

## 🔒 Security

For security concerns, please email security@fundable.com or open a draft security advisory on Github.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- StarkWare for the Cairo programming language
- OpenZeppelin for security best practices and implementations
- The StarkNet community for their continuous support

## 📞 Contact

- Telegram: [Join our channel](https://t.me/fundable_finance)
- Twitter: [@fundable](https://twitter.com/fundable_)





