# Project Specification

## Purpose
This project aims to create a fully functional chess game using Python and Pygame. The focus is on learning code architecture, modular design, and best practices for organizing and structuring a program. The game will include features such as:
- A graphical interface for playing chess.
- Support for two players (local play).
- Optional AI for single-player mode (future extension).
- Customization options (e.g., board and piece skins).

## Main Components

### 1. Game Loop
- Manages the flow of the game.
- Handles turns, win conditions, and overall coordination between components.

### 2. Board
- Represents the chessboard and its state.
- Stores tiles and pieces.
- Provides methods for querying and updating the board.

### 3. Tile
- Represents a single square on the board.
- Stores properties like color, coordinates, and the piece occupying it.

### 4. Piece
- Represents a chess piece (e.g., pawn, rook).
- Stores type, owner, and other relevant attributes.

### 5. Move Validator
- Checks if a move is legal based on the rules of chess.
- Ensures moves do not violate game rules (e.g., king safety).

### 6. Mover
- Executes moves and updates the board state.
- Handles captures and special moves (e.g., castling, en passant).

### 7. Renderer
- Draws the board, pieces, and UI elements.
- Updates the display based on the current game state.

### 8. Event Handler
- Processes user input (e.g., mouse clicks).
- Translates input into actions (e.g., selecting and moving pieces).

### 9. Menu
- Provides options for pre-game setup (e.g., player settings, AI level).
- Allows customization of board and piece skins.

### 10. Main Function
- **Purpose**: Acts as the entry point for the program.
- **Responsibilities**:
  - Creates the game window.
  - Displays the menu and processes user choices.
  - Initializes the board and other game elements based on menu selections.
  - Starts the game loop.
  - Handles quitting the game and cleanup.

## Assets
All textures (e.g., board and piece skins) and sounds (e.g., move sounds) will be stored in a dedicated `assets` folder. This ensures that resources are organized and easily accessible.

## Interactions
- **Game Loop**: Orchestrates the game, coordinating between components.
- **Board**: Stores the state of the game and interacts with the `Validator` and `Mover`.
- **Renderer**: Queries the `Board` for the current state and draws it.
- **Event Handler**: Sends user actions to the `Game Loop`.

## Future Extensions
- **AI**: Add support for playing against an AI opponent.
- **Online Multiplayer**: Enable remote play over the internet.
- **Advanced Customization**: Add more skins and themes for the board and pieces.