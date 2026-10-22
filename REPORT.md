# SLE-4: Final Viva & Architecture Decision Record (ADR) Defense

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Student:** Samruddhi Uddhavrao Patil  
**PRN:** 25UAM064  
**Division:** A  
**Date in submitted report:** 11 October 2026  
**GitHub:** https://github.com/samruddhipatil661/IAI_SLE4

## Part A — Selected architectural decision
The project selected Breadth-First Search (BFS) as the primary search strategy for an unweighted, grid-based maze. BFS uses a FIFO queue and explores the search space level by level. This provides a shortest path when one exists, assuming every move has equal cost and the BFS implementation is correct.

The maze model described in the submitted SLE-4 document is an 8 × 8 matrix with start coordinate (0, 0), goal coordinate (7, 7), 0 for open cells, and 1 for walls.

## Alternatives
1. **Depth-First Search (DFS):** Uses a LIFO stack and follows a branch before backtracking. It can expand fewer nodes in some layouts, but does not guarantee a shortest path.
2. **Greedy Best-First Search:** Uses heuristic guidance, but the result depends on the heuristic and is not generally guaranteed to be shortest.
3. **Depth-limited DFS:** Restricts search depth, but a limit can exclude a valid goal and it does not guarantee path optimality.

## Evidence and justification
The supplied SLE-4 report states that the SLE-2 profiling comparison recorded about 480 nodes expanded by BFS and 270 by DFS. These are reported results for the tested setup, not universal performance guarantees. DFS's lower reported expansion count does not mean that it always finds a better route. BFS was selected because shortest-path optimality is the key requirement for this unweighted maze model. Its trade-off is higher memory consumption from storing frontier nodes.

## Part B — SLE journey
- **SLE-1 — Foundation and planning:** Built a rule-based Python AI agent with conversational responses, runtime memory lists, and utility tools such as time, date, and calculator functions; used VS Code and Git/GitHub.
- **SLE-2 — Empirical profiling:** Implemented BFS and DFS maze solvers, counted expanded nodes, and compared performance across test cases.
- **SLE-3 — Architectural modeling:** Created a four-level C4 model covering system context, containers, components, and code-level responsibilities.
- **SLE-4 — Decision justification:** Recorded the BFS selection in an ADR and prepared to defend the decision during viva.

## Part C — C4 architecture overview
- **Level 1: System Context.** The user interacts with the maze-solving system through a command-line interface.
- **Level 2: Containers.** The documented structure separates the CLI controller (`main.py`), BFS solver (`bfs.py`), DFS solver (`dfs.py`), and supporting utilities.
- **Level 3: Components.** The submitted report names the agent/rule parser, grid-neighbor validation, and path reconstruction responsibilities.
- **Level 4: Code.** The implementation description refers to Python data structures such as deque, dictionaries, and lists.

## Part D — AI contribution note
The submitted report identifies **Gemini AI** as a support tool for structuring profiling code and benchmark comparisons, organizing C4 architecture and Markdown documentation, and formatting the ADR to the assignment structure.

The report states that the student designed the maze setup, ran Python scripts locally in VS Code, collected and checked performance metrics and path correctness, verified architectural relationships, and reviewed the final submission. Keep this note aligned with the work actually performed and be ready to explain which parts were AI-assisted.

## Conclusion
The ADR connects measured behavior from SLE-2 with the system separation documented in SLE-3. BFS was chosen for its shortest-path guarantee on an unweighted grid, while its higher memory requirement is acknowledged as the principal trade-off.

**Reference:** SLE-4 student guideline for 02AML204 – Introduction to Artificial Intelligence.