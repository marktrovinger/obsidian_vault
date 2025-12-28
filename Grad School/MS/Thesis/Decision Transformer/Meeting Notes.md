2/14:
Report notes:
- Generating data takes quite a bit of time, also outputs might be too large given the original image size, might want to look into that, maybe a coding session/sprint?
- Started work (hopefully not duplicating work already do) on integrating VizDoom into DT workflow, there are some methods which might be needed others maybe not
- My advisor might be MIA for a couple of weeks, not sure if that will affect anything
- Lets look at the paper that generated the datasets used by DT, I think reproducing those results might be a good idea

Meeting Notes:
- By Friday: 
	- understand frameskipping - PM
	- DQN Jax - clean run
	- upload 4 checkpoint folder to drive

## Meeting Goals 4-25-2023
- Reconcile approaches taken by me and Perusha, work together to get a final implementation working for data generation. Let's try to have that working before the end of the call! 
- Stretch goal: getting the data from SF directly into DT

## Meeting Results 4-25-2023
- The data structure was changed from lists of `torch` tensors to a `TensorDict`, which can allow us to read in the data from SF into the DT, according to Perusha's code.
- The length was changed from 32 to 128, to better match the processing code from Perusha, which should allow it to work better with the existing DT code.
- Perusha will push the revelant code to GitHub (done), and I will test a larger sample, using more of the `RolloutWorkers`.

## Work before 4-28-2023 Meeting
### Need to do:
- Get the `RolloutWorker` data in the correct `TensorDict` format and test with dataset construction code
- Add more to methods section of the paper, if possible, email a copy to Dr. H
- Once the above is done (code related), do a run on 50M timesteps, using 80 `RolloutWorkers`, and see how well it performs
### Nice to do:
- Start organizing the code into a seperate repo, needs a fair amount of organization and cleaning up
- A full 100M (or longer) run, data collection and results
- Barebones (but working!) integration of WandB for the Decision Transformer

## Meeting Notes 4-28-2023
- Change the collection to only 10% of the total
- Perusha got some better results using BC
- Work on getting smaller, but still useful amounts of data

## Meeting Notes - 5/5/2023
- We have potentially two valid data collection techniques
- Data generation vs. DT returns
	- Balance both of them
- Where does exploration loss come from? 

## Meeting Notes - 5/9/2023
- Model trained using SF Algo Observer collected data did really well!
- Mark: WandB integration

## Meeting Notes - 5/22/2023
- Mark will continue to generate experiment data, along with finalizing the integration of Weights and Biases for the DT training/eval process
- Meeting with new person on Friday to discuss papers mentioned on Monday
- Perusha is investigating methods for a chapter of her thesis
