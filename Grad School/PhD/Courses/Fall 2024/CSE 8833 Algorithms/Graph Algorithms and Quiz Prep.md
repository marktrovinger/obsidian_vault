# Convex Hull
- divide and conquer approach, runs in $O(n \log n)$ time
- others: Graham scan: $O(n \log n)$ and Jarvis march: $O(nh)$, where $h$ is the number of points on the hull and when $h \ll \log n$
	- all are optimal

# MST, Prim's, Kruskal's
- MST: a tree (acyclic), covers all $V$, lowest possible cost
- Used for PCB design, network, phones

## Kruskal's
- uses a disjoint-set data structure

## Prim's
- heap data structure, similar to Dijkstra's
	- Complexity:
		- array: $O(V^2)$
		- binary heap: $O(E \log V)$
		- Fib heap: $O(E + V \log V)$

# BFS, DFS
## BFS
- explores "out" before "down"
- complexity: $O(V+E)$ 
## Dijkstra's Algorithm
- shortest path algorithm
- complexity: $O(V (T_{ins} + T_{ex}) + ET_{dec})$ or $O(V \log V + E \log V) = O(E \log V)$ 
- array: $O(V^2)$
- binary heap: $O(E \log V)$
- fib heap: $O(V \log V + E)$ 

## DFS
- explores "down" before "out"
- 2 timestamps per vertex
	- discovery
	- finishing
- complexity: $\Theta(V+E)$
- Topological sort: $O(V + E)$

# Greedy and DP
## Greedy
- Fib:
	- recursive is exponential, $O(2^n)$
	- DP is linear, $O(n)$ 
## DP
- Dijkstra's algorithm
- Bellman-Ford algorithm
