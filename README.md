# Grab Fix

A ReSkate build that fixes the grab bugs skate. picked up after Season 2.

| Bug | What happens | Status |
|---|---|---|
| **Sticky Grab** | A/X modified grabs (benihana, dog piss, judo nose, one foot tail) don't register the release, so the skater holds the grab until landing. | Fixed: Grab Fix keeps the game's own `DingoGameplay.UseLegacyFootPlants` setting on. |
| **Grab Swap** | Tweak the board to nose or tail, press a trigger, get a frontside/backside grab instead. | Not fixed yet. The legacy footplants make it rarer. The grab probe records it so it can be found. |

## Install

1. Download the zip from the latest run (Actions) or release.
2. Close the game. Replace `ReSkate.dll` and `ReSkateLauncher.exe` in your ReSkate folder (next to `Skate.exe`) with the two in the zip.
3. Start ReSkate as usual.

## Use

- Menu: **Insert → Addons → GRAB FIX**. One toggle, **Grab Fix** (on by default), and **Grab probe** under it.
- Console (`~`): `grabfix status`, `grabfix on|off`, `grabfix probe on|off`.
- Settings are kept in `%LOCALAPPDATA%\ReSkate\grabfix\settings.txt`.

## Grab probe

While it's on, every air is written to `logs\grab-probe-<date>-<time>.csv` next to `ReSkate.log` (one file per launch). Each air also gets one line in `ReSkate.log`. Send both after a test.

## Build

Actions → **Build Grab Fix** → Run workflow. It builds on ReSkate `v2.1.1` (the tag can be changed), applies the patch embedded in the workflow, and uploads `ReSkate_GrabFix-<version>-ReSkate<version>` with just the two files. Tick **release** to also publish a GitHub release.

`grab-fix.patch` is the same patch as a plain file, for reading or for applying to a ReSkate source tree by hand (`git apply --ignore-whitespace grab-fix.patch`).
