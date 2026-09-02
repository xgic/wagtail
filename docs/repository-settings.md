# Repository settings (template)

Public operational notes for maintainers of
[xgic/wagtail](https://github.com/xgic/wagtail).

## Branch protection

`main` is protected:

| Rule | Intent |
|------|--------|
| No force-push / no deletion of `main` | History integrity |
| Pull request required (1 approval) | Human UI review |
| Linear history | Clean default branch |
| Required status check **Compose config** | Docker Compose–first contract |

Image build status checks live on [wagtail-dev](https://github.com/xgic/wagtail-dev).

## Labels

Apply PR labels consistently (`documentation`, `bug`, `enhancement`, `chore`, …).

## Related

- [AGENTS.md](../AGENTS.md)
- [CONTRIBUTING.md](../CONTRIBUTING.md)
- [xgic/ai BASE-STANDARDS](https://github.com/xgic/ai/blob/main/docs/BASE-STANDARDS-FOR-ORCHESTRATED-REPOS.md)
- [README standards (hub)](https://github.com/xgic/ai/blob/main/docs/readme-standards.md)
