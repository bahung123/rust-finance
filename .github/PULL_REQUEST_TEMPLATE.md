## Summary

Describe what changed and why.

## Area

- [ ] Market data ingestion
- [ ] Execution or OMS
- [ ] Risk or compliance
- [ ] Quant signals or pricing
- [ ] FIX parser
- [ ] TUI, CLI, or web UI
- [ ] AI, ML, or knowledge graph
- [ ] Persistence, metrics, or alerts
- [ ] Documentation, funding, or community
- [ ] CI, release, or supply chain

## Validation

- [ ] `cargo fmt --all -- --check`
- [ ] `cargo test --workspace --all-features --no-fail-fast`
- [ ] `cargo clippy --workspace --all-features --all-targets -- -D warnings`
- [ ] `cargo deny check --all-features`
- [ ] `cargo audit`
- [ ] Not run; reason:

## Safety

- [ ] No secrets, keys, account IDs, or private order data are included.
- [ ] Live-trading behavior is unchanged, disabled by default, or covered by tests.
- [ ] Risk, execution, parser, or replay changes include failure-mode notes.
- [ ] User-facing docs or screenshots are updated when behavior changes.

## Linked Issues

Fixes #
