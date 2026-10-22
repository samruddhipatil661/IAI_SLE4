# Architecture Decision Record (ADR)

**Title:** Selection of Breadth-First Search (BFS) over Depth-First Search (DFS) for Grid Maze Pathfinding Optimization  
**Status:** Accepted  
**Date:** 12 October 2026  
**Student:** Samruddhi Uddhavrao Patil  
**PRN:** 25UAM064 | **Division:** A  
**Course:** 02AML204 – Introduction to Artificial Intelligence

## 1. Context
The maze pathfinding engine models an 8 × 8 grid, with start node (0, 0) and goal node (7, 7). A value of 0 represents an open cell and 1 represents a wall. The system needed a search strategy that could navigate around barriers while balancing execution cost and path optimality. Because each move is treated as having equal cost, finding a shortest route is an important requirement.

## 2. Decision
BFS was selected as the primary traversal strategy. The implementation uses a FIFO queue, implemented with Python's `collections.deque`, together with visited-node tracking and parent information to reconstruct the path.

## 3. Alternatives considered
- **DFS using a LIFO stack:** Can explore deeply and may expand fewer nodes in some maze layouts, but does not guarantee the shortest path.
- **Greedy Best-First Search:** Uses a heuristic to guide exploration, but its route quality depends on the heuristic and it does not generally guarantee the shortest path.
- **DFS with a depth limit:** Limits exploration depth, but the limit may prevent reaching a valid goal beyond that depth and does not provide shortest-path optimality.

## 4. Rationale / Justification
The SLE-2 report records profiling results of approximately 480 expanded nodes for BFS and 270 for DFS in the tested comparison. These values are observations from that setup, not universal algorithm constants. Although DFS expanded fewer nodes in the reported tests, fewer expansions alone do not establish that a route is optimal. BFS explores nodes level by level, so in an unweighted grid it finds a shortest path when a path exists and standard BFS is implemented correctly. This matches the project's priority of reliable shortest-path discovery. The SLE-3 C4 model separates the CLI controller, BFS and DFS solver modules, and supporting utility functions, making the search strategy easier to explain and compare. BFS's main trade-off is higher memory use because it stores frontier nodes in a queue.

## 5. Consequences
### Positive
- Guarantees a shortest path for an unweighted graph/grid when a path exists and BFS is implemented correctly.
- Provides systematic level-by-level exploration.
- Makes the route and search behavior easier to explain during testing and viva.

### Negative / trade-offs
- Can consume more memory than DFS because many frontier nodes may be stored.
- May expand more nodes than DFS in particular maze layouts.
- The reported node counts depend on the maze, neighbor order, and measurement setup.

## 6. References
- SLE-2 profiling and BFS/DFS comparison work.
- SLE-3 C4 architecture model.
- Project repository: https://github.com/samruddhipatil661/IAI_SLE4
- Student guideline: SLE-4 Final Viva & Architecture Decision Record (ADR) Defense, course 02AML204.

---
**Defense summary:** BFS was chosen because shortest-path correctness mattered more than minimizing node expansions in every individual test.