# Updates
- trying to get the hang of building a project using ROS at this level
- `openai_ros` works on my workstation, cartpole example hangs for unknown reason, hope to fix later today
- Working on a course through the Constuct to get experience building projects using `openai_ros` faster, and with fewer problems
- `ros_gazebo_gym` uses SB3 for models, that is probably where we will end up as well
- Gym env is needed for next steps
	- Notes for creation in markdown document in the project repo
		- Later today, ideally, by the end of the week at worst
	- Maybe use Kinova API, not sure how the actual agent to robot interface is going to work yet
	- Similar envs (robotic arms) exist already, thinking about using those as a template for building the kortex env
## Goals for this week
- Notes completed (v1 anyway) for `gym` environment
- Figure out how Kortex <-> gym work together, and start thinking about how the robot might be controlled (start at least)
- course completed

## Dr. Chen
- small proof of concept
	- sim and real robot
- pose RL problem
	- what kind of problem do we want to solve?
	- how complex should it be?
- high level state
	- discretize actions and states
	- exact sequence sim2real
- simple idea:
	- sequence planning task
- task division
	- RL
	- different parts of simulator
	- multiple robots in simulator
	- gripper, actuation, moving objects from one place to another
	- formulate actions and states
- meetings with Leo and Dr. Chen on Fridays