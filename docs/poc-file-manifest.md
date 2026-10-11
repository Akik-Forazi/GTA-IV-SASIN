# PoC File Manifest

**Purpose:** every file this project adds to `GTAIV\` is listed here **before** copying (safety-and-rollback.md rule 2). Rollback deletes exactly this list. The manifest starts empty — entries are appended during local install, by the user, with version provenance.

## Candidate #1 — LuaModLoader
| # | File added to `GTAIV\` | Source (official page + version) | Date added | SHA-256 (optional) |
|---|------------------------|----------------------------------|------------|--------------------|
| — | *(none yet — nothing has been installed)* | nexusmods.com/gta4/mods/1313 | — | — |

## Candidate #2 — ScriptHookDotNet CE fork + Ultimate ASI Loader
| # | File added | Source | Date added | Notes |
|---|-----------|--------|------------|-------|
| — | *(none yet)* | — | — | |

## Conflicts encountered (abort log)
| Destination file already existed | Resolution |
|----------------------------------|------------|
| — | — |

**Rule:** an empty manifest means a vanilla game. If the manifest is non-empty, `logs/rollback_*.log` must exist proving the files were removed and vanilla boot confirmed.
