# Contributing to RustFinance Terminal

Thank you for considering a contribution. This project sits at the intersection of Rust systems engineering, market-data ingestion, execution research, risk controls, and security-sensitive automation. Contributions are welcome, but changes must be reviewable, tested, and honest about trading risk.

All contributors are expected to follow the [Code of Conduct](CODE_OF_CONDUCT.md).

## What to Work On

Good first contributions:

- Documentation fixes and diagrams
- Test coverage for deterministic replay, risk controls, and parsers
- Small clippy or rustfmt fixes
- TUI usability fixes
- Mock exchange data and replay fixtures

Advanced contributions:

- Market-data adapters
- Execution and OMS behavior
- Risk model correctness
- FIX parsing and validation
- Security hardening, fuzzing, and dependency review

Do not open pull requests that add live-trading behavior without tests, safety notes, and a clear paper-trading path.

## Development Setup

```powershell
git clone https://github.com/YOUR_USERNAME/rust-finance.git
cd rust-finance
git checkout -b feature/your-change
cargo build --workspace --all-features
```

For local development that should not hit real services:

```powershell
$env:USE_MOCK = "1"
cargo run -p tui --release
cargo run -p daemon --release
```

Use a local `.env` file for external API keys. Never commit secrets.

```text
ANTHROPIC_API_KEY="your_key"
FINNHUB_API_KEY="your_key"
ALPACA_API_KEY="your_key"
ALPACA_SECRET_KEY="your_key"
```

## Required Checks

Run the focused checks for your change first:

```powershell
cargo fmt --all -- --check
cargo test --workspace --all-features --no-fail-fast
```

Before opening a larger PR, run the stricter project gate:

```powershell
cargo clippy --workspace --all-features --all-targets -- -D warnings -D clippy::all -D clippy::pedantic -D clippy::cargo
cargo deny check --all-features
cargo audit
cargo test --workspace --doc
```

If a check fails because of a missing local tool, mention that in the PR and include the command output summary.

## Crate Ownership Map

Use this map to route reviews and understand risk:

| Area | Crates | Review Risk |
|:---|:---|:---|
| Core types and sequencing | `common`, `event_bus` | High |
| Market data | `ingestion`, `polymarket`, `feature`, `signals` | High |
| Execution and order flow | `execution`, `oms`, `fix`, `strategy` | Critical |
| Risk and compliance | `risk`, `compliance`, `pricing` | Critical |
| AI and knowledge graph | `ai`, `knowledge_graph`, `ml` | Medium |
| Storage and observability | `persistence`, `metrics`, `alerts` | Medium |
| User interfaces | `tui`, `web`, `web-dashboard`, `dashboard`, `cli` | Medium |
| Simulation and research | `backtest`, `swarm_sim`, `benchmarks` | Medium |

Changes in critical areas need tests and a short explanation of failure modes.

## Pull Request Expectations

- Keep PRs small enough to review in one sitting.
- Explain the problem, the approach, and the validation performed.
- Link related issues with `Fixes #123` when appropriate.
- Include screenshots or terminal output for TUI changes.
- Include before/after behavior for risk, execution, parser, or replay changes.
- Do not mix formatting-only changes with functional changes.
- Do not claim production trading readiness unless the PR only changes documentation that already supports that claim.

## Style

- Use `cargo fmt`.
- Prefer clear Rust over clever Rust.
- Avoid new dependencies unless they remove real complexity.
- Do not add emojis to code, commit messages, or project docs.
- Keep security-sensitive defaults fail-closed.
- Keep live-trading features opt-in and mockable.

## Security

Report vulnerabilities through GitHub private security advisories or by emailing `security@ashutosh0x.dev`. Do not open public issues for secrets, auth bypasses, unsafe parsing bugs, or exchange-authentication weaknesses.

See [SECURITY.md](SECURITY.md) for scope and response timelines.
