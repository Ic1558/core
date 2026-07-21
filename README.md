# core — 0luka Source of Truth

**Version:** 1.1.0  
**Status:** Contracts, schemas, and semantics (SOT) for 0luka modules and future systems

## About

This repository contains the **canonical contracts** that define how 0luka modules communicate. It is the **Source of Truth (SOT)** — all modules must conform to these contracts.

### What This Repo Contains

| File | Purpose |
|------|---------|
| `contracts/v1/` | OpenAPI contracts (API schemas) |
| `COMPATIBILITY.md` | Semantic versioning + backward compatibility guarantees |
| `CHANGELOG.md` | Version history |
| `VERSION` | Current version (1.1.0) |

### What This Repo Does NOT Contain

- ❌ Runtime code
- ❌ Infrastructure or deployment logic
- ❌ Credentials or secrets
- ❌ UI or executor implementation

## Current Contracts

### v1 — OPAL API

- `GET /api/jobs` — Returns map of job_id → JobDetail
- More endpoints defined in `contracts/v1/`

See `contracts/v1/` directory for full OpenAPI specs.

## Version Policy

See `COMPATIBILITY.md` for:
- Semantic versioning rules
- Backward compatibility guarantees
- Deprecation policy
- Multi-version support

## Integration

To use these contracts in your module:

1. Clone or reference this repo
2. Import the OpenAPI spec from `contracts/v1/`
3. Ensure your module conforms to the contract version you consume

## Related Repos

- [Ic1558/0luka](https://github.com/Ic1558/0luka) — Core system
- [Ic1558/qs](https://github.com/Ic1558/qs) — Quantity Surveying module
- [Ic1558/0luka-mission-control](https://github.com/Ic1558/0luka-mission-control) — Mission control dashboard