# Playing Doom in Singleplayer
Created: 2022-01-13 06:19

* Formulates the decision process as a combination of a Semi-Markov decision process and several MDPs
* Uses a manager/worker paradigm to formulate strategy
* To avoid the long term credit assignment problem, a hierarchical model is used, each worker is given an intrinsic reward according to its utility
* The large action space is addressed by dividing the action space among workers, with no overlap, allowing workers to act simutaneously
* Yolo 3 or similar detection network is used to detect entities in the environment, such as resources, enemies, and doors
* StarNet is the resulting architecture (Cuz it has the shape of a star, haha), with the manager as the center and workers orbiting (they could have called it HubNet I suppose)
* The extrinsic reward from the environment is fed into the manager, which in turn, feeds the extrinsic and intrinsic rewards into the workers, along with the basic options, which are decomposed from the combined options
* Along with YOLO to detect entities, a regression model is used to estimate the depth signal (is something getting closer to us, like a wall)
* Manager and workers both use A2C, although the authors note that any RL algorithm would work
* Workers are broken down into four categories: motion worker for movement control, attacking worker for shooting enemies, tool worker is used for opening doors and activating switches, and resource worker is used for collecting resources from the environment
* While both manager and the workers use A2C, workers have an action output instead of an option output, and objectives for workers include both the intrinsic and extrinsic rewards
* The options for what action to take at any given timestep are numerous and normally mutually exclusive, but in FPS games there is often a need to combine actions, such as turning and moving or turning and shooting, and the method for handling this is known as combined options
* Intrinsic rewards are defined for each worker: motion worker receives a positive reward for shooting correctly and a negative reward for shooting the wrong direction when the number of enemies onscreen > 0, resource worker gets a positive reward if there are resources onscreen and the action selected picks them up and a negative reward otherwise, the tool worker and attacking worker function similarly
* All experiments were run in VizDoom, and PyOblige was used to generate maps
* 5 different difficulty levels were chosen, with 20 maps per difficulty level
* They compared the PMAT, AMAT and PR for each map
* Motion worker uses the SNAIL architecture, while the other workers use the same architecture as the manager
* Training was performed for 600 epochs and it looks like performance falls apart after that point
## References
1. https://www.ijcai.org/proceedings/2019/482
2. https://arxiv.org/abs/1703.01161
3. https://github.com/Trinkle23897/ViZDoom2018-Track1