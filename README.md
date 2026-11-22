# Python Maze Game | Pygame

A single-player, randomly generated maze game developed in **Python** with **Pygame**. The player navigates toward an exit, collects stars, and avoids holes and a moving monster. The project explores **maze generation, graph traversal, collision detection, and real-time game logic**.

## Features

- **Procedural maze generation:** Uses randomized depth-first search (DFS) to build a new maze on each run.
- **Path validation:** Uses breadth-first search (BFS) to verify that the exit remains reachable after hazards are placed.
- **Start and finish selection:** Uses BFS-based distance calculations to place the start and exit far apart.
- **Interactive gameplay:** Control the player with the arrow keys while avoiding six holes and a moving monster.
- **Collectibles and scoring:** Collect up to five stars; the final score reflects collected stars, collisions, and completion time.
- **Game visualization:** Renders the maze, player, hazards, collectibles, and final results using Pygame.

## Tech Stack

- **Language:** Python 3
- **Library:** Pygame
- **Algorithms:** Randomized DFS, BFS, heuristic monster movement
- **Development environment:** PyCharm (or any Python IDE)

## Getting Started

1. Install Python 3 and clone or download this repository.
2. Install the required dependency:

   ```bash
   pip install -r requirements.txt
   ```

   Alternatively, run `pip install pygame`.

3. Launch the game:

   ```bash
   python 26_SS_B02_Simulation_V9.py
   ```

   You can also open the Python file in PyCharm and click **Run**.

## How to Play

- Use the **arrow keys** to move through open maze cells.
- **Blue square:** player
- **Yellow triangle:** start
- **Green triangle:** exit
- **Gold stars:** collectibles
- **Black circles:** holes that reset the player to the start
- **Red moving circle:** monster that chases the player using simple movement heuristics and resets the player on contact
- Reach the green exit to finish the game and see your results.

## Scoring

The end screen reports stars collected, elapsed time, monster collisions, hole collisions, and the final score.

```text
Score = (stars collected × 1000)
      − (monster hits × 50)
      − (hole hits × 30)
      − (elapsed seconds × 2)
```

Collecting every star is optional; reaching the exit ends the game.

## Implementation Highlights

**Maze generation:** A randomized DFS carves pathways through a wall grid. A small number of additional walls are opened to reduce dead ends.

**Solvability:** BFS computes reachable cells and checks that hazard placement does not eliminate every route from start to finish. Two BFS passes select approximately distant starting and ending positions.

**Enemy movement:** The monster prefers movement directions toward the player, with fallback directions if needed. This is a simple movement heuristic, **not** a shortest-path AI model.

**Game loop:** Pygame handles keyboard input, rendering, collision events, and a frame-limited update loop.

## Project Files

```text
pygame-maze-game/
├── 26_SS_B02_Simulation_V9.py   # Main game code
├── requirements.txt             # Python dependency
└── README.md                    # Project documentation
```

## Screenshots

A gameplay screenshot can be added here to demonstrate the maze and interface.

## Project Context

Developed as a Python game simulation/case-study project. This repository contains the **standalone Pygame simulation**, not the separate two-Raspberry-Pi WLAN multiplayer implementation.
