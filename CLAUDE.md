# Claude Project Guidelines

## Project Overview
This is a personal web projects repository by Genesis. Currently contains a browser-based Sudoku game (`sudoku.html`) — a single-file HTML/CSS/JS implementation with no build tools or dependencies.

## Git Workflow
- **Always commit and push changes to GitHub** after every modification.
- Remote: `https://github.com/Genchem/personal_projetcs`
- Branch: `master`
- Git user: Genesis <genesisgreat93@outlook.com>

## Project Structure
```
claude_project/
└── sudoku.html   # Self-contained Sudoku web game
```

## Sudoku Game — Key Details
- Single HTML file, no frameworks or dependencies
- Puzzle generation uses backtracking + uniqueness verification (`countSolutions`)
- Game state lives in the global `G` object
- `renderBoard()` rebuilds the DOM on every state change
- Dark mode preference is saved to `localStorage` under key `sudoku-dark`

### Difficulty (cells removed)
| Level  | Cells Removed |
|--------|--------------|
| Easy   | 36           |
| Medium | 46           |
| Hard   | 54           |

### Key Functions
| Function | Purpose |
|---|---|
| `generatePuzzle(diff)` | Builds solution + removes cells with uniqueness check |
| `startGame(diff)` | Resets all state and starts a new game |
| `renderBoard()` | Re-renders the 9×9 grid from current state |
| `inputNumber(n)` | Handles number entry (normal or notes mode) |
| `endGame(won)` | Handles win/lose, stops timer, shows overlay |
