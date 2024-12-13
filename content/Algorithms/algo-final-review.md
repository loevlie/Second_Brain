## Below is a summary of how algorithms behave or differ depending on various graph properties:

### Connected vs. Disconnected Graphs

- **BFS/DFS:**  
  - On a disconnected graph, running BFS or DFS from a single vertex only covers that component. To cover all vertices, you must restart BFS/DFS from other unvisited vertices, effectively handling each component separately.
  - On a connected graph (undirected), one BFS/DFS from any vertex will visit all vertices.

- **Topological Sort / Strongly Connected Components (SCCs):**  
  - Topological sorting is defined for directed acyclic graphs (DAGs). If the directed graph is disconnected but remains acyclic, the topological order will simply list vertices from all components.
  - SCC algorithms (e.g., Kosaraju’s or Tarjan’s) work regardless of connectivity, as they identify strongly connected subgraphs within and across disconnected components.

- **MST (Minimum Spanning Tree):**  
  - MST algorithms assume a connected undirected graph to find a spanning tree for all vertices.  
  - If the graph is disconnected, you get a Minimum Spanning Forest (MSF), i.e., one MST per connected component. Kruskal’s algorithm naturally handles this by producing a forest if the graph isn’t connected. Prim’s algorithm would need to be restarted for each component.

### Directed vs. Undirected Graphs

- **BFS/DFS:**  
  - Work similarly, but in directed graphs "reachability" is not symmetric. BFS/DFS still run the same way, but the direction of edges matters for which nodes are reachable.
  
- **Topological Sort, SCCs:**  
  - These are primarily for directed graphs. Topological sort is meaningless for undirected graphs, and SCCs are defined only for directed graphs.
  
- **MST:**  
  - MST algorithms (Kruskal’s, Prim’s) are defined for undirected graphs.  
  - In directed graphs, you might look for minimum spanning arborescences (a related but different concept).

### Weighted vs. Unweighted Graphs

- **BFS/DFS:**  
  - They do not consider weights. Used on unweighted or uniformly weighted graphs to find shortest paths in $O(V+E)$.
  
- **SSSP (Single-Source Shortest Path):**  
  - For unweighted graphs, BFS finds shortest paths.
  - For positively weighted graphs, Dijkstra’s algorithm finds shortest paths efficiently.
  - For graphs with negative weights (but no negative cycles), Bellman-Ford is used.

### Positive vs. Negative Weights

- **Dijkstra’s:**  
  - Requires all edge weights to be nonnegative.
  
- **Bellman-Ford:**  
  - Handles negative weights but not negative cycles.
  
### Cyclic vs. Acyclic Graphs

- **Topological Sort:**  
  - Only applies to Directed Acyclic Graphs (DAGs). If a cycle exists, no topological ordering is possible.
  
- **Shortest Paths:**  
  - DAG shortest paths can be found very efficiently by processing vertices in topological order.
  - Cycles are fine if they don't reduce the concept of shortest path to something ill-defined. Negative cycles reachable from the source invalidate shortest path calculations.

- **MST:**  
  - MST is defined on undirected graphs. Cycles are common, and MST algorithms essentially find a subset of edges that form no cycles. Cycles do not prevent an MST from existing.

---

In summary, the suitability of each algorithm depends heavily on whether the graph is connected or disconnected, directed or undirected, weighted or unweighted (with positive or negative weights), and whether it is cyclic or acyclic. Each property can limit or shape the way an algorithm is applied or whether it works at all.
