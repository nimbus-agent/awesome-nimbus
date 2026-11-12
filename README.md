# Awesome Nimbus [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of connectors, recipes, extensions, and resources for [**Nimbus**](https://github.com/nimbus-agent/Nimbus) — the local-first AI agent for DevOps and platform teams.

Nimbus is a headless Bun gateway that maintains a private, local SQLite index of your data across about 95 cloud services via first-party [MCP](https://modelcontextprotocol.io) connectors, gates every destructive action behind a structural human-in-the-loop (HITL) consent gate, and executes multi-step agentic workflows on your behalf. Local-first, HITL-gated, MCP-native, AGPL-3.0.

Contributions welcome — see [CONTRIBUTING.md](./CONTRIBUTING.md).

## Contents

- [Official](#official)
- [Connectors](#connectors)
- [Recipes](#recipes)
- [Extensions & Registry](#extensions--registry)
- [Companion Tools](#companion-tools)
- [Guides & Docs](#guides--docs)
- [Community](#community)

## Official

- [Nimbus](https://github.com/nimbus-agent/Nimbus) — The gateway: gateway, CLI and Tauri desktop app (the desktop app is built, not yet released).
- [`@nimbus-dev/sdk`](https://github.com/nimbus-agent/nimbus-sdk) — MIT authoring contract for extensions and connectors (TypeScript, Python and Go).
- [`@nimbus-dev/client`](https://github.com/nimbus-agent/nimbus-client) — MIT typed JSON-RPC IPC wrapper for talking to the gateway.
- [`@nimbus-dev/mcp`](https://github.com/nimbus-agent/nimbus-mcp) — Launcher for the Nimbus MCP server: gives any MCP client your local index and the built-in agents.
- [nimbus-vscode](https://github.com/nimbus-agent/nimbus-vscode) — VS Code extension (Marketplace + Open VSX).
- [nimbus-web-clipper](https://github.com/nimbus-agent/nimbus-web-clipper) — Chrome + Firefox extension: recognises the page you are on and runs the agents against it; also clips pages into your index.

### Install channels

- [homebrew-tap](https://github.com/nimbus-agent/homebrew-tap) — `brew install` (macOS/Linux).
- [scoop-bucket](https://github.com/nimbus-agent/scoop-bucket) — `scoop install` (Windows).
- [linux-repo](https://github.com/nimbus-agent/linux-repo) — GPG-signed apt/yum repository.

## Connectors

Nimbus ships **about 95 first-party MCP connectors** (in [nimbus-mcp-servers](https://github.com/nimbus-agent/nimbus-mcp-servers)). Every connector exposes a uniform tool surface (`list`/`get`/`search` read tools; `create`/`update`/`move`/`delete` write tools are HITL-gated) and ingests metadata into the local index. Categories:

- **Source control** — GitHub, GitLab, Bitbucket.
- **CI/CD** — Jenkins, GitHub Actions, CircleCI, Bitrise, Codemagic.
- **Cloud & infrastructure** — AWS, Azure, GCP, Kubernetes, IaC, ArgoCD, Flux, Vercel, Netlify, Firebase.
- **Monitoring & incidents** — Datadog, Grafana, PagerDuty, Sentry, New Relic, CloudWatch.
- **Data warehouse & BI** — Snowflake, BigQuery, Athena, Databricks, Tableau, Looker, Power BI, Metabase, Superset.
- **Orchestration & data quality** — Airflow, Prefect, Dagster, dbt, Great Expectations, Monte Carlo, Bigeye.
- **Security & quality** — Snyk, SonarQube, Semgrep, Wiz, Dependency-Track.
- **Comms & docs** — Slack, Teams, Discord, Notion, Confluence, Linear, Jira, Obsidian.
- **Productivity, CRM & more** — Google Workspace, Microsoft 365, Zoom, HubSpot, Salesforce, Stripe, and others.

> Want a connector that doesn't exist yet? Scaffold one with [create-nimbus-connector](https://github.com/nimbus-agent/create-nimbus-connector) and list it here.

*Community connectors:*

- *Your connector here — open a PR!*

## Recipes

Shareable, signed, LLM-free declarative tool-call workflows (`.nimbus-recipe.yaml`), verifiable with `nimbus verify-share --replay`.

- Create one with `nimbus share create <session-id> --as-recipe`. A public gallery is not planned (the `nimbus-recipes` scaffold was retired on 2026-11-12), so this list is where recipes are collected.
- *Your recipe here — open a PR!*

## Extensions & Registry

- [create-nimbus-connector](https://github.com/nimbus-agent/create-nimbus-connector) — Scaffolding generator for first-party-style Nimbus MCP connectors.
- The extension registry's protocol and client ship in the gateway ([roadmap, Phase 9.5](https://github.com/nimbus-agent/Nimbus/blob/main/docs/roadmap.md#phase-95--marketplace-registry)); the public registry is not live yet.
- [nimbus-trust](https://github.com/nimbus-agent/nimbus-trust) — The signed trust feed every install applies: key revocations, takedowns and verified publishers.
- [nimbus-mcp-servers](https://github.com/nimbus-agent/nimbus-mcp-servers) — Standalone MCP servers usable by any MCP client (Claude Desktop, Cursor, …).

## Companion Tools

- *Built something on top of Nimbus? Open a PR to list it.*
- Retired on 2026-11-12, never built: `nimbus-raycast`, `nimbus-statuspage` and `nimbus-postmortem`. The [roadmap's client surfaces](https://github.com/nimbus-agent/Nimbus/blob/main/docs/roadmap.md#client-surfaces) say where each one's work went.

## Guides & Docs

- [Architecture](https://github.com/nimbus-agent/Nimbus/blob/main/docs/architecture.md) — Subsystem design, IPC catalogue, schema reference.
- [Security invariants](https://github.com/nimbus-agent/Nimbus/blob/main/docs/SECURITY-INVARIANTS.md) — The structural defenses, each with a production wiring site and an enforcement test.
- [Security model & disclosure](https://github.com/nimbus-agent/nimbus-security) — How to report a vulnerability.
- [CLI reference](https://github.com/nimbus-agent/Nimbus/blob/main/docs/cli-reference.md) — Full subcommand reference.
- [Benchmarks](https://github.com/nimbus-agent/nimbus-benchmarks) — Public performance trends for the gateway.

## Community

- *Blog posts, talks, and tutorials — open a PR to add yours.*

## License

[MIT](./LICENSE) — list content. Linked projects retain their own licenses (Nimbus core is AGPL-3.0).
