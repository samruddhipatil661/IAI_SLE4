# SLE-4 Viva Preparation — Questions and Short Answers

**Student:** Samruddhi Uddhavrao Patil | **PRN:** 25UAM064  
**Course:** 02AML204 – Introduction to Artificial Intelligence

## Core questions

### 1. What is an ADR?
ADR stands for **Architecture Decision Record**. It documents an important design decision, the alternatives considered, the reason for the choice, and its positive and negative consequences.

### 2. What decision did you record in your ADR?
I selected Breadth-First Search (BFS) as the primary search algorithm for our unweighted grid-based maze because it guarantees a shortest path when a path exists.

### 3. Why did you choose BFS instead of DFS?
BFS explores level by level, so it finds the shortest path in an unweighted graph. DFS explores deeply along one branch and can return a longer path, even if a shorter path exists.

### 4. What is the difference between a queue and a stack?
A queue follows FIFO: First In, First Out. A stack follows LIFO: Last In, First Out. BFS uses a queue; DFS uses a stack or recursion.

### 5. What did your profiling comparison show?
The SLE-4 report records approximately 480 expanded nodes for BFS and 270 for DFS in the tested setup. DFS expanded fewer nodes in that comparison, but node count alone does not prove shortest-path optimality. I chose BFS because shortest-path correctness was the priority.

### 6. Are 480 and 270 universal values?
No. They are the figures recorded in our report for the tested setup. Results can change with maze layout, neighbor order, and measurement conditions.

### 7. What is the main disadvantage of BFS?
BFS can use more memory because it stores many nodes in its frontier queue. This can become important for larger search spaces.

### 8. What is grid-based maze pathfinding?
It is finding a route from a start cell to a goal cell in a grid while avoiding blocked cells. In our described model, 0 means an open cell and 1 means a wall.

### 9. What are the start and goal coordinates in your model?
The report describes an 8 × 8 grid, with start at (0, 0) and goal at (7, 7).

### 10. What is the C4 model and why did you use it?
The C4 model describes software architecture at four levels: System Context, Container, Component, and Code. It helps explain the system from a high-level user view down to implementation details.

### 11. Explain the Container diagram.
The documented design separates the CLI controller (`main.py`), BFS solver (`bfs.py`), DFS solver (`dfs.py`), and supporting utilities. Each part has a clearer responsibility, making the system easier to understand and maintain.

### 12. What is CLI?
CLI means **Command-Line Interface**. It lets a user interact with a program by entering commands or input in a terminal.

### 13. What does the visited set do?
It records nodes that have already been explored so the search avoids repeatedly processing the same nodes and getting stuck revisiting cycles.

### 14. What is path reconstruction?
It rebuilds the route from the start to the goal using parent information recorded while searching.

### 15. What happens when the maze becomes larger?
The search space can grow, and memory and execution time may increase. BFS can require substantial memory because it stores frontier nodes. The appropriate algorithm depends on requirements for optimality, memory, and performance.

### 16. Why not use Greedy Best-First Search?
It can use a heuristic to guide the search, but it does not generally guarantee the shortest path. BFS was a better match for our shortest-path requirement in an unweighted grid.

### 17. What did you learn across SLE-1 to SLE-4?
SLE-1 focused on building the AI agent, SLE-2 on profiling BFS and DFS, SLE-3 on modeling the architecture with C4 diagrams, and SLE-4 on documenting and defending an architectural decision.

### 18. How did you use AI?
The submitted report identifies Gemini AI as support for structuring profiling comparisons, organizing C4/Markdown documentation, and formatting the ADR. I should clearly distinguish that assistance from the code execution, testing, and validation I personally performed, as recorded in my report.

## Last-minute reminders
- Define ADR correctly: Architecture Decision Record.
- State the reason first: BFS guarantees the shortest path for an unweighted grid.
- Be honest about profiling: 480 vs. 270 are reported test results, not universal constants.
- Explain the trade-off: BFS uses more memory.
- Be able to explain your own diagrams, code, measurements, and AI contribution without reading every answer word for word.