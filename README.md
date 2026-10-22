# SLE-4: Final Viva & Architecture Decision Record (ADR)

**Course:** 02AML204 – Introduction to Artificial Intelligence  
**Student:** Samruddhi Uddhavrao Patil  
**PRN:** 25UAM064  
**Division:** A  
**Project:** Grid-Based Maze Pathfinding Engine (BFS vs. DFS)  
**Repository:** https://github.com/samruddhipatil661/IAI_SLE4

## Overview
This repository documents the SLE-4 decision to use Breadth-First Search (BFS) as the primary search strategy for an unweighted, grid-based maze. It connects the algorithm profiling work from SLE-2 and the C4 architecture model from SLE-3 with a written Architecture Decision Record and viva preparation.

## Main files
- [REPORT.md](REPORT.md) — SLE-1 to SLE-4 journey, decision summary, and AI contribution note.
- [ADR.md](ADR.md) — complete Architecture Decision Record for choosing BFS over DFS.
- [VIVA_PREPARATION.md](VIVA_PREPARATION.md) — likely viva questions with concise answers.
- [CONTRIBUTION_LOG.md](CONTRIBUTION_LOG.md) — contribution and verification record.

## Decision in brief
BFS explores the grid level by level using a FIFO queue and guarantees a shortest path when all moves have equal cost. DFS uses a stack and can explore fewer nodes in some layouts, but it does not guarantee the shortest path. The project report records benchmark figures of approximately 480 nodes expanded by BFS and 270 by DFS; these figures should be presented as the reported profiling results for the tested setup, not as universal performance guarantees.

## System context
- Grid: 8 × 8
- Start: (0, 0)
- Goal: (7, 7)
- Cell values: 0 = open cell, 1 = wall
- Course: 02AML204 – Introduction to Artificial Intelligence

## Related work
The broader SLE sequence covered an AI agent in SLE-1, BFS/DFS profiling in SLE-2, C4 architecture diagrams in SLE-3, and architectural decision justification in SLE-4.

## AI contribution
The submitted SLE-4 report identifies Gemini AI as an aid for structuring profiling comparisons, organizing C4/Markdown documentation, and formatting the ADR. It also records that the student ran scripts, checked path correctness and metrics, and reviewed the final submission.

---
*Prepared for academic documentation and viva discussion. Explain the implementation and measurements honestly based on the work you actually ran.*