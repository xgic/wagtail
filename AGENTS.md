# AI Agent Instructions — XGIC Wagtail

Public repository. Follow https://github.com/xgic/ai for multi-repo standards.

## Product

- **Role:** thin end-user Wagtail **template** (GitHub Template)
- **Producer image:** `ghcr.io/xgic/wagtail-dev:0.1.2` from https://github.com/xgic/wagtail-dev
- **CLI:** https://github.com/xgic/wagtail-cli (`xgic wagtail …`)
- **CMS decision:** [ADR-0006](https://github.com/xgic/ai/blob/main/docs/adr/0006-adopt-wagtail.md)

## Scope

- Empty-site start consuming the pinned producer image
- Compose overrides only as needed for the empty template
- Product StreamField / relational models belong in consumer site repositories, not this template
- Dev Container `remoteUser` is `vscode` (image user). Not a `wagtail` OS user. Compose sets `user: "0:0"` so the image entrypoint can align the `docker` group to the mounted engine socket, then exec as `vscode`.
- Docker-outside-of-Docker: `/var/run/docker.sock` is mounted. The producer image supplies the Docker CLI. Do not enable Docker-in-Docker.
- Compose identity: `name: xgic-wagtail` plus `XGIC_COMPOSE_PROJECT` / `XGIC_PRIMARY_SERVICE` on the primary service.
- `xgic wagtail setup` for first-run PostgreSQL (not SQLite; not raw `wagtail start` alone). Setup also inserts `django.contrib.postgres` into generated `INSTALLED_APPS`.
- `xgic wagtail dev` for migrate + `runserver 0.0.0.0:8000`.
- GitHub remotes: prefer HTTPS (VS Code host credential helper). Producer image installs `openssh-client` for other SSH hosts. Do not copy host private keys.
- Hybrid Django templates + Next.js later (not this bootstrap)

## Out of scope

- Defining the producer image (that belongs in xgic/wagtail-dev)
- Duplicating producer environment pins (Wagtail / `psycopg` in `requirements.txt`)
- Inventing a GHCR tag before the producer publishes one
- Private host defaults
- Payload CMS template work
- StreamField / extra relational content models (this repository stays an empty template)
- Empty-site footprint: recorded and accepted (https://github.com/xgic/wagtail/issues/3)

## Rules

**Public GitHub writes:** Before `gh issue create|edit`, `gh pr create|edit`, or any public comment on this repository, complete the **mandatory public-safe draft gate** in https://github.com/xgic/ai/blob/main/docs/BASE-STANDARDS-FOR-ORCHESTRATED-REPOS.md.
- Public-safe content only
- Human UI review before merge to `main`
- Dedicated issue-number branches; Conventional Commits
- **Labels required**
- Apache-2.0; root `CODEOWNERS` (`@xgic`)
