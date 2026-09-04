# Compatibility Promise

This repository defines the contract compatibility guarantees for public schemas in the 0luka ecosystem.

## Transition & Architecture Status (September 2026)

1. **Active Inter-Module Contracts**:
   - Active cross-repo contracts are now defined via `graft/` directories directly in each repository under the **0LU-1076 Project Orientation Standard**.
   - Canonical system governance, agent transport policies, and dispatch laws reside in [`Ic1558/0luka`](https://github.com/Ic1558/0luka) (`CONTRACT.yaml`, `.agent/SOT.md`).

2. **Contract Preservation & Freezing**:
   - Existing contracts in `contracts/v1/` (including `opal_api.openapi.json`) are frozen and preserved for historical compatibility.
   - Any module consuming `contracts/v1/` contracts can rely on zero breaking changes.

## Guarantees

1. **Semantic Versioning**
   - MAJOR: breaking contract changes
   - MINOR: backward-compatible additions
   - PATCH: clarifications or fixes

2. **Backward Compatibility**
   - No breaking changes in MINOR or PATCH versions
   - New fields must always be optional

3. **Deprecation Policy**
   - Deprecated items must be clearly marked
   - Removal only allowed in next MAJOR version
   - Migration notes must be provided

4. **Multi-Version Support**
   - Multiple contract versions may coexist (`v1`, `v2`, ...)
   - Modules choose which version to consume explicitly

## Non-Goals

- This repo contains **no runtime code**
- No infrastructure, credentials, or deployment logic
- No UI or executor implementation
- No dynamic governance or routing law (owned by `Ic1558/0luka`)
