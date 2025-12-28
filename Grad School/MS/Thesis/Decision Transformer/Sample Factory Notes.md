My goal with these notes is to trace what is happening when a full training run is made in Sample Factory, using the VizDoom environment.

When this line from the documentation is run:
````
python -m sf_examples.vizdoom.train_vizdoom --env=doom_battle --train_for_env_steps=4000000000 --algo=APPO --env_frameskip=4 --use_rnn=True --batch_size=2048 --wide_aspect_ratio=False --num_workers=20 --num_envs_per_worker=20 --num_policies=1  --experiment=doom_battle_w20_v20
````

- the `train_vizdoom.py` handles all of the command line parsing, and creates a `Runner` object to actually run the training loop
- Within `Runner`, the main configuration variables are set (in the constructor), the `run` function starts the event loop for training
- `doom_gym` handles the wrapping of the VizDoom environment, and might be a promising candidate to use if we need to use Dopamine instead, as it provides a fairly smooth (thus far) interface, including a step function needed to conform to the gym interface
- `_get_minibatches` in `learner.py` might be a good place to test saving experience replay buffer, or at least adding transistions to the buffer, test this in debug
- Design idea: train on PPO using SF for a very high timestep count (10M or more) or until convergence, and sample only 500k from after the point at which the model converges
- replace the env in trainer_doom with our environment
