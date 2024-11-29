# Game Maze #
This code is a maze game built with Pygame, a Python library designed for 2D game development. Below is a detailed explanation of the libraries used and the purpose of different parts of the code.

## 1. Libraries Used ##
### 1.1. Pygame ###
`import pygame`
Pygame is a library used for creating 2D games. It provides tools for rendering graphics, handling user input, and managing the game loop.

**Usage:**

_Graphics Rendering_: Drawing the maze, player, and exit (pygame.draw.rect, pygame.display.set_mode, etc.).
Event Handling: Capturing user inputs like keyboard events (pygame.event.get, pygame.KEYDOWN).
Text Rendering: Displaying score and messages on the screen (pygame.font.Font, screen.blit).
Screen Updates: Continuously updating visual elements (pygame.display.flip).
### 1.2. sys
`import sys`
Python's built-in library used for exiting the program.

Usage:

`sys.exit()`: Terminates the program when the user closes the game or when the game ends.
## 2. Code Components and Their Purposes
### 2.1. Maze Definition

`maze = [
    [1, 1, 1, ...],
    ...
]`
Purpose:
The maze is represented as a 2D list, where 1 denotes walls, and 0 denotes paths.
This structure defines the game's environment and is used to check valid player movements.
### 2.2. Settings and Colors
`cell_size = 60
wall_color = (0, 0, 0)
street_color = (255, 255, 255)
player_color = (0, 0, 255)
exit_color = (0, 255, 0)`
_Purpose_:
Sets the size of each maze cell and defines colors for walls, paths, the player, and the exit.
These settings control the game's visual design.
### 2.3. Drawing Functions
`draw_maze(screen)`: Draws the maze's walls and paths.
`draw_player(screen, player_x, player_y)`: Renders the player's current position on the screen.
`draw_exit(screen, exit_x, exit_y)`: Displays the exit point in the maze.
`draw_score(screen, score)`: Shows the player's current score at the top of the screen.
### 2.4. Movement Control Function
`def control_move(event, player_x, player_y, score):`
_Purpose_:
Handles keyboard inputs to move the player in the maze.
Checks if the movement is valid. If the player moves correctly, they earn points; otherwise, points are deducted.
### 2.5. Main Game Loop (main() Function)
`def main():`
_Purpose_:
Manages the game's main logic and controls the flow of gameplay.
Processes user inputs to move the player, updates the screen, and checks if the player reaches the exit.
Displays a congratulatory message when the player wins and prompts them to play again or quit.
## 3. Key Functions and Their Usage
`pygame.display.set_mode(...)`: Creates the game window.
`pygame.event.get()`: Captures keyboard and mouse events.
`pygame.draw.rect(...)`: Draws graphical elements like walls, the player, and the exit.
`pygame.font.Font(...) and screen.blit(...)`: Manages text rendering and displays text (e.g., score and messages) on the screen.
`pygame.display.flip()`: Updates the screen to reflect changes.
`pygame.time.wait(2000)`: Pauses the game briefly after the player wins.
**Game Workflow**
The game begins with the player starting at a defined position in the maze.
The player uses arrow keys to navigate through the maze while earning or losing points based on their movements.
Upon reaching the exit, a congratulatory message is displayed, and the game asks if the player wants to replay.
If the player chooses "Yes," the maze resets; otherwise, the game exits.
This code provides a simple but interactive maze game with a scoring system and replay functionality, offering a fun and engaging experience.
