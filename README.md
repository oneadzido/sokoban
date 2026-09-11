# Sokoban – Classic Puzzle Game

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Android](https://img.shields.io/badge/Android-5.0%2B-brightgreen.svg)](https://developer.android.com)
[![Privacy](https://img.shields.io/badge/Privacy-Policy-blue.svg)](PRIVACY.md)

[![Build](https://github.com/oneadzido/sokoban/actions/workflows/main.yml/badge.svg)](https://github.com/oneadzido/sokoban/actions/workflows/main.yml)

---

A classic Sokoban puzzle game for Android — push boxes onto targets in the fewest moves possible.

Developed by a self-motivated, self-learning developer from Ghana who has been passionate about computers since childhood. Built entirely on an Android smartphone, in deep partnership with AI. Not a developer by training — a developer by passion.

---

## Features

### Gameplay

- **90 levels** in the standard Sokoban `.sbl` format
- **Movement** — an on-screen D-pad (up, down, left, right) and keyboard support (arrow keys and WASD)
- **Undo** — revert the last move at any time; the button is disabled when there is no move to undo
- **Move counter** — every move that changes the board is counted
- **Timer** — runs whenever the board is visible and the level is not solved; the timer and the overlay state are two views of the same thing
- **Best stats** — best moves and best time saved independently for each level
- **Auto-save** — progress persists across app restarts
- **Pause** — hides the board behind the Paused overlay and stops the timer
- **Reset Level** — restarts the current puzzle; best stats are kept
- **Reset Game** — clears all progress and best stats, and returns to Level 1

### Action Row

Five controls sit in a single row above the D-pad:

- **Reset Game** — clears all progress and best stats, and returns to Level 1
- **Previous** — moves to the previous level, with a confirmation if the current level is in progress
- **Pause** — toggles between pausing and resuming; the button shows the Resume glyph while an overlay can be dismissed
- **Next** — moves to the next level, with the same confirmation rule
- **Reset Level** — restarts the current puzzle; best stats are kept

The Previous and Next buttons are disabled only while the game is paused, so a freshly loaded or solved level can still be navigated away from.

### Overlay System

The board is either fully visible and playable, or covered by an overlay that hides it. The overlay exists in three states, and dismissing any of them returns the board to play:

- **Level Loaded** — a freshly loaded level shows its number (`LEVEL 1`, `LEVEL 47`, and so on) until you dismiss the overlay. Dismissing it is the act that starts the level, so the clock runs from the moment the board becomes visible.
- **Level Paused** — the board is hidden behind `LEVEL PAUSED` and the timer stops. Tapping Resume returns the board to play and restarts the clock.
- **Level Solved** — the board stays sharp for half a second so the final move is visible, then blurs behind `LEVEL SOLVED!`. After two seconds, the next level loads automatically.

### Restore Model

On app restart, the saved state is classified by its content, and the app continues from where you were headed:

- **Solved board** — the app was killed between solving a level and the auto-advance firing. The next level is loaded fresh, exactly as the auto-advance would have done.
- **No moves, board not solved** — you had opened a level but had not started playing. The level is loaded fresh with the Level Loaded overlay.
- **Some moves, board not solved** — a game was genuinely in progress. The board is restored and shown with the Level Paused overlay so you resume deliberately.

### Visuals & Theming

- **Emoji board** — walls, targets, boxes, and player rendered as emojis, with no board background painted
- **FontAwesome icons** for the D-pad, the action row, and the dialog header buttons
- **Player pop animation** — a small scale bounce each time the player moves
- **Solved overlay blur** — the board is blurred behind the solved label so the arrangement cannot be studied after the level is complete
- **Light and dark themes** — the app follows the system's light/dark setting by default
- **Three-state theme button** — cycles through System (microchip), Light (sun), and Dark (moon) with a single tap; the chosen mode is stored and applied on the next launch
- **Edge-to-edge design** — the card, the sheets, and the system bars share one continuous surface; bar icon colours follow the active mode
- **Full-screen sheets** — the About and Rules dialogs fill the screen and draw behind the bars, just like the main activity

### Other

- **Accessibility** — every button has a content description; enabled buttons carry a tooltip where the platform supports it
- **No permissions** — the game runs entirely offline
- **No data collection** — nothing leaves the device

---

## Technical Details

- **Minimum SDK**: Android 5.0 (API 21)
- **Target SDK**: Android 15 (API 35)
- **Build Tools**: AGP 8.1.0, Gradle 8.0, JDK 17
- **Architecture**: MVVM with `GameViewModel` and `LiveData`
- **Persistence**: `SharedPreferences` with Gson serialisation
- **Undo**: delta-based — only the direction of each move is stored, and the board is reconstructed by replaying moves from the base state
- **Icons**: FontAwesome 6 (Free Solid) for buttons; emojis for the game board
- **Theme**: DayNight with a runtime three-state switch (`SYSTEM`, `LIGHT`, `DARK`) managed by `ThemeManager`

---

## Download

Get the latest APK from:
- [GitHub Releases](https://github.com/oneadzido/sokoban/releases)
- GitHub Actions artifacts (see the `Build` badge above)

---

## Build from Source

### Prerequisites

- Android Studio Hedgehog or later
- JDK 17
- Android SDK API 35

### Build Commands

```bash
git clone https://github.com/oneadzido/sokoban.git
cd sokoban

./gradlew assembleDebug     # Debug build
./gradlew assembleRelease   # Release build
./gradlew clean             # Clean build