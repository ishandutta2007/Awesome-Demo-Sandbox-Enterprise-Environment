# Awesome-Demo-Sandbox-Enterprise-Environment

## Top Demo & Sandbox Enterprise Environment Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Ephemeral Preview Environments, Isolated Sandboxes & Demo Infrastructure*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Demo & Sandbox Enterprise Environments**. These tools provide isolated, disposable copies of applications and their dependencies—enabling sales demos, QA testing, and feature previews without risking production data or creating conflicts between teams sharing a staging environment.

**Examples** include Vercel Preview Environments, Release.com, Bunnyshell, Okteto, Uffizzi, LocalStack, Salesforce Scratch Orgs, and open-source alternatives like Fadebox, K8s Ephemeral Environments, and GoodRx Lifecycle (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted ephemeral environments, open-source preview infrastructure, and community-driven sandbox orchestration—ideal for organizations seeking data sovereignty and predictable costs over per-preview SaaS billing. The open-source landscape has matured to the point where **Fadebox** offers Docker-based ephemeral environments with a free tier [citation:8], **K8s Ephemeral Environments** provides full-stack PR previews on a single VPS for under $120/month [citation:3], and **GoodRx Lifecycle** delivers selective microservice previews with a fallback to shared staging [citation:13]. Note that **LocalStack Community Edition was replaced by a proprietary image in March 2026**—teams relying on the free tier should evaluate open-source alternatives like fakecloud [citation:15].

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|-------------|-------------------|--------------------------|
| **[Vercel Preview Environments](https://vercel.com/)** | Automatic preview deployments for every Git branch/PR with unique URLs. Zero-config for Next.js and frontend frameworks. Ephemeral by default; persists until branch deletion. | Pro: **$20/month** (includes preview deployments); Enterprise: custom | **Hobby (free)**: preview deployments for personal projects; non-commercial only |
| **[Release.com](https://release.com/)** | Ephemeral environments for development, QA, and demos. Spins up full-stack environments on demand with configurable infrastructure and automatic teardown. | Quote-only (usage-based) | Free tier available for small teams |
| **[Bunnyshell](https://www.bunnyshell.com/)** | Ephemeral environments platform with Kubernetes-native orchestration. Creates isolated environments per PR or on demand, with support for complex microservice dependencies. | Quote-only | No free tier; demo via sales |
| **[Okteto](https://okteto.com/)** | Kubernetes development environments with preview environments for PRs. Focused on developer productivity with hot-reload and remote development. | Quote-only (per-developer or per-cluster) | **Free tier** available for small teams |
| **[Uffizzi](https://www.uffizzi.com/)** | Ephemeral environments for full-stack applications. Creates preview environments per PR with database and service dependencies. | Quote-only | Free tier available for open-source projects |
| **[LocalStack](https://localstack.cloud/)** | Local AWS cloud emulator for testing and sandboxing. **Critical: Community Edition replaced by proprietary image requiring auth token in March 2026** [citation:15]. Pro adds advanced services (RDS, ElastiCache, Cognito, SES v2, API Gateway v2). | Pro: quote-only; Community (legacy): deprecated | **No longer free**—Community Edition requires account and auth token as of March 2026 |
| **[Salesforce Scratch Orgs](https://developer.salesforce.com/)** | Disposable Salesforce environments for development and testing. Configurable features, limits, and duration (typically 1–30 days). Source-driven development model. | Included with Salesforce Developer Edition or paid subscriptions | **Free Developer Edition** includes scratch org allocations; paid orgs have higher limits |
| **[Oracle Sandboxes](https://docs.oracle.com/en/cloud/saas/applications-common/26d/oaext/overview-of-sandboxes.html)** | Isolated environments for testing configuration changes without impacting mainline. Supports test-only and publish workflows, with access controls (full, edit/preview, view-only) [citation:1]. | Included with Oracle Cloud Applications subscription | No separate free tier; bundled with enterprise subscription |
| **[Microsoft Business Central Preview Environments](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/preview-environments)** | Sandbox environments on preview versions of Business Central for testing upcoming releases. Public preview periods run March and September; environments deleted 30 days after GA [citation:11]. | Included with Business Central subscription | No separate free tier; requires Business Central license |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[K8s Ephemeral Environments](https://github.com/koder-cat/k8s-ephemeral-environments)** | [![Stars](https://img.shields.io/github/stars/koder-cat/k8s-ephemeral-environments?style=social&color=white)](https://github.com/koder-cat/k8s-ephemeral-environments/stargazers) | **Full-stack preview environments with databases for every PR—self-hosted alternative to Vercel/Qovery.** Runs on a single VPS with k3s, DNS, TLS, and observability (Prometheus/Loki/Grafana). Each PR gets an isolated app instance and database (PostgreSQL, MongoDB, MinIO, Redis). **Goals: preview URL within 10 minutes, cleanup within 5 minutes, 5+ simultaneous PRs, under $120/month infrastructure cost.** Phase 1 complete and operational. Currently supports public repositories only [citation:3]. |
| **[Fadebox](https://hub.docker.com/r/fadebox/fadebox)** | [![Stars](https://img.shields.io/github/stars/fadebox/fadebox?style=social&color=white)](https://github.com/fadebox/fadebox/stargazers) | **Self-hosted ephemeral environments on Docker—no Kubernetes required.** Describe services as reusable Compose-native templates, spin up isolated copies per branch/developer/demo, each at a predictable URL (`https://shop-dev-pr42-web.envs.example.com`). Features: one-click deploy, per-container state/health/logs, name-based ingress with wildcard TLS via Traefik, multi-runtime (local or remote daemons over TCP with mTLS), private registries, GitOps value sources, SSO/OIDC, CI-ready CLI. **Proprietary license with Free tier included.** Runs as two containers (app + PostgreSQL) [citation:8]. |
| **[GoodRx Lifecycle](https://github.com/GoodRxOSS/lifecycle)** | [![Stars](https://img.shields.io/github/stars/GoodRxOSS/lifecycle?style=social&color=white)](https://github.com/GoodRxOSS/lifecycle/stargazers) | **Ephemeral environments with selective microservice previews and fallback to shared staging.** Open-sourced from GoodRx (2025). Define services in `lifecycle.yaml`; when a PR is created, Lifecycle launches preview environments for changed services while **falling back to the shared/static environment for unchanged services**—reducing cost and complexity for microservice teams. Self-hosted Helm chart for Kubernetes (GCP and AWS). GitHub app adds smart comments on PRs showing environment state with enable/disable toggles [citation:13]. |
| **[Cella](https://github.com/latere-ai/cella)** | [![Stars](https://img.shields.io/github/stars/latere-ai/cella?style=social&color=white)](https://github.com/latere-ai/cella/stargazers) | **Open-source sandbox orchestration for AI agents and isolated workloads.** Sandbox API with Kubernetes, Podman, and local process drivers. Features: egress gateway for network boundary enforcement, admission webhook for manifest validation, journaled mutation records delivered signed to sinks, envelope-encrypted secrets, and desktop vocabulary for screen/pointer/keyboard events. Go-based with PostgreSQL or in-memory store [citation:2]. **Not a demo environment tool**—focused on secure sandbox isolation for agent execution. |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[fakecloud](https://fakecloud.dev/)** | — | **Open-source AWS emulator—the migration target for LocalStack Community users.** Single binary, no account, no token, no paid tier. Covers services most teams relied on LocalStack Community for, plus RDS, ElastiCache, Cognito User Pools, SES v2, and API Gateway v2 (which moved to LocalStack Pro). Same port (`4566`) and dummy credentials—application code unchanged. **~500ms startup vs ~3s for LocalStack container** [citation:15]. |
| **[scratchpool](https://github.com/Tbristo01/scratchpool)** | [![Stars](https://img.shields.io/github/stars/Tbristo01/scratchpool?style=social&color=white)](https://github.com/Tbristo01/scratchpool/stargazers) | **Self-refilling pool of ready Salesforce scratch orgs on your laptop.** Claim a warm org in ~2 seconds from CLI or Claude Code. Zero dependencies. `scratchpool init --hub my-devhub --size 2` starts filling; `scratchpool claim PROJ-123` grabs a warm org; `scratchpool release` deletes and frees the Dev Hub slot. Background scheduler maintains pool size. **Not a general sandbox tool**—specific to Salesforce scratch org workflows [citation:4]. |
| **[MavMeta](https://github.com/Syntax-Syllogism/MavMeta)** | [![Stars](https://img.shields.io/github/stars/Syntax-Syllogism/MavMeta?style=social&color=white)](https://github.com/Syntax-Syllogism/MavMeta/stargazers) | **Salesforce admin/developer GUI with scratch org management.** Quick-switch between production, sandbox, and scratch orgs. Scratch Org Wizard for guided setup. Metadata explorer, SOQL explorer, REST explorer, LWC Playground. Runs entirely on `127.0.0.1`—no telemetry, credentials never persisted. **Complements scratch org infrastructure** with a management UI [citation:9]. |

**Frameworks for building custom systems**: Choose **K8s Ephemeral Environments** for a complete self-hosted PR preview platform on a single VPS (under $120/month), **Fadebox** for Docker-based ephemeral environments without Kubernetes overhead, and **GoodRx Lifecycle** for microservice teams needing selective service previews with shared staging fallback. For Salesforce-specific sandbox workflows, **scratchpool** provides warm org pooling while **MavMeta** offers a management GUI. For AWS-dependent demos, **fakecloud** replaces the now-proprietary LocalStack Community [citation:15].

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Demo and sandbox environments often contain production-like data or credentials; enforce strict data anonymization, network isolation, and automatic teardown policies.
- **Open-source ephemeral environments have matured but require infrastructure ownership.** K8s Ephemeral Environments targets a single VPS under $120/month [citation:3], Fadebox requires Docker with Compose plugin [citation:8], and GoodRx Lifecycle requires a Kubernetes cluster with Helm [citation:13]. **LocalStack Community Edition is no longer free**—the March 2026 change requires an auth token, and fakecloud is the recommended open-source migration path [citation:15]. Salesforce scratch orgs are free with Developer Edition but limited in number and duration; scratchpool helps maximize their utility through warm pooling [citation:4].

---

**Made for sales engineers, QA teams, platform engineers, and developers building demo and sandbox infrastructure.**  
Let's make enterprise demo and sandbox environments more open, ephemeral, and cost-predictable.
