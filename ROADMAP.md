# RustFinance Terminal Roadmap

This roadmap keeps growth tied to engineering quality. The project should attract Rust, quant, fintech, and security contributors without implying that it is production trading infrastructure.

## 30 Days: Community Readiness

- Land community health files: code of conduct, issue templates, PR template, and updated contribution guide.
- Keep funding files live: `.github/FUNDING.yml`, `funding.json`, and README sponsor links.
- Curate at least 10 starter issues across documentation, tests, beginner Rust fixes, and advanced market-data or quant work.
- Publish a clean `v0.4.0` release note draft with screenshots, demo video, security posture, and safety disclaimer.
- Submit `funding.json` to FLOSS/fund and prepare GitHub Secure Open Source Fund application copy.
- Improve README first screen around install, demo, safety, roadmap, and good-first-issue links.

## 60 Days: Contributor Funnel

- Add replay fixtures for ingestion, FIX parsing, risk checks, and paper execution.
- Add a `docs/architecture/` contributor tour covering crate boundaries and event flow.
- Split good-first issues into small, testable tasks with clear acceptance criteria.
- Add fuzzing targets for external input surfaces: FIX, WebSocket payloads, and config parsing.
- Improve CI feedback speed with focused jobs for docs-only, Rust-only, and security-only changes.
- Start monthly public project notes covering merged work, upcoming roadmap, and sponsor impact.

## 90 Days: Ecosystem Credibility

- Publish stable demo binaries through GitHub Releases with SBOM/auditable build notes.
- Prepare FINOS Labs intake material: governance, roadmap, compliance posture, and contribution process.
- Publish one technical article for Rust developers and one practical article for quant/fintech users.
- Evaluate publishing selected library crates to crates.io once names, APIs, and MSRV policy are stable.
- Add benchmark baselines for ingestion latency, event bus throughput, risk gate latency, and TUI responsiveness.
- Move from solo-maintainer workflow toward reviewer areas for docs, tests, risk, ingestion, and UI.

## Funding and Sustainability

- GitHub Sponsors: use for recurring community support.
- Buy Me a Coffee: use for low-friction one-time support.
- thanks.dev: use for dependency-graph funding.
- FLOSS/fund: use `funding.json`; current schema is `v1.1.0`.
- GitHub Secure Open Source Fund: apply with focus on parser hardening, supply-chain controls, fuzzing, and incident response.
- FINOS Labs: apply after community files, roadmap, and governance are visible.
- Tidelift: defer until at least one public crates.io package is ready to claim.

## Safety Positioning

RustFinance Terminal is open-source research and infrastructure. It is not financial advice, not a broker, and not a claim of live-trading readiness. Every growth push should point users toward mock mode, paper trading, tests, and independent review before real capital is involved.
