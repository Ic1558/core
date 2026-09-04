# core — 0luka Source of Truth & Contracts Archive

**Version:** 1.2.0  
**Status:** Contracts, schemas, and semantics for 0luka modules (Historical SOT & Contracts Archive)

> [!NOTE]
> **Architecture Transition Notice (September 2026 / Foundation Recovery F0–F4):**  
> Canonical governance laws, agent routing contracts, and system orientation have transitioned directly into [`Ic1558/0luka`](https://github.com/Ic1558/0luka) (`CONTRACT.yaml`, `.agent/SOT.md`, `core_brain/governance/`).  
> Active inter-module contracts and dependency boundaries are now maintained via `graft/` directories in each respective repository under the **0LU-1076 Project Orientation Standard**.  
> This repository is maintained as a frozen, backward-compatible archive for public API contracts (such as OpenAPI specs in `contracts/v1/`).

## About

This repository historically defined the contracts and interface schemas across 0luka modules. All active contracts here are preserved for backwards compatibility and integration reference.

### What This Repo Contains

| File / Directory | Purpose |
|---|---|
| `contracts/v1/` | OpenAPI contracts and public API schemas (e.g., OPAL API) |
| `COMPATIBILITY.md` | Semantic versioning + backward compatibility guarantees & migration notes |
| `CHANGELOG.md` | Version history |
| `VERSION` | Current version (1.2.0) |

### What This Repo Does NOT Contain

- ❌ Runtime code
- ❌ Infrastructure or deployment logic
- ❌ Credentials or secrets
- ❌ UI or executor implementation
- ❌ Dynamic governance or dispatch law (owned by `Ic1558/0luka`)

## Current Contracts

### v1 — OPAL API

- `GET /api/jobs` — Returns map of job_id → JobDetail
- OpenAPI specification: `contracts/v1/opal_api.openapi.json`

See `contracts/v1/` directory for full OpenAPI specs.

## Operating Law: CODE_DRIVING Continuity (0LU-1085)

All work in the 0luka ecosystem follows continuous execution:
- **One Objective = One Executor**: Do not spawn duplicate lanes.
- **Never Idle on PR / CI**: `test -> commit -> push -> continue`. An open PR is an active handoff to GG, not a stopping state.
- **Deterministic Orientation**: Read only the project orientation surfaces to ground context.

## Related Repositories (Active 6 Boundaries + Vault)

```
Active Boundaries (6 Active Repos):
Ic1558/0luka              ← kernel repo (pipeline, dispatch, governance, consult bus :8091, in-tree runtime adapters)
Ic1558/0luka-engine       ← external document OCR engine (thai_slip_ocr, Thai bank slips, v2.db @ icmini, paper trading)
Ic1558/qs                 ← Quantity Surveying & Takeoff workspace (HUD, touch/pointer geometry, BOQ pricing, preview worker)
Ic1558/edge-staff         ← internal staff portal (theedges.work/staff, Cloudflare Access, D1 edge-documents/expense_raw_payments)
Ic1558/edge-apple         ← native iOS/iPad shell (EdgeShellKit, native drawing/viewer, intake submission picker)
Ic1558/theedges-web       ← public website only (theedges.work marketing, preview3, client portal /client/{slug}; staff worker removed 0LU-1142)

Vault & Doctrine:
Ic1558/0luka-memory       ← vault: agent memory, handoffs, plans, postmortems (zero application code)
Ic1558/0luka-guide        ← doctrine, classification, priority, boundary decisions

Quarantined / Superseded:
Ic1558/0luka-mission-control ← quarantined: legacy observability dashboard
Ic1558/qs-pipeline        ← superseded: merged into Ic1558/qs
Ic1558/the-edge-sot       ← superseded: replaced by per-project .agent/SOT.md
Ic1558/edge-be            ← superseded: replaced by Cloudflare Workers and 0luka-engine
```