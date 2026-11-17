# Our names

Names the Vagrant Story port used where upstream already names the address. Upstream's name stands; the
port adopts it when its address constants are generated from these maps.

## Upstream symbol map or matched source names

| address | upstream | port | port file |
|---|---|---|---|
| `0x8001F5EC` | `__main` | `cxxMain` | `game/boot/resident_facts.h` |
| `0x80026A04` | `ChangeClearPAD` | `cardStop` | `game/boot/resident_facts.h` |
| `0x80026974` | `EnterCriticalSection` | `cardStart` | `game/boot/resident_facts.h` |
| `0x8002EA40` | `ReadInitPadFlag` | `cardProbe` | `game/boot/resident_facts.h` |
| `0x8002EE84` | `InitCARD2` | `cardConfigure` | `game/boot/resident_facts.h` |
| `0x8002F094` | `_copy_memcard_patch` | `cardConfigureEvents` | `game/boot/resident_facts.h` |
| `0x8002EF90` | `_patch_card` | `cardConfigureHardware` | `game/boot/resident_facts.h` |
| `0x8002F024` | `_patch_card2` | `cardConfigureSoftware` | `game/boot/resident_facts.h` |
| `0x8002EEB4` | `_patch_card_info` | `cardConfigureFilesystem` | `game/boot/resident_facts.h` |
| `0x80026984` | `ExitCriticalSection` | `cardResume` | `game/boot/resident_facts.h` |
| `0x8002EE94` | `StartCARD2` | `cardStartCom` | `game/boot/resident_facts.h` |
| `0x8001E5C4` | `SsUtReverbOff` | `reverbOff` | `game/boot/resident_facts.h` |
| `0x80071334` | `vs_title_exec` | `titleEntry` | `game/boot/resident_facts.h` |
| `0x8001E5E4` | `SsUtReverbOn` | `reverbOn` | `game/boot/resident_facts.h` |
| `0x8004271C` | `gpuSyncVoidCallback` | `gpuSyncCallback` | `game/boot/resident_facts.h` |
| `0x80013230` | `Sound_SetCdMixVolume` | `setCdVolume` | `game/boot/resident_facts.h` |
| `0x8005E24C` | `vs_gametime_tickspeed` | `gameTimeTickSpeed` | `game/boot/resident_facts.h` |
| `0x80021470` | `CD_cw` | `cdCommand` | `game/cd/cd_facts.h` |
| `0x800443CC` | `diskUpdate` | `diskStateMachine` | `game/cd/cd_facts.h` |
| `0x800BC2E8` | `vs_battle_script_Cx_Dx_camera` | `cameraCommand` | `game/frame/battle_draw_facts.h` |
| `0x8007CCF0` | `vs_battle_setProjectionDistance` | `battleProjectionDistanceSetter` | `game/render/battle_projection_facts.h` |
| `0x8005E248` | `vs_main_projectionDistance` | `projectionDistanceWord` | `game/render/battle_projection_facts.h` |
| `0x8005E0C8` | `vs_main_nearClip` | `nearClipWord` | `game/render/battle_projection_facts.h` |
| `0x800F1DC9` | `backgroundVisible` | `tiledBackdropShown` | `game/render/battle_sky.cpp` |
| `0x800F1DCC` | `backgroundLayout` | `tiledBackdropLayout` | `game/render/battle_sky.cpp` |
| `0x8006A778` | `drawSprt` | `drawSprite` | `game/render/title_splash_facts.h` |
| `0x8006A49C` | `initMemcard` | `titleMemcardTransfer` | `game/save/title_memcard_facts.h` |
| `0x8006E988` | `saveFileExists` | `titleSaveScreen` | `game/save/title_save_facts.h` |

Several of the port's boot names were wrong: `0x80026974`/`0x80026984` are `EnterCriticalSection`/`ExitCriticalSection`,
`0x80026A04` is `ChangeClearPAD`, and the `0x8002EExx`-`0x8002F0xx` group is libcard's `InitCARD2`/`StartCARD2`/`_patch_card*`.

## Upstream source globals placed by the port

Defined in upstream `src/SLUS_010.40/main.c` with no symbol-map entry; the address is the port's, consistent with
main.c's declaration order (`sfxData` 0x5800 bytes from `0x80050478` ends where `resetEnabled`'s neighbours start;
`buttonHeldFrameCount[32]` at `0x80055C90` ends at `disk` `0x80055D10`; `vs_main_drawEnv[2]` at `0x8005E0D0` ends at
`vs_main_dispEnv` `0x8005E188`). They sit in `config/SLUS_010.40/symbol_addrs_findings.txt`.

| upstream | port |
|---|---|
| `vs_main_titleScreenCount` | `titleScreenCount` |
| `vs_main_startState` | `titleStartState` |
| `disk` | `vs_main_disk` |
| `vs_main_padBuffer` | `padBuffer0` |
| `vs_main_drawEnv` | `battleDrawEnv` |
| `vs_main_dispEnv` | `residentDispEnv` |
| `vs_main_saveGameClearData` | `saveGameClearData` |
| `vs_main_buttonsState` | `buttonsState` |
| `vs_main_settings` | `settings` |
| `vs_main_gametime` | `gameTime` |
| `vs_main_stateFlags` | `stateFlags` |
| `vs_main_inventoryIndices` | `inventoryIndices` |

## No image

`0x8010C000` (the heap arena `vs_main_initHeap` is given at boot) and `0x80068800` (the overlay load base) are
addresses, not symbols of any image.
