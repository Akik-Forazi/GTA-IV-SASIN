# Local Verification Checklist — GTA IV: SASIN

**Context:** this repository is developed in a remote workspace with **no access** to the Windows machine, the game install, or the target laptop. Everything marked UNVERIFIED elsewhere is discharged here, by the user, in order. Each step appends to the referenced log file. Nothing may be marked verified in `docs/compatibility-matrix.md` without the matching log.

## 0. Preflight (no installation)
- [ ] `GTAIV.exe` present at the expected path; Properties → Details → version recorded to `logs/baseline_build.txt` (expected 1.2.0.59 — **record what you see**)
- [ ] Launcher type noted (Rockstar / Steam) in the same log
- [ ] ≥ 3 GB free on system drive (record the number)
- [ ] `baseline_inventory.csv` captured per safety-and-rollback.md
- [ ] Game boots vanilla once; graphics preset noted (start: 720p, medium-low)

## 1. Runtime candidate #1 — LuaModLoader (after user approval)
- [ ] Download exact version + URL recorded into `docs/poc-file-manifest.md`
- [ ] Files staged in project `downloads\`, manifest list written **before** copying
- [ ] Copy into `GTAIV\` (abort on any file conflict)
- [ ] P0 gate: boot to menu, loader log present, vanilla behavior unchanged → `logs/poc_p0.log`
- [ ] P1 gate: subtitle natives draw two lines; native names logged → `logs/poc_p1.log`
- [ ] **If P0/P1 fail:** stop, log the failure mode, switch to candidate #2 (ScriptHookDotNet CE fork) — do not debug beyond 30 minutes before switching

## 2. PoC cinematic
- [ ] P2 gate: 60–90 s cinematic plays end-to-end twice → `logs/poc_p2.log` (FPS + notes)
- [ ] P3 gate: rollback executed, vanilla confirmed, reinstall + replay identical → `logs/poc_p3.log`
- [ ] Screen recording optional; stored in git-ignored `cinematics/renders/`

## 3. Post-PoC decisions (user)
- [ ] Approve/adjust runtime choice based on logs
- [ ] Approve persistence mechanism (native vs. project-folder JSON profile)
- [ ] Approve scene-budget rules from measured FPS (technical-architecture.md)

## 4. Then, and only then
- Mission scripting begins (Act I missions as data files, one at a time per Readmap Stage 8), each gated by a smoke test log.

## Honesty rule
A checkbox without a log is a claim, not a verification. No exceptions — this checklist exists because the prior compatibility doc fabricated "VERIFIED LOCALLY" rows.
