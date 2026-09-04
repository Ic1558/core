# PROJECT.md — core (Contracts Source of Truth)

## What this is

`core` is the active contracts Source of Truth (SOT) repository for the 0luka ecosystem, holding canonical public API contracts (such as OPAL API OpenAPI specs in `contracts/v1/`), interface schemas, and versioned data contracts.

## Architecture Status (September 2026)

- **Division with Kernel**: Dynamic pipeline execution and system governance laws live in [`Ic1558/0luka`](https://github.com/Ic1558/0luka) (`CONTRACT.yaml`, `.agent/SOT.md`), while `core` defines public API schemas and interface contracts.
- **Project Orientation (0LU-1076)**: Inter-module contracts and dependency boundaries reference these contracts via `graft/` directories in each respective repository.

## Active Scope

- Public OpenAPI schemas (`contracts/v1/opal_api.openapi.json`).
- Semantic versioning and backward-compatibility guarantees (`COMPATIBILITY.md`).
- Multi-version contract management (`v1`, `v2`, ...).

## Explicit Non-Scope

- **No runtime code**: Zero daemons, workers, or scripts.
- **No infrastructure**: Zero deployment configurations, Wrangler, or launchd files.
- **No active governance or routing law**: Managed exclusively by `Ic1558/0luka`.
- **No application or UI logic**: Managed in external engine repos (`qs`, `edge-staff`, `edge-apple`, `theedges-web`, `0luka-engine`).
