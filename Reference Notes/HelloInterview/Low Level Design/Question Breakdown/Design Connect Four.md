---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/connect-four
has-questions: false
---

# Problem
Build the object-oriented design for a two-player Connect Four game. Players take turns dropping discs into a 7-column, 6-row board. The first to align four of their own discs vertically, horizontally, or diagonally wins.

# Requirements
- 2 players
- connect 4 to win
- board -> 7-column, 6-row
- Align horizontally, vertically or diagonally
- Tie
- Alternative turns

# Entities and Relationships
Player
Board
Piece
Game

Game -> 2 players, 1 board
Board -> 7 col x 6 rows -> 42 pieces

# Class Design

```java
class Game {
	private Board board;
	private Player player;
	private int turn = 0;
	private Player winner;
	
	public void makeMove(int col)
	private void updatePlayer()
	private void calculateWinner()
}

class Board {
	// pieces
	// update board state
	public void addPiece()
	// get board state
}

class Player {
	private String name;
	
	public Player(String name) {
		this.name = name;
	}
	
	public String getName() { return this.name }
}

class Piece {

}
```

# Implementation

# Extensibility

