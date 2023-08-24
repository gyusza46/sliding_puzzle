# Sliding Puzzle Solver

This repository contains a Python program that solves the sliding puzzle using the A* algorithm. The sliding puzzle is a classic puzzle game in which a player must slide tiles into the correct positions to solve the puzzle.

## Description

The program uses the A* algorithm to solve the sliding puzzle. The main steps of the program are explained below.

### 1. Loading and Slicing the Image

The program starts by loading an image and dividing it into smaller parts based on the specified grid size. This step is performed using the `slicing` function.

### 2. Defining the Goal State

The `goal` function generates the goal state of the puzzle based on the given grid size. This goal state serves as the reference for solving the puzzle.

### 3. Checking Solvability

The `solvable` function determines whether a given puzzle configuration is solvable or not. The solvability condition depends on the parity of the grid size and the number of inversions in the puzzle.

### 4. Swapping Tiles and Generating Possible Steps

The `swap` function swaps two tiles in the puzzle configuration. The `steps` function generates all possible steps (neighboring configurations) from the current puzzle configuration.

### 5. Calculating Manhattan Distance

The `distance` function calculates the Manhattan distance between the current puzzle configuration and the goal state. This heuristic is used in the A* algorithm to estimate the cost of reaching the goal.

### 6. Solving the Puzzle using A*

The `solveAstar` function implements the A* algorithm to solve the sliding puzzle. It uses a priority queue to explore possible paths and selects the path with the lowest estimated cost (heuristic + path cost) to the goal.

## Usage

To use the sliding puzzle solver, follow these steps:

1. Define the starting puzzle configuration using a 2D list.
2. Generate the goal state using the `goal` function.
3. Check if the puzzle is solvable using the `solvable` function.
4. If solvable, call the `solveAstar` function with the starting and goal configurations.

```python
start = [[6, 2, 5, 1],
         [9, 7, 12, 4],
         [13, 0, 3, 8],
         [14, 10, 11, 15]]  # Initial puzzle configuration

final = goal(len(start))  # Generate the goal state

if solvable(start, final):  # Check if the puzzle is solvable
    solveAstar(start, final)  # Solve the puzzle using A*
