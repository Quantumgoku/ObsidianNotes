---
created: 2026-08-23T20:16
updated: 2026-08-23T20:26
---
O(n+m) -> n=#node, m=#edges
dive deep into 1 path, recursively
Use it when question asks to find or ig need to visit all nodes

**Implementation**
```
void dfs(int s) {
if (visited[s]) return;
visited[s] = true;
// process node s
for (auto u: adj[s]) {
dfs(u);
}
}
```
