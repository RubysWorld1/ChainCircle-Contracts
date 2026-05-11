# Contributing to SaveCircle Contracts

Thank you for contributing to SaveCircle Contracts. This repository is designed to support professional development, collaboration, and high-quality smart contract work on Stellar Soroban.

## Prerequisites

- [Rust](https://www.rust-lang.org/tools/install) (stable)
- `wasm32-unknown-unknown` target:
  ```bash
  rustup target add wasm32-unknown-unknown
  ```
- [Soroban CLI](https://soroban.stellar.org/docs/getting-started/setup):
  ```bash
  cargo install --locked soroban-cli
  ```

## Setup

```bash
git clone https://github.com/RubysDefi/SaveCircle-Contracts.git
cd SaveCircle-Contracts
rustup target add wasm32-unknown-unknown
cargo install --locked soroban-cli
```

## Local Validation

Run the build and test steps before opening a pull request:

```bash
cargo fmt --all -- --check
cargo build --target wasm32-unknown-unknown --release
cargo test
```

Optional linting:

```bash
cargo clippy --all -- -D warnings
```

## Branching Strategy

Create feature branches from `main`.

| Type | Branch Name |
|---|---|
| Feature | `feat/<short-description>` |
| Fix | `fix/<short-description>` |
| Test | `test/<short-description>` |
| Docs | `docs/<short-description>` |

## Commit Guidelines

Use Conventional Commits for clarity and history:

```text
feat(savings_circle): add payout rotation scheduling
fix(microloan): correct repayment penalty logic
test(credit_score): add credit score edge case coverage
```

## Pull Request Process

1. Confirm your branch is based on `main`.
2. Run formatting, build, and tests locally.
3. Open a PR using `.github/PULL_REQUEST_TEMPLATE.md`.
4. Target the `main` branch.
5. Add a clear description, related issue, and summary of changes.
6. Request review from one or more maintainers.

### PR Checklist

- [ ] Code is formatted with `cargo fmt`
- [ ] All tests pass (`cargo test`)
- [ ] Contract builds to WASM (`cargo build --target wasm32-unknown-unknown --release`)
- [ ] No secrets or credentials included
- [ ] TODO items are addressed or documented

## Code Style

- Keep contract logic simple and explicit
- Favor clear comments for business rules and state transitions
- Add or update tests for every non-trivial change
- Avoid committing generated artifacts or build outputs

## Issues and Feature Requests

Use the repository issue templates for bug reports and feature requests:
- `.github/ISSUE_TEMPLATE/bug_report.md`
- `.github/ISSUE_TEMPLATE/feature_request.md`

If you are unsure where to begin, open an issue describing your idea or the area you want to improve.

## Repository Workflow

This repo uses GitHub Actions for continuous integration. The workflow builds the workspace as a Soroban contract project and runs the test suite on every push and pull request targeting `main`.

## Code of Conduct

By participating in this project, you agree to abide by the [Code of Conduct](CODE_OF_CONDUCT.md).

## Licensing

This project is licensed under MIT. Contributions are accepted under the same license.
