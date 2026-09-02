# XGIC Wagtail

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](LICENSE)

**Thin Wagtail site template.** Use this repository as the GitHub Template for a
new Wagtail site. Official Python and Postgres images; Wagtail 8.0 via pip.
Schema lives here. The producer documents pins; it is not the app start.

Standards hub: [xgic/ai](https://github.com/xgic/ai) · Default CMS:
[ADR-0006](https://github.com/xgic/ai/blob/main/docs/adr/0006-adopt-wagtail.md)

---

## Quick start

1. Click **Use this template** (or clone this repo).
2. Reopen in the Dev Container (Compose-first).
3. Install pins and create an empty site (no custom schema yet):

```bash
python -m pip install -r requirements.txt
wagtail start mysite .
# then point Django DATABASES at the Compose Postgres service
```

Default Compose services:

| Service | Image |
|---------|--------|
| `xgic-wagtail` | `python:3.14-bookworm` |
| `postgres` | `postgres:18-bookworm` |

Pins are owned by [xgic/wagtail-dev](https://github.com/xgic/wagtail-dev). Do not
introduce a custom GHCR image in this template until that producer publishes one
for a measured need.

CLI: [xgic/wagtail-cli](https://github.com/xgic/wagtail-cli) (`xgic wagtail …`).

---

## Empty-site gate

Record memory and cold-start on a constrained Linux environment **before** adding
schema. Do not start StreamField / relational content models in this bootstrap.

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Human review in the GitHub UI before merge.

## License

Apache License 2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE).
