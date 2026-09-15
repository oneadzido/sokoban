# Changelog

All notable changes to Sokoban are documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.1] — 2026-09-15

### Changed

- Levels now ship as 90 individual `.sbl` files under `assets/levels/` instead of a single combined `original.sbl`. No level content was altered.
- `LevelRepository` gained `loadSingleLevel(AssetManager, String)`.
- `GameViewModel.loadLevels(String)` was replaced by `GameViewModel.loadLevels(int)`.
- `MainActivity.onCreate` now calls `viewModel.loadLevels(90)`.

### Added

- **XSokoban** attribution in the About sheet's Libraries section, crediting the level collection, Thinking Rabbit Inc., and the XSokoban Extra contributors.
- `license_xsokoban` and `about_library_xsokoban` string resources.
- `textViewAboutXsokoban` entry in `dialog_about.xml`.

---

## [1.0.0] — 2026-09-11

### Added

- Initial public release.
- 90 levels in the standard Sokoban `.sbl` format.
- On-screen D-pad and keyboard support (arrow keys and WASD).
- Undo, move counter, timer, best stats per level, and auto-save.
- Pause, Reset Level, Reset Game, and level navigation.
- Overlay system with three states: Level Loaded, Level Paused, Level Solved.
- Emoji board with FontAwesome control icons.
- Light and dark themes with a three-state theme button.
- About and Rules sheets, both full-screen and edge-to-edge.
- No permissions, no data collection.