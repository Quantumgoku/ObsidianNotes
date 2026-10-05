---
created: 2026-09-20T13:50
updated: 2026-09-20T14:03
---
**Topological Sort**
an ordering of the nodes of a directed graph such that if there is a path from node a to node b, then node a appears before node b in the ordering

Algo:
go through the nodes of the graph and always begin a [[DFS]] at the current node if it has not been processed yet.
Three states:
1-> state 0- the node has not been processed
2-> state 1- the node is under processing
3-> state 2- the node has been processed


If a directed graph is acyclic, DP can be applied. We can efficiently solce the following problems concerning paths from a starting node to an ending node:
-> how many different paths are there?
-> what is the shortest/longest path?
->what is the min/max no edges in a path?
-> which nodes certainly appear in any path?