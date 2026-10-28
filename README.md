# Zhongwen Patch

![image alt](https://github.com/kROM3r/zhongwenpatch/blob/4c27675b2c5bf102d7a4edc146bcdc1d3f70b544/image-1793210835067.png)

A chinese add-on mod with extras for the PC version of Resident Evil 2 (1998)
running on [Classic REbirth](https://classicrebirth.com).

为 Classic REbirth 上的《生化危机2》PC 版提供中文文本与扩展功能（非官方）。

> **Version 1.0**, the first public release: download it from
> [Releases](../../releases).
>
> **Unofficial.** Zhongwen Patch is not affiliated with or endorsed by
> Gemini (Classic REbirth), Capcom or Sourcenext.

## What it does

- **The game in Chinese on Classic REbirth** (`re2cn.dll`): title, menus,
  messages, items, documents, the opening narration, the EX.BATTLE briefing
  and ending message, and the results screens. All of it is drawn from the
  Chinese data of your install. Simplified and Traditional builds are
  detected by themselves. Untick "Enable Chinese" to play in English.
- **No violence warning at startup**, as in the 1999 Chinese release.
- **Door Hotkey**: hold a key and doors, ladders and lifts are used on the
  first frame you reach them, under the same rules as the action button.
- **Rebind controls**: keyboard keys and controller buttons for every
  action, from Classic REbirth's CONFIGURATION window.
- **Supreme Skip**: the Supreme level of Resevilnemesis30's Door & Cutscene
  Skip mod in one option. Cutscenes stay skippable for as long as they
  play, and the patch fixes, with its own code, the scenes that broke when
  skipped. The releases carry the mod's files already prepared, with
  credit, as its author allows.
- **生化危机2: SPEEDRUN EDITION**: Gemini's Speedrun Edition in Chinese.
  A setup makes it from your own copy of the Speedrun Edition, which is not
  included.
- **Fixes in memory**: the Sourcenext update's corrections to the discs'
  rooms, the results screen in Chinese, the main hall's emergency ladder,
  and a lock that keeps the discs' Indeo 5 movies off (they crash Classic
  REbirth 1.0.9).
- **CONFIGURATION window**: "Enable Chinese", a MOD SELECTION list with the
  two Chinese versions only, and a Zhongwen Patch line under Classic
  REbirth's own.

## How it works

Nothing original is modified, neither the game's files nor Classic
REbirth's. Two separate DLLs change the game's code in memory:

- `re2cn.dll` is a mod module that Classic REbirth loads itself;
- `xinput9_1_0.dll` passes every XInput call on to Windows and loads
  before Classic REbirth's CONFIGURATION window.

The Chinese mod carries no game data. The files `bio2 1.10.exe` expects
in the Sourcenext format are made from the discs' own files as they are
read. Corrected rooms are fixed in memory as they are read, and the
Supreme Skip files reach the game through a file redirect.

## Requirements

- The Chinese PC release of Resident Evil 2 (生化危机2): the retail
  Simplified discs, Leon, Claire or both installed into one folder. The fan
  pack 《生化危机2》简繁中文完美版 V1.6 also works.
- `bio2 1.10.exe`, the executable of Sourcenext's official 1.1.0 update,
  the only one Classic REbirth accepts. Classic REbirth's site offers it on
  its Resident Evil 2 page.
- 7-Zip, only for the optional setups: the Speedrun Edition, and preparing
  the Supreme Skip files again.

Classic REbirth (`ddraw.dll`, unmodified) comes with the release. The
Chinese text is read from the Leon disc's `REGIST\leon.exe`; with only the
Claire disc installed, play in English for now.

## Install

1. Put `bio2 1.10.exe` in the game folder (the one with `COMMON`, `REGIST`
   and `Pl0` or `PL1`).
2. Unzip `Zhongwen_Patch_v1.0.zip` and drag the contents of its folder into
   the game folder.
3. Open `bio2 1.10.exe`, press **OK** in CONFIGURATION and pick **生化危机2**
   in MOD SELECTION.

Nothing of your install is deleted or overwritten.

## Building

Needs llvm-mingw (i686), 7-Zip and Windows PowerShell.

    sh src/build.sh <path/to/i686-w64-mingw32-gcc>
    powershell -ExecutionPolicy Bypass -File Install-ZhongwenPatch.ps1
    powershell -ExecutionPolicy Bypass -File Create-Package.ps1 -Release

## What is included

This repository holds only the patch's own code, scripts and texts, under
GPL-3.0. Every release zip also carries the license as `LICENSE.txt`.

| | Release zips | Not included anywhere |
|---|---|---|
| Classic REbirth | `ddraw.dll`, unmodified, with its CC BY-NC-ND 4.0 license | |
| Door & Cutscene Skip | its files, already prepared, with credit | |
| Speedrun Edition | the setup only | Gemini's `mod_sr_crypto.7z` |
| The game | | game data, `bio2 1.10.exe` |

## Credits

- Classic REbirth and BIOHAZARD 2: SPEEDRUN EDITION: Gemini
  ([classicrebirth.com](https://classicrebirth.com)).
- Door & Cutscene Skip: Resevilnemesis30. descawed's update 1.1 listed the
  scenes that Zhongwen Patch fixes with its own code; the update is not
  used.
- Resident Evil 2 / Biohazard 2 / 生化危机2: Capcom. PC edition and its
  1.1.0 update: Sourcenext. Chinese editions: Capcom Asia, published by
  Shanghai Ubi Soft (mainland China) and The Third Wave (Taiwan).

## License

Zhongwen Patch is free software: its code, scripts, texts and documentation
are licensed under the [GNU General Public License v3.0](LICENSE)
(GPL-3.0-only). The license covers only Zhongwen Patch's own work: Classic
REbirth, the Door & Cutscene Skip files and the game keep their own terms,
listed in [NOTICE.txt](NOTICE.txt).
