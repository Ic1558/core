# Compatibility Promise

This repository defines the **Source of Truth (SOT)** for all 0luka-related modules.

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
