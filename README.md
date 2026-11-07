# core — Source of Truth for Contracts

**Version:** 1.1.0
**Status:** Contracts, schemas, and semantics (SOT) that modules conform to. System-agnostic.

## About

This repository holds the **canonical contracts** that define how modules communicate. All modules must conform to them. It was started under the legacy 0luka system and is kept deliberately small so any system can consume it. The current system is [LukaOS](https://github.com/Ic1558/lukaos).

### What This Repo Contains

| File | Purpose |
|------|---------|
| `contracts/v1/` | OpenAPI contracts (API schemas) |
| `COMPATIBILITY.md` | Semantic versioning + backward compatibility guarantees |
| `CHANGELOG.md` | Version history |
| `VERSION` | Current version (1.1.0) |

### What This Repo Does NOT Contain

- Runtime code
- Infrastructure or deployment logic
- Credentials or secrets
- UI or executor implementation

## Current Contracts

### v1 — OPAL API

Inherited from the legacy 0luka/02luka OPAL pipeline.

- `GET /api/jobs` — Returns map of job_id → JobDetail
- More endpoints defined in `contracts/v1/`

See `contracts/v1/` for full OpenAPI specs. LukaOS-specific contracts are not defined here yet.

## Version Policy

See `COMPATIBILITY.md` for semantic versioning rules, backward compatibility guarantees, deprecation policy and multi-version support.

## Integration

1. Clone or reference this repo
2. Import the OpenAPI spec from `contracts/v1/`
3. Ensure your module conforms to the contract version you consume

## Related Repos

- [Ic1558/lukaos](https://github.com/Ic1558/lukaos) — current system (Rust local-first runtime)
- [Ic1558/qs](https://github.com/Ic1558/qs) — Quantity Surveying module
- [Ic1558/0luka](https://github.com/Ic1558/0luka) — legacy system, superseded by LukaOS
