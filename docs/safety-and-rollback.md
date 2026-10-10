# Safety and Rollback Plan

## Core Safety Rules
1. Never modify or overwrite vanilla game files in `GTAIV/`.
2. Given C drive free space constraints (~20 GB free vs ~22.6 GB game size), full directory duplication of the game is impractical.
3. **Alternative Rollback Strategy:** Maintain a pristine backup archive of modified DLL/ASI files only, or use a targeted file verification check via Steam/Launcher if binary corruption occurs.
4. Keep all project code and docs strictly inside `GTA-IV-SASIN/`.
