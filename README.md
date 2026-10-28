# Zhongwen Patch

<img=https://imgur.com/a/jPoeVtE>

Chinese text and extras for the PC version of Resident Evil 2 (1998)
running on [Classic REbirth](https://classicrebirth.com).

为 Classic REbirth 上的《生化危机2》PC 版提供中文文本与扩展功能（非官方）。

> **Status:** in development. Version 0.9 is not the final version; 1.0 is
> being prepared.
>
> **Unofficial.** Zhongwen Patch is not affiliated with or endorsed by
> Gemini (Classic REbirth), Capcom or Sourcenext.

## What it does

- **Chinese on Classic REbirth** (`re2cn.dll`): title, menus, messages,
  items, documents, the opening narration, the EX.BATTLE briefing and the
  results screens, drawn from the Chinese data of your install. The
  Simplified and Traditional builds are detected by themselves.
- **Door Hotkey**: hold a key and doors, ladders and lifts are used on the
  first frame you reach them, under the same rules as the action button.
- **Rebind controls**: keyboard keys and controller buttons for every
  action, from Classic REbirth's CONFIGURATION window.
- **Supreme Skip support**: the Supreme level of the Door & Cutscene Skip
  mod in one option, with cutscenes skippable for as long as they play and
  fixes for some skipped scenes. The mod and its update are not included.
- **Fixes in memory**: the Sourcenext update's corrections to the Chinese
  discs' rooms, the results screen in Chinese, the main hall's emergency
  ladder, and a lock that keeps the discs' Indeo 5 movies (which crash
  Classic REbirth 1.0.9) off.
- **CONFIGURATION window**: "Enable Chinese", the patch's mods first in
  MOD SELECTION, and a Zhongwen Patch line under Classic REbirth's own.

## How it works

Nothing original is modified, neither the game's files nor Classic
REbirth's. Two separate DLLs change the game's code in memory:

- `re2cn.dll` is a mod module that Classic REbirth loads itself;
- `xinput9_1_0.dll` passes every XInput call on to Windows and loads
  before Classic REbirth's CONFIGURATION window.

Files reach the game through Classic REbirth's mod system or are
redirected as they are read.

## Requirements

- The Chinese PC release of Resident Evil 2 (生化危机2): the retail
  Simplified discs (Leon, Claire or both).
- [Classic REbirth](https://classicrebirth.com) for Resident Evil 2
  (`ddraw.dll`).
- `bio2 1.10.exe`, from Sourcenext's official 1.1.0 update, the only
  executable Classic REbirth accepts.
- The Sourcenext language data the mods are built from (`bio2xp.7z`).
- 7-Zip. To build from source: llvm-mingw (i686).
- Optional, for Supreme Skip only: Resevilnemesis30's Door & Cutscene Skip
  mod (`RE2_Door_Cutscene_Skip_*.7z`) and descawed's update
  (`cutscene_skip_update_1.1.zip`). Put them in `_ZhongwenPatch` and run
  `Set up Supreme Skip.bat` to prepare the files.

The Chinese text is read from the Leon disc's `REGIST\leon.exe`. With
only the Claire disc installed, play in English or Japanese for now.

## Building

    sh src/build.sh <path/to/i686-w64-mingw32-gcc>
    powershell -ExecutionPolicy Bypass -File Install-ZhongwenPatch.ps1

## Not included

This repository holds only the patch's own code and texts. It does not
include Classic REbirth, `bio2 1.10.exe`, any game data, the Sourcenext
files or the Door & Cutscene Skip mod: bring your own copies.

## Credits

- Classic REbirth: Gemini
- Door & Cutscene Skip: Resevilnemesis30; update 1.1: descawed
- Resident Evil 2 / Biohazard 2 / 生化危机2: Capcom. PC edition and its
  1.1.0 update: Sourcenext. Chinese editions: Capcom Asia, published by
  Shanghai Ubi Soft (mainland China) and The Third Wave (Taiwan).

  
