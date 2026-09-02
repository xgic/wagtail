# AI Agent Instructions — XGIC Wagtail

Public repository. Follow https://github.com/xgic/ai for multi-repo standards.

## Product

- **Role:** thin end-user Wagtail **template** (GitHub Template)
- **Pins:** https://github.com/xgic/wagtail-dev (official Python/Postgres; `wagtail==8.0`)
- **CLI:** https://github.com/xgic/wagtail-cli (`xgic wagtail …`)
- **CMS decision:** [ADR-0006](https://github.com/xgic/ai/blob/main/docs/adr/0006-adopt-wagtail.md)

## Scope

- Site schema, extensions, and Compose overrides
- Empty-site start on official images
- Hybrid Django templates + Next.js later (not this bootstrap)

## Out of scope

- Custom producer GHCR image (deferred)
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
