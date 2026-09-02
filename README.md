# XGIC Wagtail

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![Docker Compose](https://img.shields.io/badge/Docker-Compose-blue?logo=docker&logoColor=white)](https://docs.docker.com/compose/)
[![Producer release](https://img.shields.io/github/v/release/xgic/wagtail-dev?label=wagtail-dev&logo=github)](https://github.com/xgic/wagtail-dev/releases)
[![GHCR image](https://img.shields.io/badge/GHCR-wagtail--dev-blue?logo=github)](https://github.com/users/xgic/packages/container/package/wagtail-dev)
[![Use this template](https://img.shields.io/badge/GitHub-Use_this_template-24292f?logo=github)](https://github.com/xgic/wagtail/generate)
[![CI](https://github.com/xgic/wagtail/actions/workflows/ci.yml/badge.svg)](https://github.com/xgic/wagtail/actions/workflows/ci.yml)

## The optimal way to start Wagtail sites

**For humans and AI coding assistants.**

This repository is XGIC’s **recommended starting point** for new [Wagtail](https://wagtail.org) sites. It gives you a **reproducible Dev Container**, a **pinned multi-arch environment image**, and a **single CLI brand**.

| You want… | You get… |
|-----------|----------|
| A clean site repository on day one | **Use this template** → your product remote |
| Minutes to a working workspace | pull `ghcr.io/xgic/wagtail-dev` · **Reopen in Container** · run `xgic` |
| The same path for AI and humans | Modular **XGIC CLI** (`xgic wagtail …`) + [AGENTS.md](AGENTS.md) |

Image producer and CI: **[xgic/wagtail-dev](https://github.com/xgic/wagtail-dev)** · Standards: **[xgic/ai](https://github.com/xgic/ai)** · CMS: [ADR-0006](https://github.com/xgic/ai/blob/main/docs/adr/0006-adopt-wagtail.md)

---

## Quick start

1. **[Use this template](https://github.com/xgic/wagtail/generate)** → create and clone **your** repository.
2. Open the folder in **VS Code** → **Dev Containers: Reopen in Container**.
3. In the container terminal:

```bash
xgic --version
xgic wagtail info
python -m pip install -r requirements.txt
wagtail start mysite .
```

The first GHCR tag is published from [xgic/wagtail-dev](https://github.com/xgic/wagtail-dev) (`v*` + GitHub Release). Until that tag exists, Compose can build the producer Dockerfile locally from a sibling clone, or wait for `ghcr.io/xgic/wagtail-dev:0.1.0`.

---

## Vision

Environment drift wastes more CMS time than missing features. XGIC’s approach:

1. **One published environment** — versioned on GHCR, reviewed in the producer.
2. **One thin template** — this repository: site schema and a pinned image.
3. **One CLI brand** — **XGIC CLI** for humans and agents.

---

## Why start here

| Benefit | Detail |
|---------|--------|
| **Fastest path** | Pre-built image; no Dockerfile rebuild in every site repo |
| **Reproducible pins** | Semver image tags match producer releases |
| **AI-operable** | Stable commands in [AGENTS.md](AGENTS.md) |
| **Clear ownership** | Schema here; image in [wagtail-dev](https://github.com/xgic/wagtail-dev); CLI in [wagtail-cli](https://github.com/xgic/wagtail-cli) |
| **Open-source rigor** | Apache-2.0, CODEOWNERS, public-safe docs, human-reviewed PRs |

---

## Empty-site gate

Record memory and cold-start on a constrained Linux environment **before** adding schema. Do not start StreamField / relational content models in this bootstrap.

---

## XGIC standards

- [BASE-STANDARDS](https://github.com/xgic/ai/blob/main/docs/BASE-STANDARDS-FOR-ORCHESTRATED-REPOS.md)
- [README standards](https://github.com/xgic/ai/blob/main/docs/readme-standards.md)
- Agents: [AGENTS.md](AGENTS.md)

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Human review in the GitHub UI before merge.

## License

Apache License 2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
