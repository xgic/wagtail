# AI Agent Instructions — XGIC Wagtail

Public repository. Follow https://github.com/xgic/ai for multi-repo standards.

## Product

- **Role:** thin end-user Wagtail **template** (GitHub Template)
- **Producer image:** `ghcr.io/xgic/wagtail-dev:0.1.1` from https://github.com/xgic/wagtail-dev
- **CLI:** https://github.com/xgic/wagtail-cli (`xgic wagtail …`)
- **CMS decision:** [ADR-0006](https://github.com/xgic/ai/blob/main/docs/adr/0006-adopt-wagtail.md)

## Scope

- Site schema, extensions, and Compose overrides
- Empty-site start consuming the pinned producer image
- `xgic wagtail setup` for first-run PostgreSQL (not SQLite; not raw `wagtail start` alone). Setup also inserts `django.contrib.postgres` into generated `INSTALLED_APPS`.
- Hybrid Django templates + Next.js later (not this bootstrap)

## Out of scope

- Defining the producer image (that belongs in xgic/wagtail-dev)
- Duplicating producer environment pins (Wagtail / `psycopg` in `requirements.txt`)
- Inventing a GHCR tag before the producer publishes one
- Private host defaults
- Payload CMS template work
- Measuring empty-site footprint belongs in a dedicated follow-up issue

## Rules

**Public GitHub writes:** Before `gh issue create|edit`, `gh pr create|edit`, or any public comment on this repository, complete the **mandatory public-safe draft gate** in https://github.com/xgic/ai/blob/main/docs/BASE-STANDARDS-FOR-ORCHESTRATED-REPOS.md.
- Public-safe content only
- Human UI review before merge to `main`
- Dedicated issue-number branches; Conventional Commits
- **Labels required**
- Apache-2.0; root `CODEOWNERS` (`@xgic`)
