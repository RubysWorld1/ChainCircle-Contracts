# SaveCircle Contracts

[![CI](https://github.com/RubysDefi/SaveCircle-Contracts/actions/workflows/ci.yml/badge.svg)](https://github.com/RubysDefi/SaveCircle-Contracts/actions)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview

SaveCircle Contracts is a Soroban-based smart contract workspace for community savings and lending circles on Stellar.

This repository contains three modular contracts:

- `savings_circle` — pooled saving groups with contribution tracking, withdrawals, and rotation logic.
- `credit_score` — on-chain credit profile generation based on contribution and repayment history.
- `microloan` — loan issuance, repayment tracking, and default handling.

## Why SaveCircle?

- Designed for community financial inclusion
- Built on Stellar Soroban for secure on-chain execution
- Modular workspace for independent contract development

## Status

| Contract | Status |
|---|---|
| `savings_circle` | Scaffolded / in development |
| `credit_score` | Scaffolded / in development |
| `microloan` | Scaffolded / in development |

## Requirements

- Rust stable toolchain
- `wasm32-unknown-unknown` target
- Soroban CLI

## Quick Start

```bash
git clone https://github.com/RubysDefi/SaveCircle-Contracts.git
cd SaveCircle-Contracts
rustup target add wasm32-unknown-unknown
cargo install --locked soroban-cli
cargo build --target wasm32-unknown-unknown --release
cargo test
```

## Development Workflow

1. Create a feature branch from `main`:
   - `feat/short-description`
   - `fix/short-description`
   - `test/short-description`
2. Implement the contract logic or test coverage.
3. Run formatting, build, and test checks.
4. Open a pull request using the template in `.github/PULL_REQUEST_TEMPLATE.md`.

## Structure

```
contracts/
├── credit_score/     # On-chain scoring and eligibility logic
├── microloan/        # Loan lifecycle and default tracking
└── savings_circle/   # Community pool, contribution, and payout logic
Cargo.toml            # Workspace configuration and shared dependencies
```

## Local Commands

Build all contracts:

```bash
cargo build --target wasm32-unknown-unknown --release
```

Run tests:

```bash
cargo test
```

Format Rust code:

```bash
cargo fmt --all
```

Optional linting:

```bash
cargo clippy --all -- -D warnings
```

## Contribution

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before submitting issues or pull requests.

## Continuous Integration

This repository runs GitHub Actions for every push and pull request targeting `main`.

The CI workflow installs Rust and the Soroban CLI, builds the workspace for `wasm32-unknown-unknown`, and runs all tests.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
