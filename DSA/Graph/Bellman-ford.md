---
created: 2026-08-23T20:28
updated: 2026-08-23T20:32
---
The Bellman–Ford algorithm1 finds shortest paths from a starting node to all nodes of the graph. The algorithm can process all kinds of graphs, provided that the graph does not contain a cycle with negative length. If the graph contains a negative cycle, the algorithm can detect this.
**Implementaion**
```
for (int i = 1; i <= n; i++) distance[i] = INF;
distance[x] = 0;
for (int i = 1; i <= n-1; i++) {
for (auto e : edges) {
int a, b, w;
tie(a, b, w) = e;
distance[b] = min(distance[b], distance[a]+w);
}
}
```

A negative cycle can be detected using the Bellman–Ford algorithm by running
the algorithm for n rounds. If the last round reduces any distance, the graph
contains a negative cycle. 