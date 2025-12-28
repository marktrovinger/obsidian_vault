- Mobile robot path planning
- Goal: feasible, computationally efficient
### Ant Colony Optimization
- Colony (start) -> pheromone trail (path) -> food (goal)
- Swarm intelligence for multiple robots
- Can handle dynamic environment well
#### Pheromone Trail
- Laid by ants on the route
- Strength increases as more ants travel the trail
- Dynamic update of strength of pheromone
- Map config is an adjacency matrix
- Can always find near-optimal solution
	- No guarantee of best results
	- Dependent on number of iterations
- Professor works through a 4 city TSP example