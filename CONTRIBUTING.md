# Contributing to ChainCircle Contracts

This repo is part of the **Stellar Drips Wave Programme**. Contributions earn points and rewards!

## Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (stable)
- WASM target: `rustup target add wasm32-unknown-unknown`
- [Soroban CLI](https://soroban.stellar.org/docs/getting-started/setup): `cargo install --locked soroban-cli`

## Getting Started

```bash
git clone https://github.com/RubysWorld1/ChainCircle-Contracts.git
cd ChainCircle-Contracts
```

## Before Pushing — CI Checklist

The CI pipeline will fail if any of these steps fail. Run them locally before pushing:

```bash
# 1. Make sure all contracts compile to WASM
cargo build --target wasm32-unknown-unknown --release

# 2. Run all contract tests
cargo test
```

**CI checks on every push/PR:**
- `cargo build --target wasm32-unknown-unknown --release` — all contracts compile
- `cargo test` — all tests pass

## Project Structure

```
contracts/
├── savings_circle/   # Core savings circle logic
├── credit_score/     # On-chain credit scoring
└── microloan/        # Microloan disbursement and repayment
```

## Branch Naming

| Type | Format |
|---|---|
| Feature | `feat/short-description` |
| Bug fix | `fix/short-description` |
| Tests | `test/short-description` |

## Commit Messages

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat(savings_circle): implement token transfer on payout
fix(credit_score): correct score floor on default penalty
test(microloan): add default detection test
```

## Pull Request Process

1. Ensure all tests pass: `cargo test`
2. Ensure contracts build: `cargo build --target wasm32-unknown-unknown --release`
3. Open a PR against `develop`
4. Fill in the PR template
5. Request a review from a maintainer

## General Rules

- Always branch off `develop`, never commit directly to `main`
- Branch name must follow the naming convention below
- Fill in the PR template completely before submitting
- Never commit secrets or credentials
- If your issue has a `TODO` comment in the code, your PR must address that specific TODO

## Wave Bounty Issues

Issues tagged with point values are eligible for Drips Wave rewards. Check the issue tracker for available bounties. Look for issues marked with `TODO` comments in the source code as starting points.
