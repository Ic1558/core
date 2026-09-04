# AGENTS.md — core

## Operating Discipline

This repository is a contracts archive. It contains no runtime code.

### Operating Law: CODE_DRIVING Continuity (0LU-1085)
- **Continuous Execution**: `test -> commit -> push -> continue`.
- **Open PRs**: An open PR is an active handoff to GG, never an idle waiting state.
- **Scope Discipline**: Do not add application code, runtime scripts, or private credentials to this repo.

### Hard Invariants
1. **No Breaking Contract Changes**: All schemas in `contracts/v1/` are frozen. Any additions must be strictly backward-compatible.
2. **Governance Lives in 0luka**: Do not recreate governance or agent routing laws here. System governance belongs exclusively in `Ic1558/0luka`.
3. **No Secrets**: Never commit `.env` or credential files.
