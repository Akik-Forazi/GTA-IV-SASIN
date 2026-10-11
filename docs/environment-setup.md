# Environment Setup Guide — GTA IV: SASIN

**Revision 2 (2026-10-11).** Remote workspace (story/tech development) vs. local machine (execution) are separated; only the user's machine can run anything.

## Local machine (target laptop — the only execution environment)
- Windows 11 x64, HP EliteBook 840 G5, i5-8350U, Intel UHD 620, ~16 GB RAM.
- Game at `C:\Users\user\akik\Games\Grand.Theft.Auto.IV.Complete.Edition.v1.2.0.59\GTAIV\` (starting point — verify, don't assume; checklist step 0).
- Project workspace beside it: `C:\Users\user\akik\Games\Grand.Theft.Auto.IV.Complete.Edition.v1.2.0.59\GTA-IV-SASIN\` — **never inside the game folder**.
- No build toolchain is required while the runtime candidate is Lua-based (a deciding factor; see technical-architecture.md). If the .NET fallback is activated: .NET Framework requirements per ScriptHookDotNet CE fork's page.

## Remote workspace (this repository)
- Content only: story documents, mission data drafts, runbooks, manifests. No credentials, no game assets, no binaries beyond loader manifests (files are downloaded locally from official pages, never committed).

## Sync flow
1. Remote: docs + mission data authored and pushed to GitHub.
2. Local: `git pull` in the project folder.
3. Local: run checklist steps; logs stay local (git-ignored) except when a user chooses to commit a redacted copy.
