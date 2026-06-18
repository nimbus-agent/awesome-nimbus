# Awesome Nimbus [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of connectors, recipes, extensions, and resources for [**Nimbus**](https://github.com/nimbus-agent/Nimbus) — the local-first AI agent for DevOps and platform teams.

Nimbus is a headless Bun gateway that maintains a private, local SQLite index of your data across ~94 cloud services via first-party [MCP](https://modelcontextprotocol.io) connectors, gates every destructive action behind a structural human-in-the-loop (HITL) consent gate, and executes multi-step agentic workflows on your behalf. Local-first, HITL-gated, MCP-native, AGPL-3.0.

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

- [Nimbus](https://github.com/nimbus-agent/Nimbus) — The monorepo: gateway, CLI, Tauri desktop, SDK, MCP connectors, VS Code extension.
- [`@nimbus-dev/sdk`](https://github.com/nimbus-agent/Nimbus/tree/main/packages/sdk) — MIT SDK for building first-party-style extensions and connectors.
- [`@nimbus-dev/client`](https://github.com/nimbus-agent/Nimbus/tree/main/packages/client) — MIT typed JSON-RPC IPC wrapper for talking to the gateway.
- [nimbus-vscode](https://github.com/nimbus-agent/Nimbus/tree/main/packages/vscode-extension) — VS Code extension (Marketplace + Open VSX).

### Install channels

- [homebrew-tap](https://github.com/nimbus-agent/homebrew-tap) — `brew install` (macOS/Linux).
- [scoop-bucket](https://github.com/nimbus-agent/scoop-bucket) — `scoop install` (Windows).
- [linux-repo](https://github.com/nimbus-agent/linux-repo) — GPG-signed apt/yum repository.

## Connectors

Nimbus ships **~94 first-party MCP connectors** (in [`packages/mcp-connectors`](https://github.com/nimbus-agent/Nimbus/tree/main/packages/mcp-connectors)). Every connector exposes a uniform tool surface (`list`/`get`/`search` read tools; `create`/`update`/`move`/`delete` write tools are HITL-gated) and ingests metadata into the local index. Categories:

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

- [nimbus-recipes](https://github.com/nimbus-agent/nimbus-recipes) — The community recipe hub.
- *Your recipe here — open a PR!*

## Extensions & Registry

- [create-nimbus-connector](https://github.com/nimbus-agent/create-nimbus-connector) — Scaffold a new connector from the first-party template.
- [nimbus-connector-registry](https://github.com/nimbus-agent/nimbus-connector-registry) — Signed index + publisher-key directory for the connector/extension marketplace.
- [nimbus-mcp-servers](https://github.com/nimbus-agent/nimbus-mcp-servers) — Standalone MCP servers usable by any MCP client (Claude Desktop, Cursor, …).

## Companion Tools

- [nimbus-raycast](https://github.com/nimbus-agent/nimbus-raycast) — Raycast extension: quick-ask Nimbus from anywhere on macOS.
- [nimbus-statuspage](https://github.com/nimbus-agent/nimbus-statuspage) — Generate on-call/status pages from indexed incidents, alerts, and DORA metrics.

## Guides & Docs

- [Architecture](https://github.com/nimbus-agent/Nimbus/blob/main/docs/architecture.md) — Subsystem design, IPC catalogue, schema reference.
- [Security invariants](https://github.com/nimbus-agent/nimbus-security) — The I1–I27 structural defenses + disclosure policy.
- [CLI reference](https://github.com/nimbus-agent/Nimbus/blob/main/docs/cli-reference.md) — Full subcommand reference.
- [Benchmarks](https://github.com/nimbus-agent/nimbus-benchmarks) — Public performance trends for the gateway.

## Community

- *Blog posts, talks, and tutorials — open a PR to add yours.*

## License

[MIT](./LICENSE) — list content. Linked projects retain their own licenses (Nimbus core is AGPL-3.0).
