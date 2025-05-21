# Tetris Game

[English](README.EN.md) | [简体中文](README.md)

A Tetris game implemented with pure HTML, CSS and JavaScript.

## Game Overview
Tetris is a classic puzzle game. This implementation is built with pure HTML, CSS and JavaScript, without any external frameworks or libraries. The game retains the core gameplay of classic Tetris while adding modern interface design and enhanced features.

## Game Features

- 🎮 **Classic Gameplay**: Contains 7 different shapes of blocks, which can be rotated and moved to eliminate rows
- 👁️ **Block Preview**: Displays the next block to appear, helping players plan ahead
- 👻 **Ghost Block**: Shows a semi-transparent hint of where the current block will land
- 🔢 **Scoring System**: Calculates score based on eliminated rows and displays current level
- 🎚️ **Difficulty Selection**: Provides beginner, intermediate, and advanced difficulty options
- 🎛️ **Game Controls**: Supports pause/resume and restart functions

## Controls

- ← → : Move block left/right
- ↑ : Rotate block
- ↓ : Accelerate block falling
- Space : Drop block directly to the bottom
- P : Pause/resume game
- R : Restart game

## Game Screenshot

![Tetris Game Screenshot](https://cdn.forminio.cn/picx-images-hosting@master/wenzhan/俄罗斯方块截图.2rvd5ud368.webp)

## Online Demo

🎮 [Click here to play the game online](https://blog.forminio.cn/e-luo-si-fang-kuai)

## Installation and Running
Clone the repository:

```bash
git clone https://github.com/Forminio/tetris-game.git
```

Open the index.html file to start the game

## Core Implementation Logic

### Data Structures

1. **Game Board Grid**: Uses a two-dimensional array `boardGrid` to represent the game board, 0 indicates empty, non-zero values indicate fixed block types
2. **Block Shapes**: Uses the `SHAPES` array to store 7 different shapes of blocks and their types
3. **Current Block**: Uses `currentShape`, `currentType`, `currentRow`, `currentCol` to track the current active block
4. **Next Block**: Uses `nextShape` and `nextType` to store the next block to appear

### Main Functional Modules

#### 1. Game Initialization

The game initializes by setting basic parameters (rows, columns, block size, etc.), creating the game board grid, and adding keyboard and button event listeners.

#### 2. Block Generation and Movement

When generating a block, it randomly selects a shape and sets the initial position. When moving a block, it first checks if the move is valid (whether it will collide with other blocks or boundaries), then updates the position and redraws.

#### 3. Collision Detection and Block Fixing

Collision detection is used to determine if a block can move to a specified position. When a block can no longer fall, it will be fixed to the game board, then check if there are rows to be eliminated, and generate a new block.

#### 4. Row Elimination and Score Calculation

When a row is filled with blocks, the row will be eliminated, and a new empty row will be added at the top. The number of eliminated rows affects the score and game level, and level increases will speed up block falling.

#### 5. User Interaction

The game supports keyboard and button operations. Users can control block movement, rotation, and accelerated falling through the keyboard, and can also start, pause, and restart the game, as well as select difficulty levels through buttons.

## Core Functionality Details

### 1. Block Rotation Algorithm

Block rotation is implemented through matrix transposition and row reversal:

The rotation algorithm creates a copy of the block matrix and then rotates it 90 degrees. If the rotated position causes a collision, it will attempt a "wall kick" operation, trying to move left or right to accommodate the rotation.

### 2. Ghost Block Implementation

The ghost block is a semi-transparent hint of the lowest position the current block can fall to without moving:

The ghost block determines its position by simulating the current block falling until collision, then draws a semi-transparent block at that position, helping players plan their landing spot.

### 3. Game State Management

Game state management ensures the game behaves correctly in different states, such as stopping block falling in the paused state and displaying the end screen in the game over state.

## Implementation Highlights

1. **Modular Design**: Game logic is broken down into multiple functional modules, such as block generation, collision detection, row elimination, etc., making the code structure clear.

2. **Responsive Interface**: The game interface uses CSS to implement responsive design, adapting to different screen sizes.

3. **Efficient Rendering**: Uses DOM operations rather than Canvas drawing, improving performance by only updating the changed parts.

4. **Enhanced Game Experience**: Added ghost blocks, block preview, difficulty selection, and other features to enhance the gaming experience.

5. **State Management**: Implemented complete game state management, including start, pause, resume, and end states.

## Contribution Guidelines
Pull Requests and Issues are welcome!

### License
MIT License
