---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: false
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/connect-four
has-questions: false
---

> [!note]
> Done with class design itself. Implementation is straightforward and so, I did not proceed to complete it. I am already familiar with another problem -> Tic Tac Toe.

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
enum GameState {
	IN_PROGRESS,
	TIE,
	HAS_WINNER,
}

enum DiscColor {
	RED,
	YELLOW,
}

class Game {
	private Board board;
	private Player player1;
	private Player player2;
	private Player currentPlayer;
	private GameState gameState;
	private Player winner;
	
	public Game(Player player1, Player player2) {
		this.player1 = player1;
		this.player2 = player2;
	}
	
	public void makeMove(int col)
	private void updatePlayer()
	public Player getPlayer1()
	public Player getPlayer2()
	public GameState getGameState()
	public Player getWinner()
}

class Board {
	// pieces
	private int ROWS = 6;
	private int COLS = 7;
	private String[][] = new String[ROWS][COLS]
	
	public Board() {}
	public boolean canPlace(int col)
	public void addDisc()
	public boolean checkWinner()
	public boolean isFull()
}

class Player {
	private String name;
	private DiscColor discColor;
	
	public Player(String name, DiscColor discColor) {
		this.name = name;
		this.discColor = discColor;
	}
	
	public String getName() { return this.name }
	public DiscColor getDiscColor() { return this.discColor }
}
```

# Implementation
```java
enum GameState {
	IN_PROGRESS,
	TIE,
	HAS_WINNER,
}

enum DiscColor {
	RED,
	YELLOW,
}

class Game {
	private Board board;
	private Player player1;
	private Player player2;
	private Player currentPlayer;
	private GameState gameState;
	private Player winner;
	
	public Game(Player player1, Player player2) {
		this.player1 = player1;
		this.player2 = player2;
	}
	
	public void makeMove(int col) {
		DiscColor currDiscColor = currentPlayer.getDiscColor();
		
		/*
			get current player
			check if can be added to col
			if can be added to col, add
			calculate if there is winner
			calculate if there is tie
		*/
		if (board.canPlace(col) && addDisc(col, currDiscColor)) {
		}
	}
	private void updatePlayer()
	public Player getPlayer1()
	public Player getPlayer2()
	public GameState getGameState()
	public Player getWinner()
}

class Board {
	private int ROWS = 6;
	private int COLS = 7;
	private String[][] = new String[ROWS][COLS]
	
	public Board() {}
	public boolean canPlace(int col)
	public void addDisc()
	public boolean checkWinner()
	public boolean isFull()
}

class Player {
	private String name;
	private DiscColor discColor;
	
	public Player(String name, DiscColor discColor) {
		this.name = name;
		this.discColor = discColor;
	}
	
	public String getName() { return this.name }
	public DiscColor getDiscColor() { return this.discColor }
}
```

# Extensibility

