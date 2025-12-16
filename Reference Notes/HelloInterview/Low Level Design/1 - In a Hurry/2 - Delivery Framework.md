---
tags:
  - reference-notes
  - low-level-design
source_url: https://www.hellointerview.com/learn/low-level-design/in-a-hurry/delivery
---

# Requirements
- Requirements gathering and determining of scope and constraints
# Entities and Relationships
- Based on requirements, identify key entities
# Class Design
- Identify classes based on entities
- Identify fields and methods
	- state needed -> fields
	- behaviors needed -> methods
- If an entity needs to manage its own state -> class
	- otherwise, field in a class

## UML Diagrams
- UML Diagrams are an outdated practice
- It is sufficient to write in classes instead as it is modern and swifter to write
- Use any notation that can clearly communicate your intent
```
class Game:
  - board: Board
  - playerX: Player
  - playerO: Player
  - currentPlayer: Player
  - state: GameState (IN_PROGRESS, WON, DRAW)
  - winner: Player? (null if no winner)

  + makeMove(player, row, col) -> bool
  + getCurrentPlayer() -> Player
  + getGameState() -> GameState
  + getWinner() -> Player?
  + getBoard() -> Board
```
# Implementation
- Define method implementations in classes
# Extensibility and maintainability
- Extensibility of created classes
- Will showcase flexibility of design