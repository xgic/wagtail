# XGIC Wagtail

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)
[![Docker Compose](https://img.shields.io/badge/Docker-Compose-blue?logo=docker&logoColor=white)](https://docs.docker.com/compose/)
[![Producer release](https://img.shields.io/github/v/release/xgic/wagtail-dev?label=wagtail-dev&logo=github)](https://github.com/xgic/wagtail-dev/releases)
[![GHCR image](https://img.shields.io/badge/GHCR-wagtail--dev-blue?logo=github)](https://github.com/users/xgic/packages/container/package/wagtail-dev)
[![Use this template](https://img.shields.io/badge/GitHub-Use_this_template-24292f?logo=github)](https://github.com/xgic/wagtail/generate)
[![CI](https://github.com/xgic/wagtail/actions/workflows/ci.yml/badge.svg)](https://github.com/xgic/wagtail/actions/workflows/ci.yml)
[![Wagtail](https://img.shields.io/badge/Wagtail-8.0-2E1F5E?logo=wagtail&logoColor=white)](https://docs.wagtail.org/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-18-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/docs/18/)

## The optimal way to start Wagtail sites

**For humans and AI coding assistants.**

This repository is XGIC’s **recommended starting point** for new [Wagtail](https://wagtail.org) sites ([docs](https://docs.wagtail.org/)). It gives you a **reproducible Dev Container**, a **pinned multi-arch environment image**, and a **single CLI brand**.

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
xgic wagtail setup
xgic wagtail dev
```

`xgic wagtail setup` is idempotent: it writes `create-wagtail-config.json` / `.devcontainer/.env` when missing, runs `wagtail start` if there is no site yet, points Django at **PostgreSQL** (Compose service `postgres`), and inserts `django.contrib.postgres` into the generated `<project>/settings/base.py` `INSTALLED_APPS` (immediately before `django.contrib.admin`). `wagtail start` alone would leave SQLite in `settings/base.py`; that is not the XGIC default.

`xgic wagtail dev` waits for PostgreSQL, runs `migrate --noinput`, then
`python manage.py runserver 0.0.0.0:8000` (port 8000 forwarded by the Dev Container).

The Dev Container mounts the host Docker engine socket. After the producer
image that ships a Docker CLI is pinned, `docker` / `xgic logs` / `xgic check`
inside the container talk to that engine (Docker-outside-of-Docker, not
Docker-in-Docker). `.devcontainer/.env` is written by `xgic wagtail setup`;
it is expected to be missing on a clean template clone.

Wagtail and `psycopg` ship in `ghcr.io/xgic/wagtail-dev`. Environment pins live in [xgic/wagtail-dev](https://github.com/xgic/wagtail-dev) (`requirements.txt` baked into the image). The producer image also installs **XGIC CLI** from PyPI (`xgic-wagtail-cli`, which depends on `xgic-cli`). After setup, keep extra site packages in the generated project. Refresh JSON Schema IntelliSense with `xgic wagtail schema`.

Host-only (no Dev Container):

```bash
uv pip install "xgic-wagtail-cli>=0.1.0"
```

That pulls `xgic-cli>=0.2.1` from package metadata. Do not list core and
the module together unless you are pinning an override.

Compose pins `ghcr.io/xgic/wagtail-dev:0.1.2` ([GitHub Release](https://github.com/xgic/wagtail-dev/releases/tag/v0.1.2)).

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

## XGIC standards

- [BASE-STANDARDS](https://github.com/xgic/ai/blob/main/docs/BASE-STANDARDS-FOR-ORCHESTRATED-REPOS.md)
- [README standards](https://github.com/xgic/ai/blob/main/docs/readme-standards.md)
- Agents: [AGENTS.md](AGENTS.md)

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Human review in the GitHub UI before merge.

## License

Apache License 2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
