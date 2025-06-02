# Asteroids

A modern recreation of the classic **Asteroids** arcade game, built in Python using Pygame. Pilot your spaceship through a field of drifting asteroids, destroy them with your blaster, and avoid collisions to survive as long as possible.

## Features

- **Player ship** with smooth rotation and thrust (forward/backward)
- **Asteroid spawning** at random screen edges, drifting in random directions
- **Collision detection**: when an asteroid collides with the player, the game ends.
- **Easy-to-read codebase** with modular classes.

## Prerequisites

- **Python 3.7+**
- **Pygame 2.6.1**

## Installation

1. **Clone** this repository:

  ```bash
  git clone https://github.com/rod-ml/asteroids
  ```

2.**Install** the required dependencies:

  ```bash
  pip install -r requirements.txt
  ```

## Running the game

From within the asteroids folder, simply run:

```bash
python main.py
```

This will open a 1280x720 window where you can start playing right away.

## Controls

- **W** -- Thrust forward
- **S** -- Thrust backward
- **A** -- Rotate left
- **D** -- Rotate right
- **SPACE** -- Shoot a projectile

Try to shoot all asteroids before they hit your ship. When a large asteroid is hit, it splits into smaller ones. Keep clearing the asteroids out to rack up more "survival time."

## Project Structure

```
asteroids/
├── main.py            # Entry point for the game loop
├── player.py          # Player ship logic (movement, rotation, shooting)
├── asteroid.py        # Single asteroid behavior (drawing, splitting)
├── asteroidfield.py   # Manages spawning and updating multiple asteroids
├── shot.py            # Projectile logic (movement and collision)
├── circleshape.py     # Base class for any circular object (position, velocity, collision)
├── constants.py       # All game constants (screen size, speeds, radii, spawn rate, etc.)
├── requirements.txt   # Lists `pygame==2.6.1`
├── LICENSE            # MIT License (© 2025 Rodrigo M.L.)
├── .gitignore         # Standard Python/IDE ignores
└── venv/              # (Optional) Virtual environment containing pygameu
```

- **main.py** initializes Pygame, sets up the screen, clock, and sprite groups; it then creates a Player and an AsteroidField, and enters the main loop (checking for input, updating sprites, handling collisions, and drawing).
- **player.py** defines the Player class (inherits from CircleShape), reads keyboard input (W, A, S, D, SPACE), and handles thrust, rotation, and shooting cooldown.
- **asteroidfield.py** periodically spawns new Asteroid instances at random edges; each asteroid drifts inward with a randomized velocity.
- **asteroid.py** defines how an Asteroid is drawn and implements splitting into smaller pieces when hit.
- **shot.py** defines the Shot class (also inherits from CircleShape), moves projectiles forward, and checks for collisions with asteroids.
- **circleshape.py** is a small helper base class for any circular game object (holds position, velocity, radius, collision check).
- **constants.py** holds all tunable values—screen dimensions, speeds, radii, spawn rate, etc.
- **requirements.txt** ensures anyone can install the exact Pygame version:
