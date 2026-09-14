---
created: 2026-08-23T18:29
updated: 2026-08-23T20:27
---


**Graph Traversal**
**[[DFS]]**
dive deep into 1 path, recursively

**[[BFS ]]**
visits the nodes in increasing order of their distance from starting node

[[Bellman-ford]]
shortest path from starting node to all nodes


_**[[CP Handbook]]**_

Any sorting algorithm which swaps consecutive elements will always have TC of minimum O(n^2).

when analyzing sorting problems one of the important observation is **inversion:** a pair of array elements (array[a], array[b]) such that a < b and array[a] > array[b], i.e., the elements are in the wrong order

so the TC is n^2 because these type of algorithms sorts the array with inversion so as there are number of inversions the complexity will grow, that's why a worst case reverse array has n*(n+1)/2 number of inversions that's why the TC is n^2.

And because of the inherent comparison of sorting algorithms, the algorithms to sort an array cant go lower than nlogn.