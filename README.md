# Dungo's Minesweeper

A modern, polished recreation of the classic logic puzzle, built in Python using the Pygame-CE library. This project features a strictly decoupled architecture, a dynamic animated background, persistent local high score tracking, and real-time algorithmic audio synthesis.

## Key Features

* Classic & Custom Modes: Play standard Beginner (9x9), Intermediate (16x16), and Expert (30x16) difficulties, or define your own grid size and mine count.
* Advanced Mechanics: Includes traditional Chording (middle-click to reveal neighbors) and a limited Hint system that algorithmically guarantees a safe tile without playing the game for you.
* Algorithmic Audio Synthesizer: Real-time audio feedback generated mathematically using Numpy, rendering custom wave frequencies for clicks, reveals, flags, and explosions without relying on external audio files.
* Persistent Leaderboards: Automatically tracks completion times and calculates 3BV (Bechtel's Board Benchmark Value) efficiency, saving the top 10 scores per difficulty locally in a JSON file.
* Modern UI & Rendering: Features a custom deep purple and lavender theme, tactile button drop-shadows, an animated floating-tile background, and a fixed 1080x720 rendering resolution.

## Installation & Setup

### Option 1: Play the Standalone Build (Windows)
1. Download the latest release .zip from the Releases tab.
2. Extract the entire folder to your local drive.
3. Run the executable to launch the game.

### Option 2: Run from Source
If you want to run the engine from the source code:
1. Clone this repository:
   git clone https://github.com/YOUR_USERNAME/Dungos-Minesweeper.git
2. Install the required dependencies:
   pip install pygame-ce numpy
3. Run the engine:
   python main.py

## How to Play
1. Launch the game.
2. Select a difficulty level (Beginner, Intermediate, Expert) or configure your own grid via the Custom Setup menu.
3. Left-click to reveal tiles, right-click to flag them, and middle-click revealed numbers to chord adjacent tiles.
4. Use the Hint button if you get stuck.

## Architecture
This project follows a decoupled architectural standard, enforcing strict separation across the codebase:
* Engine & Loop: Managed by src/core/game_engine.py, separating delta-time calculations and OS-level window management from game logic.
* Game State: Managed centrally, with board and cell logic isolated from rendering (src/core/board_manager.py).
* UI Encapsulation: Self-contained components that manage their own hover states and event polling (src/interface/ui_components.py).
* Safe File Handling: Dynamic path resolution ensures assets load flawlessly regardless of whether the application is running from source or as a compiled executable (src/utilities/constants.py).

## Built With
* Python 3
* Pygame-CE (Community Edition)
* Numpy
