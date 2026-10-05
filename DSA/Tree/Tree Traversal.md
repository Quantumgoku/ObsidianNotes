---
created: 2026-09-22T18:44
updated: 2026-09-22T19:05
---
Same as graph traversal but easier as there are no cycles in the tree and it is not possible to reach a node from multiple directions.

The typical way to traverse a tree is to start a [[DFS]] 
`void dfs(int s,int e){
	for(auto u: adj[s]){
		if(u!=e) dfs(u,s);
	}
}`

s-> current node
e-> prev node, cuz to make sure that the search only moves to nodes that have not been visited yet

**Algos**
A general way to approach many tree problems is to first root the tree arbitrarily.
[[Diameter]]


DP
DP can be used to calculate some info during a [[Tree Traversal]] 
we can calculate in O(n) -> time for each node of a rooted tree the number of nodes in its subtree 
The length of the longest path from the node to a leaf