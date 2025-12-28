### General Class
- Exam on Tuesday, HonorLock for distance students, get notes downloaded onto workstation if needed

## Obstacle Avoidance
- reactive navigation, distinct from path planning, as the obstacles in path planning are static
- global vs local path planning
	- outputs linear speed and a safe direction
	- takes rangefinder data and goal direction as input
- Navigation problems are a sequence of valid configurations
	- Source -> destination
- Moving obstacles require a different approach!
	- Moving obstacles and a moving target are even more difficult
### Virtual Field Force
- uses a potential field and certainty grid
- Potential field was discussed in AI Robotics
- Drawback: local minima
- Ideally we want to be able to change direction without having to change speed
- Occupied cells emit repulsive force
	- Magnitude is proportional to certainty
	- repulsive in obstacles
	- attractive force in target
