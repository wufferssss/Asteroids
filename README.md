# Asteroids

A 2D arcade game built in Python using [Pygame](https://www.pygame.org/). Pilot your ship through an asteroid field, blast incoming space rocks into smaller fragments, and survive as long as you can!

---

## 🎮 Game Controls

| Key | Action |
| :--- | :--- |
| <kbd>W</kbd> | Move forward (thrust) |
| <kbd>S</kbd> | Move backward (reverse) |
| <kbd>A</kbd> | Rotate ship left (counter-clockwise) |
| <kbd>D</kbd> | Rotate ship right (clockwise) |
| <kbd>Space</kbd> | Shoot blasters |
| **Window Close (✕)** | Exit game |

---

## 🚀 Getting Started

### Prerequisites

- **Python**: Version `3.13` or newer
- Recommended: [uv](https://docs.astral.sh/uv/) (fast Python package manager) or standard `pip`

---

### Option 1: Using `uv` (Recommended)

If you have `uv` installed, setting up and running is instant:

1. **Clone or navigate to the repository:**
   ```bash
   cd Asteroids
   ```

2. **Sync dependencies and environment:**
   ```bash
   uv sync
   ```

3. **Start the game:**
   ```bash
   uv run python main.py
   ```

---

### Option 2: Using standard `pip` & `venv`

1. **Clone or navigate to the repository:**
   ```bash
   cd Asteroids
   ```

2. **Create and activate a virtual environment:**
   - **Windows (PowerShell):**
     ```powershell
     python -m venv .venv
     .venv\Scripts\Activate.ps1
     ```
   - **Windows (Command Prompt):**
     ```cmd
     python -m venv .venv
     .venv\Scripts\activate.bat
     ```
   - **macOS / Linux:**
     ```bash
     python3 -m venv .venv
     source .venv/bin/activate
     ```

3. **Install dependencies:**
   ```bash
   pip install pygame==2.6.1
   ```
   *(Alternatively: `pip install -e .`)*

4. **Launch the game:**
   ```bash
   python main.py
   ```

---

## 🕹️ Gameplay Rules & Mechanics

- **Splitting Asteroids**: When an asteroid is hit by a laser, it splits into two smaller, faster pieces until it reaches minimum size and is destroyed.
- **Weapon Cooldown**: Lasers fire rapidly with a short built-in cooldown (0.3s) between shots.
- **Collisions & Game Over**: A single collision with any asteroid will end the game immediately.

---

## ⚙️ Customization & Constants

You can tweak gameplay parameters in [`constants.py`](constants.py):

- **Window Resolution**: `SCREEN_WIDTH` (1280), `SCREEN_HEIGHT` (720)
- **Ship Movement**: `PLAYER_SPEED` (200), `PLAYER_TURN_SPEED` (300)
- **Combat**: `PLAYER_SHOOT_SPEED` (500), `PLAYER_SHOOT_COOLDOWN_SECONDS` (0.3)
- **Asteroid Settings**: `ASTEROID_SPAWN_RATE_SECONDS` (0.8), `ASTEROID_KINDS` (3), `ASTEROID_MIN_RADIUS` (20)

---

## 📁 Project Architecture

- [`main.py`](main.py): Entry point, Pygame display initialization, event loop, and collision handling.
- [`player.py`](player.py): Player ship representation, rotation, movement vectors, and shooting logic.
- [`asteroid.py`](asteroid.py): Asteroid physics, rendering, and recursive splitting behavior upon destruction.
- [`asteroidfield.py`](asteroidfield.py): Spawner responsible for generating asteroids around screen boundaries.
- [`shot.py`](shot.py): Projectile class for player blaster shots.
- [`circleshape.py`](circleshape.py): Base class implementing circle-based 2D collision detection and geometry.
- [`constants.py`](constants.py): Centralized game variables and configuration.
- [`logger.py`](logger.py): Telemetry recorder logging game state and game events to JSONL files.
