# Class Specifications

## 1. Game Loop
- **Purpose**: Manages the flow of the game, including turns, win conditions, and coordination between components.
- **Attributes**:
  - `is_running`: Boolean indicating if the game is active.
  - `current_turn`: Tracks whose turn it is (white/black).
- **Methods**:
  - `start()`: Initializes the game and starts the loop.
  - `process_turn()`: Handles the logic for a single turn.
  - `end_game()`: Ends the game and performs cleanup.
- **Interactions**:
  - Coordinates with the `Board`, `Renderer`, `Event Handler`, `Validator`, and `Menu`.

## 2. Board
- **Purpose**: Represents the chessboard and manages the state of the game.
- **Attributes**:
  - `tiles`: A 2D array of `Tile` objects representing the board.
  - `pieces`: A list of all active `Piece` objects.
- **Methods**:
  - `initialize_board()`: Sets up the board with pieces in their starting positions.
  - `move_piece(start, end)`: Moves a piece from one tile to another.
  - `remove_piece(piece)`: Removes a piece from the board and updates the tile it occupies.
  - `get_piece_at(tile)`: Returns the piece at a given tile.
- **Interactions**:
  - Communicates with the `Validator` to check move legality.
  - Provides state information to the `Renderer` for drawing.

## 3. Tile
- **Purpose**: Represents a single square on the board.
- **Attributes**:
  - `color`: The color of the tile (e.g., light or dark).
  - `coordinates`: The position of the tile on the board.
  - `piece`: The piece currently occupying the tile (if any).
- **Methods**:
  - `is_occupied()`: Returns whether the tile is occupied by a piece.

## 4. Piece
- **Purpose**: Represents a chess piece.
- **Attributes**:
  - `type`: The type of the piece (e.g., pawn, rook).
  - `owner`: The owner of the piece (white/black).
- **Methods**:
  - `get_valid_moves(board)`: Returns a list of valid moves for the piece.

## 5. Move Validator
- **Purpose**: Checks if a move is legal based on the rules of chess.
- **Attributes**:
  - None (stateless).
- **Methods**:
  - `is_move_legal(board, start, end)`: Returns whether a move is legal.

## 6. Mover
- **Purpose**: Executes moves and updates the board state.
- **Attributes**:
  - None (stateless).
- **Methods**:
  - `execute_move(board, start, end)`: Moves a piece and handles captures.

## 7. Renderer
- **Purpose**: Draws the board, pieces, and UI elements.
- **Attributes**:
  - `screen`: The Pygame screen object.
- **Methods**:
  - `draw_board(board)`: Draws the board and pieces.
  - `update_display()`: Updates the screen.

## 8. Event Handler
- **Purpose**: Processes user input.
- **Attributes**:
  - None (stateless).
- **Methods**:
  - `process_input()`: Handles user input (e.g., mouse clicks).

## 9. Menu
- **Purpose**: Provides options for pre-game setup.
- **Attributes**:
  - `options`: Stores menu options (e.g., player settings, AI level).
- **Methods**:
  - `display_menu()`: Displays the menu.
  - `get_selection()`: Returns the user’s menu selection.