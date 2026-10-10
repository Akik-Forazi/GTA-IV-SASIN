# Technical Architecture — GTA IV: SASIN

## Overview
SASIN uses a hybrid architecture designed to maintain high performance and separation of concerns on GTA IV Complete Edition (v1.2.0.59).

### 1. Native Layer (C++ ASI)
- Loaded via Ultimate ASI Loader (`version.dll`).
- Manages memory hooks (via MinHook), game state observation, input polling, and persistence storage.
- Interfacing with native game functions and memory heaps.

### 2. Campaign Definition Layer (Lua / JSON)
- Mission logic, trigger volumes, objective tracking, and dialogue sequences defined in external JSON/Lua files.
- Allows hot-reloading and rapid iteration without recompiling native binaries.
