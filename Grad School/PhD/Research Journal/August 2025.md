## August 1, 2025
### Kinova Group
Meeting notes:
- Leo working on hardware, paper sections for grasping
- I was added to the paper
- Probably need to update the group on MA simulation progress
- Work on any writing that needs done

### Robust MARL
Worked on getting the trajectory extraction working, need to be able to pull trajectories that are at terminal states.

## August 2, 2025
### Robust MARL
Working on getting trajectory sampling working, using methods in flashbax. 
Ideas:
- `buffer = fbx.make_prioritised_flat_buffer(...)`
- `buffer = fbx.make_prioritised_trajectory_buffer(...)`

Basically, I need to be able to grab data from episode ending trajectories, so they need to have `1. 1. 1.` as the data in the terminal dictionary.

## August 3, 2025
Based on what I learned yesterday, and today, I need a way to iterate through the terminals and add the observations that coincide with a terminal state. Since this is stored in a Jax format, I might be able to just grab them, but I need to research this more.

## August 4, 2025
Worked on a couple of ideas for getting correct trajectories. The iteration method is way too slow, trying the mask idea tomorrow.

## August 5, 2025
Working on the masking idea, and then trying to pipeline the mask-> trajectories-> LLM-> dataset. Masking worked, now I need to extract both the allied and enemy health data for comparison.

##  August 6, 2025
### Robust MARL
Thinking about how the reward model should be structured.

### ViZDoom Meeting
Working on the single-player environment, focusing on the single player "campaign". Possible ideas: text buffer output to some sort of agent. 
- Support inside of the engine, hijacking the internal log structure and exposing those to the python api, similar to how SMAC outputs the state.
- High level planner that could examine a text version of the scene and make decisions based on the information

#### TODOs:
- Work on the very basic proof of concept, look at adding a flag to the `base_gymnasium_env` that will output the labels for what is seen as well as game variable information. 
- Need to get `x11` forwarding working for a demonstration next week.
	- Or just develop on macOS

### Thoughts
The game variables may need to be adjusted, but do we want to do that for every scenario? Is there a way to "backdoor" and get the variables needed, such as health, even when the scenario doesn't allow that info?

## August 7, 2025
### Robust MARL
Based on the Teams conversation with Dr. Sun yesterday, I need to really put some time into this project, or he may drop me as a student. To that end, I am devoting the majority of the hours during 8-5 to work on this project, and possibly an hour (at least) in the evening as well. I am going to keep a running list of tasks that need done, using this document to track my progress. 
#### TODOs:
- Pipeline from dataset->LLM working without issue, for both the Trajectory and Action Comparison prompts. The trajectory prompt looks at only the final state, so we need a different approach for the action comparison.
- For AC prompt, we need two subsequent states, in order to judge the actions of the agents in question. Using this framework though, we could simply have it evaluate the performance of an individual agent, by sampling two states.
	- The preference model indicates that the reward for a preferred action and a dispreferred action, under a given state. How closely do the states need to match in order to determine action preference? Let's assume that we can find two states that are similar enough in the data for the moment.

## August 11, 2025
I am officially off of the robust MARL project.

### Robotics
I am reading through the digital twins paper that Dr. Chen sent me, and I am taking a robotics course this coming semester. I plan to take several robotics courses, as this will be my research area going forward.

## August 13, 2025
### ViZDoom
Working on telemetry data output, it appears that the ANSI render mode wasn't ever created?
Questions for Marek:
- Mac or Linux, does it matter?
	- Asked on Discord
- Robot telemetry, observation space, what would it look like? Do we need to know the number of objects within the scene? Does this fit with the goals of the project?
	- Use the JSON format and the text space in Gymnasium
- Development question: rebuild after changing something is necessary?
	- Also, asked on Discord

## August 14, 2025
### ViZDoom

## August 15, 2025
### Book Chapter
Should be 10-15 pages, first draft is due March 1, 2026, review chapter due May 1, revised due June 15.
- How computer science-y should I get?
	- More would be better

### Kinova Group


### Dr. Chen Meeting
Digital twin of CAVS proving ground? Use of digital twins/cousins in construction, as the state of the building changed from the previous day's work

#### Digital Twin for Offroad
- Active research project, doesn't need to use MAVs, could use Gazebo, or Unity

#### Construction
"Living" digital twin, use of vision foundation models, LLMs for image recognition, stored in web/cloud interface, used by site managers to oversee project, sent to ROS/Gazebo for robotic simulations
- Jenny, Charles

#### Bigger Picture 
- Academia
	- More theoretical
- Industry
	- More practical
	- Space rovers is a mixture of theoretical and practical

Action items:
- Read through framework paper Dr. Chen sent me, look through for possible ideas
- Read through any other materials he sends me
- After paper submission, Leo will continue on that arm, we will meet separately 
## August 19, 2025
### ViZDoom
Working on getting the text output working before the meeting tomorrow. Also need to work on getting a better issue description written on GitHub.

### Robotics/Digital Cousin

## August 20, 2025
### ViZDoom Meeting
Tristan might be able to help, I need to work on getting something closer to a workable solution implemented for MA. Look at SMAC for how to translate terrain features into numeric.

### Robotics
Testing getting the Quadcopter-v0 working in IsaacLab on Brawler. How do we approach having multiple drones working in a MA setting?

## August 21, 2025
### ViZDoom
Still working on getting a PR ready for text output, plan to finish that prior to the meeting next Wednesday. I also want to work on a better outline of the multi-agent code so I can work with Tristan.

### Robotics
Got the Quadcopter-v0 working, still need to work on how a MA setting of this would work. I also need to message Dr. Chen about moving forward on either the digital twins work or on the offroad work that MAVS is doing.

### SMAC w/ John
I need to think about what ideas I have before the meeting tomorrow. I should probably message him to see what we want to discuss.

### General
This is something I need to keep in mind when thinking about research, from Andy Matuschak in a piece entitled ["Cultivating depth and stillness in research"](https://andymatuschak.org/stillness/):

>Another pattern has to do with my stance towards the work. I’m much more likely to flinch away from difficulty when I view my research problem as a task, as something to be accomplished. I’m much less likely to flinch away when I’m feeling intensely curious, when I truly want to understand something, when it’s a landscape to explore rather than a destination to reach. Happily, curiosity can be cultivated. And curiosity is much more likely than task-orientation to lead me to interesting ideas.

## August 22, 2025
### RL Meetings
SMACv2lite? Maybe a different approach not taken in the paper? 
Action Items:
- Papers read and possible approaches listed

### Robotics

## August 25, 2025
### CRDF
#### Simulators
#### Approaches


## August 27, 2025
### ViZDoom
Finished the text output PR. Meeting notes:
- Tristan is working on the MA stuff, running into some issues with multi-threaded performance
- Muhammed is working on finishing audio stuff
- Telemetry as observation wrapper instead of in base gym environment, getting game variables is easier than using the config file for the environment
- Implement scripts that do learning for next meeting