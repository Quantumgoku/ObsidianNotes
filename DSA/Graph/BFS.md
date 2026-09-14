---
created: 2026-08-23T19:49
updated: 2026-08-23T19:58
---
Problems that use BFS usually ask to find the fewest number of steps (or the shortest path) needed to reach a certain end point (state) from the starting one. Besides this, certain ways of passing from one point to another are offered, all of them having the same cost of 1 (sometimes it may be equal to another number).

BFS guarantees that when you first reach a cell you reached it using the shortest number of moves.

```
visited[x] = true;
distance[x] = 0;
q.push(x);
while (!q.empty()) {
int s = q.front(); q.pop();
// process node s
for (auto u : adj[s]) {
	if (visited[u]) continue;
	visited[u] = true;
	distance[u] = distance[s]+1;
	q.push(u);
}

```

Basic Code for traversal
