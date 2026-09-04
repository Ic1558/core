# PROJECT.md — core (Historical SOT & Contracts Archive)

## What this is

`core` historically served as the contracts Source of Truth (SOT) repository for the 0luka ecosystem, holding public API contracts (such as OPAL API OpenAPI specs in `contracts/v1/`).

## Architecture Status (September 2026 / Foundation Recovery F0–F4)

- **Transition to 0luka Kernel**: Canonical governance laws, agent routing contracts, and system orientation have transitioned directly into [`Ic1558/0luka`](https://github.com/Ic1558/0luka) (`CONTRACT.yaml`, `.agent/SOT.md`, `core_brain/governance/`).
- **Transition to 0LU-1076 Grafts**: Active inter-module contracts and dependency boundaries are now maintained via `graft/` directories in each respective repository.
- **Contract Archive**: This repository is maintained as a frozen, backward-compatible archive for public API contracts in `contracts/v1/`.

## Active Scope

- Backward-compatible OpenAPI schemas (`contracts/v1/opal_api.openapi.json`).
- Semantic versioning and compatibility guarantees (`COMPATIBILITY.md`).
- Historical contract reference.

## Explicit Non-Scope

- **No runtime code**: Zero daemons, workers, or scripts.
- **No infrastructure**: Zero deployment configurations, Wrangler, or launchd files.
- **No active governance or routing law**: Managed exclusively by `Ic1558/0luka`.
- **No application or UI logic**: Managed in external engine repos (`qs`, `edge-staff`, `edge-apple`, `theedges-web`, `0luka-engine`).
