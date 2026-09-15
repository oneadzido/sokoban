# Sokoban v1.0.1

**Release Date:** September 15, 2026

---

## What's New

This is a maintenance release. Gameplay, controls, theming, and persistence are unchanged from v1.0.0. The update is entirely about how the 90 levels ship inside the APK, plus an in-app attribution for the classic level collection.

---

## Changes

### Level Loading

- **Levels now ship as individual files.** Each of the 90 levels is stored as its own `.sbl` file in `app/src/main/assets/levels/`, named `level.01.sbl` through `level.90.sbl`, replacing the single combined `original.sbl` file used in v1.0.0.
- **Same levels, same order.** The 90 files are the classic XSokoban levels (`screen.1` through `screen.90`), renamed only. No level content was altered. Every level plays exactly as it did in v1.0.0.
- **Why the change.** The new layout mirrors the XSokoban source layout, makes each level easy to inspect in a text editor, and makes adding, removing, or replacing a single level a one-file operation.

### About Sheet

- **XSokoban attribution added.** The About sheet's Libraries section now includes an **XSokoban** entry alongside Google Gson and FontAwesome. Tapping it crossfades the license viewer to a short attribution that credits the XSokoban collection, Thinking Rabbit Inc. as the designers of the original 50 levels, and the community contributors of the XSokoban Extra set. Nothing about the existing entries changed.

### Under the Hood

- `LevelRepository` gained a `loadSingleLevel(AssetManager, String)` method that parses one level from one asset file.
- `GameViewModel.loadLevels(String)` was replaced by `GameViewModel.loadLevels(int)`, which loads all 90 files in order at startup.
- `MainActivity.onCreate` now calls `viewModel.loadLevels(90)`.
- The About sheet's license viewer gained one new clickable entry, wired through the same listener pattern as the existing ones.

---

## Not Changed

- Gameplay, movement, undo, replay, and win detection
- Timer and overlay behaviour
- Save/restore and best stats
- Light and dark themes, and the three-state theme button
- The Rules sheet
- All layouts, drawables, and icons other than the About sheet's new entry
- Permissions — the app still requests none

---

## Upgrade Notes

No action is required. Updating from v1.0.0 replaces the APK in place; saved progress, best stats, and theme preference are preserved.

---

## System Requirements

- **Minimum SDK:** Android 5.0 (API 21)
- **Target SDK:** Android 15 (API 35)
- **Architecture:** Universal APK (no native libraries)

---

## Download

Download the APK from the **Assets** section of this release.

---

## Installation

1. Download the APK file
2. Enable **Install from unknown sources** in your device settings if prompted
3. Open the APK file and tap **Install**

---

## Credits

- **XSokoban** by Joseph L. Traub — the classic Unix Sokoban implementation and the 90-level collection
- **Thinking Rabbit Inc.** — creators of Sokoban (1982) and designers of the original 50 levels
- **Google Gson** — JSON serialisation of game state
- **FontAwesome** by Fonticons, Inc. — the icon font used in buttons and controls

---

## License

Licensed under the MIT License.

Copyright (c) 2026 Richard Korbla Adzido

---

**Made with love in Ghana.**