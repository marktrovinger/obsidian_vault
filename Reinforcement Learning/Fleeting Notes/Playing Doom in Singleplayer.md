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
* 
## References
1. https://www.ijcai.org/proceedings/2019/482