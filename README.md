8-Puzzle Solver using BFS and DFS
SLE-3: Architectural Design (Full C4 Model)
Course: 02AML204 – Introduction to Artificial Intelligence
PRN: 25UAM087
Name: Pranav Gajanan Revankar
Division: B
Date: 04 October 2026
GitHub: https://github.com/pranavrevankar33-ctrl
1. Project Description
The 8-Puzzle Solver is a search-based AI system that solves a 3×3 sliding-tile puzzle using two uninformed search algorithms:
Breadth-First Search (BFS)
Depth-First Search (DFS)
The system takes a fixed start state and goal state and searches for the goal. For each algorithm, it counts the number of nodes expanded and measures the average execution time over 3 runs.
The same puzzle, start state, and move order are used for both algorithms so their performance can be compared fairly.
2. C4 Architecture
Level 1 – Context
The User / Operator provides the start state and goal state and receives the average execution time and number of nodes expanded for BFS and DFS.
The system has no external database or network dependency and uses Python's standard library.
Level 2 – Containers
The system contains six main building blocks:
Input Module – Holds INITIAL_STATE and GOAL_STATE.
Experiment Driver – Runs each solver 3 times and measures execution time.
Search Engine – Contains solve_bfs() and solve_dfs().
Neighbour Generator – get_neighbors() generates valid moves.
Memory / Visited Set – Prevents states from being expanded twice.
Output Module – Prints the final performance summary.
Level 3 – Components
Inside the Search Engine:
Frontier – A deque for BFS and a list for DFS.
Goal Test – Checks whether the current state is the goal.
Node Counter – Counts expanded nodes.
Neighbour Lookup – Generates the next states.
Visited Set – Prevents repeated state expansion.
The implementation counts nodes but does not reconstruct an actual move path.
Level 4 – Code
Name
Type
Responsibility
INITIAL_STATE
Tuple
Fixed starting state
GOAL_STATE
Tuple
Fixed goal state
get_neighbors(state)
Function
Returns valid Up/Down/Left/Right states
solve_bfs(start, goal)
Function
Performs Breadth-First Search
solve_dfs(start, goal)
Function
Performs Depth-First Search
run_experiments()
Function
Runs both algorithms 3 times and measures results
3. BFS and DFS
Breadth-First Search (BFS)
BFS uses a FIFO queue (deque) and explores states level by level.
Depth-First Search (DFS)
DFS uses a LIFO stack (list) and explores one branch deeply before moving to another.
Both algorithms use the same neighbour generator and visited set. The main difference is the Frontier data structure.
4. Design Decisions
get_neighbors() is shared by BFS and DFS to keep the comparison fair.
BFS uses a deque, while DFS uses a list.
A visited set prevents cycles in the puzzle's state graph.
Timing is handled only by the Experiment Driver.
No heuristic module is used because BFS and DFS are uninformed algorithms.
An A* version could later be added with a heuristic component.
5. Performance Measurement
Each algorithm is executed 3 times.
Execution time is measured using:
time.perf_counter()
The system reports the average execution time and number of nodes expanded.
6. Technologies Used
Python
Breadth-First Search (BFS)
Depth-First Search (DFS)
C4 Model
Python standard library: time, collections
7. AI Contribution
AI Tools Used
Gemini
ChatGPT
Claude
AI Helped With
Suggested the C4 structure.
Drafted the four architectural levels.
Produced diagrams.
Drafted explanations from the SLE-1 and SLE-2 reports.
My Contribution
Chose the BFS/DFS 8-Puzzle system.
Reviewed the diagrams and descriptions.
Checked the architecture against bfs_dfs_8puzzle.py.
Verified that container and function names match the implementation.
8. Project Evolution
SLE-1: Built a rule-based chatbot agent.
SLE-2: Measured the 8-Puzzle BFS/DFS search code.
SLE-3: Documented the architecture using the C4 Model.
9. Conclusion
The C4 model represents the 8-Puzzle Solver at four levels:
Context → Container → Component → Code
The architecture shows that BFS and DFS share the same neighbour-generation logic and visited-set approach, while their main difference is how the Frontier is handled.
Author
Pranav Gajanan Revankar
PRN: 25UAM087
Division: B
