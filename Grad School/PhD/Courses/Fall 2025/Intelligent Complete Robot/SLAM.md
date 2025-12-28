### General class stuff
- Midterm exam on Nov. 4
	- Start making a plan for review today!
- No lecture on Nov. 6
	- $D*$-lite presentation due that day

### Lecture content
- We always use probability when discussing mapping, due to uncertainty in sensors and actuators
- at every timestep $t$, we have poses ($x_t$ or $u_t$, why we have two variables for the same thing, i don't know) and sensor measurements ($z_t$)
- doing both localization and mapping is SLAM
- relevant information vs. raw sensor data?
- integrate this information over time?
- identify previously visited state?
- data association problem
- Occupancy Grid Algorithm
	- uses the posterior of the previously visited states
		- $p(m | z_{1:t}, x_{1:t})$ 
		- $m_i$ is probability of a grid cell being occupied
		- the overall map is the product:
			- $p(m | z_{1:t}, x_{1:t}) =\displaystyle \prod_i p(m_i | z_{1:t}, x_{1:t})$  