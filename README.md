# Multithreaded Rat-in-a-Maze Solver (Java)
## Problem Description:
<img width="653" alt="image" src="https://github.com/hdyrmdht/Rat_in_a_Maze_Problem-main/assets/73208810/7b5016a0-17ce-4da3-9427-05faf54d443e">
<img width="217" alt="image" src="https://github.com/hdyrmdht/Rat_in_a_Maze_Problem-main/assets/73208810/aac8299c-2f6c-43d8-9100-6ef2b2c1f44c">


Given an 𝑁 × 𝑁 binary matrix representing a maze where 0 indicates a dead end and 1 indicates a passable block, this project addresses the task of navigating a rat from the upper left corner (source) to the lower right corner (destination). The rat can only move forward and down in the matrix.

## Solution:
Utilizing multithreading in Java, this program dynamically generates a maze grid based on user-defined dimensions. It allows the user to mark dead blocks in real-time. The solution employs two parallel threads: one to move the rat forward and another to move it downward. These threads coordinate via a shared variable (deadEnd) to identify and handle dead ends, utilizing random waiting times.

## Race Condition Mitigation:
To address race conditions arising from shared access to the grid class (an ArrayList storing the rat's steps), mutex locks have been implemented. This ensures exclusive access to the critical section, preventing conflicts and ensuring data consistency.

## Algorithm Overview:
The algorithm's behavior is nondeterministic due to the nature of multithreading. Each thread attempts to move the rat forward or downward based on available paths. If a dead end is encountered, the rat backtracks to the nearest junction with multiple paths and explores alternate directions.

## Special Case Handling:
In scenarios where the rat faces a dead end after choosing a specific path, it retraces steps to the nearest junction with multiple paths, marks the chosen direction as blocked, and explores other available paths.

## Division of Labor:
Sayed Mahmoud and Sara Abdelhafiez: Maze generation
Dimiana Ibrahiem: Grid handling
Ahmed Adel: Rat's forward movement
Ahmed Hegazy: Rat's downward movement
Mohamed Reda: GUI development
Hadeer Medhat: Documentation

## > Project documentation:https://github.com/hdyrmdht/Rat_in_a_Maze_Problem-main/raw/main/RAT%20IN%20MAZE%20documentation.docx
