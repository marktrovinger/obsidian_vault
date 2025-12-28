## Branch and Bound
- explore implicit graphs
	- not stored in memory, but a representation of the overall state
- looking for an optimal solution to the problem
- idea: calculate a bound on the possible values that lie farther in the graph
- if the only solution is worse farther into the graph, we don't need to explore any more of this part of the graph
- DFS or BDS search + the bounds calculation
- DFS
	- inverse order of creation
	- stack
- BFS
	- order of creation
	- queue
- Examples:
	- Knapsack
		- $\Sigma_{i=1}^k x_i v_i + (W - \Sigma_{i=1}^k x_i w_i)\frac{v_{k+1}}{w_{k+1}}$ 
			- first term is the item value
			- second is the bound on the value that can be added
		- generate only successor nodes that satisfy the weight constraint
		- calculate an upper bound on the solution value and cut useless branches in order to guide exploration
	- Assignment

## Backtracking
- search organization in an implicit graph
- resembles DFS, typically a tree but at least acyclic
- idea:
	- build partial solutions as search progresses 
	- successful if the solution can be completely defined, unsuccessful in cases where a partial solution isn't able to be completed
- Knapsack:
	- Implicit tree is constructed, with each node as a partial solution to the problem, and if a new best solution is found, it is added as the possible global solution, until a better global solution is found