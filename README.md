# Sokoban – Classic Puzzle Game

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Android](https://img.shields.io/badge/Android-5.0%2B-brightgreen.svg)](https://developer.android.com)
[![Privacy](https://img.shields.io/badge/Privacy-Policy-blue.svg)](PRIVACY.md)

[![Build](https://github.com/oneadzido/sokoban/actions/workflows/main.yml/badge.svg)](https://github.com/oneadzido/sokoban/actions/workflows/main.yml)

---

A classic Sokoban puzzle game for Android – push boxes onto targets in the fewest moves possible.

Developed by a self‑taught developer from Ghana as a passion project, using only his Android smartphone in deep partnership with AI.

---

## Features

- **90 levels** (standard Sokoban format, `.sbl`)
- **Simple touch & D‑pad controls**
- **Undo** – revert any move
- **Timer & move counter** – track your performance
- **Record stats** – best moves and time saved per level
- **Auto‑save** – progress is saved automatically
- **Reset level** or **reset entire game** with a single tap
- **Pause** – freeze the timer anytime
- **Rich visual feedback** – emojis for walls, targets, boxes, and player
- **FontAwesome icons** for buttons and controls
- **Completion overlay** – level completion message with blur effect
- **Progress tracking** – each completed level is tracked

---

## Technical Details

- **Minimum SDK**: Android 5.0 (API 21)
- **Target SDK**: Android 15 (API 35)
- **Build Tools**: AGP 8.1.0, Gradle 8.0, JDK 17
- **Architecture**: MVVM (ViewModel + LiveData)
- **Persistence**: SharedPreferences with Gson serialisation
- **Icons**: FontAwesome 6 (Free Solid) for buttons; emojis for game board

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