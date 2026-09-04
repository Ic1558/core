# core — 0luka Contracts Source of Truth

**Version:** 1.2.0  
**Status:** Active — Canonical contracts, schemas, and interface specifications (SOT) for 0luka modules

## About

This repository defines the **canonical public contracts** and interface specifications that govern how 0luka modules communicate. It is the active **Contracts Source of Truth (SOT)** — all modules must conform to these contracts.

### Division of Responsibility
- `Ic1558/0luka`: Owns dynamic kernel pipeline, task dispatch, and system governance laws (`CONTRACT.yaml`, `.agent/SOT.md`).
- `Ic1558/core`: Owns canonical public API contracts (OpenAPI schemas in `contracts/v1/`), interface definitions, and versioned data contracts consumed across modules.
- Inter-module dependency boundaries reference these contracts via `graft/` directories under the **0LU-1076 Project Orientation Standard**.

### What This Repo Contains

| File / Directory | Purpose |
|---|---|
| `contracts/v1/` | OpenAPI contracts and public API schemas (e.g., OPAL API) |
| `COMPATIBILITY.md` | Semantic versioning + backward compatibility guarantees |
| `CHANGELOG.md` | Version history |
| `VERSION` | Current version (1.2.0) |

### What This Repo Does NOT Contain

- ❌ Runtime code
- ❌ Infrastructure or deployment logic
- ❌ Credentials or secrets
- ❌ UI or executor implementation
- ❌ Dynamic kernel dispatch law (owned by `Ic1558/0luka`)

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

## Related Repositories (Active Architecture Ecosystem)

```
Active Core, Governance & Doctrine:
Ic1558/0luka              ← kernel repo (pipeline, dispatch, governance, consult bus :8091, in-tree runtime adapters)
Ic1558/core               ← this repo — contracts SOT (OpenAPI contracts, public schemas, interface doctrine)
Ic1558/0luka-guide        ← canonical doctrine, classification, priority, boundary decisions
Ic1558/0luka-memory       ← vault: agent memory, handoffs, plans, postmortems (zero application code)

Active Execution Boundaries (6 Primary Repos):
Ic1558/0luka-engine       ← external document OCR engine (thai_slip_ocr, Thai bank slips, v2.db @ icmini, paper trading)
Ic1558/qs                 ← Quantity Surveying & Takeoff workspace (HUD, touch/pointer geometry, BOQ pricing, preview worker)
Ic1558/edge-staff         ← internal staff portal (theedges.work/staff, Cloudflare Access, D1 edge-documents/expense_raw_payments)
Ic1558/edge-apple         ← native iOS/iPad shell (EdgeShellKit, native drawing/viewer, intake submission picker)
Ic1558/theedges-web       ← public website only (theedges.work marketing, preview3, client portal /client/{slug}; staff worker removed 0LU-1142)

Active Supporting Systems (Business SOT, Backend Broker, Observability):
Ic1558/the-edge-sot       ← canonical business foundation SOT (The EDGE company truth, storage surfaces, remote bridge rules)
Ic1558/edge-be            ← backend adapter and LAN broker (apps/control-plane, apps/lan-broker, remote operational control)
Ic1558/0luka-mission-control ← observability and mission dashboard surface (Next.js web app)

Quarantined / Superseded:
Ic1558/02luka             ← archived legacy kernel
Ic1558/qs-pipeline        ← superseded: merged into Ic1558/qs
```