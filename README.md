# Asteroids

A simple Asteroids clone written in Python with [pygame](https://www.pygame.org/). Pilot a triangular ship, drift through space, and shoot asteroids that split into smaller pieces when hit.

Built as a learning project to practice OOP, inheritance, and the pygame sprite system.

## Requirements

- Python 3.13+
- [uv](https://docs.astral.sh/uv/) (recommended) or `pip`

## Setup

Using `uv` (recommended — uses the pinned versions in `uv.lock`):

```bash
uv sync
```

Or using `pip`:

```bash
python -m venv .venv
source .venv/bin/activate
pip install pygame==2.6.1
```

## Run

```bash
uv run main.py
```

Or, with an activated venv:

```bash
python main.py
```

## Controls

| Key     | Action          |
| ------- | --------------- |
| `W`     | Move forward    |
| `S`     | Move backward   |
| `A`     | Rotate left     |
| `D`     | Rotate right    |
| `Space` | Shoot           |

Colliding with an asteroid ends the game.

## Project structure

| File              | Purpose                                                        |
| ----------------- | -------------------------------------------------------------- |
| `main.py`         | Entry point — game loop, sprite groups, collision handling.    |
| `constants.py`    | Tunable values (screen size, speeds, radii, cooldowns).        |
| `circleshape.py`  | `CircleShape` base class — wraps `pygame.sprite.Sprite` with position, velocity, radius, and circle-based collision. |
| `player.py`       | `Player` — input handling, movement, rotation, shooting cooldown. |
| `shot.py`         | `Shot` — bullets fired by the player.                          |
| `asteroid.py`     | `Asteroid` — asteroid behavior, including splitting on hit.    |
| `asteroidfield.py`| `AsteroidField` — spawns asteroids at the screen edges.        |
| `logger.py`       | Optional debug logger that writes per-second game state and events to `game_state.jsonl` / `game_events.jsonl`. |

## Tuning

All gameplay values (player speed, turn speed, shoot cooldown, asteroid spawn rate, etc.) live in `constants.py` and can be tweaked freely without touching the rest of the code.
