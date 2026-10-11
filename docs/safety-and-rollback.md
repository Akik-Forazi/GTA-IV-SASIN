# Safety & Rollback Runbook — GTA IV: SASIN

**Revision 2 (2026-10-11).** Expands the prior one-page plan into an executable runbook. Hard rules first, then procedures.

## Non-negotiable rules
1. **Never modify, overwrite, move, or delete any original game file.** Loader DLLs are *additions*; if any step would overwrite an existing file (a conflicting `dinput8.dll`, etc.), the step **aborts** and the conflict is documented for user decision.
2. **No installation without explicit user approval** (canon-ledger 6.4). Every loader/patch file is listed in `docs/poc-file-manifest.md` before it is copied.
3. **No full-game duplication** (~22.6 GB install vs ~20 GB free): rollback is file-targeted, not directory cloning.
4. **Everything project-side stays in the project folder** (`…\GTA-IV-SASIN\`), never inside `GTAIV\`.
5. No test may be reported as passed unless a log exists in `logs/` with date, build, and result.

## Disk safety
- Project folder footprint target: < 200 MB (text assets, logs, small binaries).
- Before first install: confirm ≥ 3 GB free on the system drive (log it). If below, stop and free space — the game plus OS swap on a nearly-full drive is a crash generator, not a modding environment.

## Baseline capture (once, before any install)
1. Record game build: right-click `GTAIV.exe` → Properties → Details → record Product/File version into `logs/baseline_build.txt`. Expected 1.2.0.59 (verify — do not assume).
2. Record inventory: from an elevated PowerShell in `GTAIV\`: `Get-ChildItem -Recurse -File | Select-Object FullName,Length | Export-Csv …\logs\baseline_inventory.csv` (names and sizes only — no copies).
3. Note launcher type (Rockstar Games Launcher / Steam) in `logs/baseline_build.txt` — rollback via "verify files" differs between them.

## Install procedure (per candidate runtime; executed only after user approval)
1. Download the loader/runtime from its official page (compatibility-matrix.md sources) — record the exact version and URL in `docs/poc-file-manifest.md`.
2. Stage downloads in `…\GTA-IV-SASIN\downloads\` (never run installers from temp).
3. Copy **only** the manifest-listed files into `GTAIV\`. If a destination file already exists → **abort**, document the conflict, choose a non-conflicting proxy-DLL name per the loader's documented options.
4. Boot the game once, confirm menu + loader log, quit cleanly.
5. Log everything to `logs/install_<date>.log`.

## Rollback procedure (proven at PoC P3)
1. Quit the game.
2. Delete exactly the files listed in `docs/poc-file-manifest.md` (and only those).
3. Diff the current inventory against `baseline_inventory.csv` — confirm zero unexpected changes; record the diff in `logs/rollback_<date>.log`.
4. Boot the game once vanilla to confirm clean state.

## Failure handling
| Symptom | First response |
|---|---|
| Game won't boot after install | Remove manifest files (rollback), retry candidate #2 runtime, log the failure |
| Loader log absent | Wrong DLL name/conflict → check manifest step 3 notes |
| Crash during P2 cinematic | Halve the sequence (camera-only, then text-only), isolate the failing native, log native name + parameters |
| Save/profile oddities | Project never writes saves; verify by rolling back and re-testing — then file an issue note before proceeding |
| Disk < 3 GB free at any point | Stop all testing until space is freed |

## What this project will never do
- Modify game archives (no OpenIV edits to originals), replace executables, downgrade builds, install graphics injectors, or touch online components.
- Store credentials, tokens, or personal data anywhere in the repository (see README; CI-less static content only).
