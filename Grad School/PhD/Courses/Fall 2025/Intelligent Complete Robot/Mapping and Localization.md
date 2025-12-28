### General class stuff - October 27, lecture from October 23
- Nothing to report, asked Dr. Luo about how the exam will be given to online students, no response yet
- Starting on $D*$-lite presentation on Thursday
- Working on prep for the exam, but first focus is on HW3

### Lecture Content
- Continues (somewhat) from [[SLAM]] and [[Mapping]]
- OGM
	- discretization of a continuous space
	- each cell represents the _probability_ of a cell being occupied
		- this can be binary (1 or 0) or probabilistic 
		- Updated with sensor data, sensor fusion covers gaps or limitations in sensor systems
	- Used in [[SLAM]]
	- Grid maps or landmark (this seems to be a more general note about mapping)
	- Feature maps are used with Kalman filters, but can use significant resources
	- Posterior over maps (checked and I had the wrong answer in HW3)
	- state is assumed to be _static_
- Binary Bayes Filter
	- Log odds form transforms a product (mentioned in [[SLAM]]) into a sum, which are much less resource intensive to compute
	- Each cell is updated using this method
	- $P(z|x)$ probability of a measurement given a pose?
		- Not much was explained about this, was at the end of the lecture, so maybe more next Thursday?