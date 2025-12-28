## ViZDoom and Sample Factory
Install dependencies:
``````
sudo apt install cmake git libboost-all-dev libsdl2-dev libopenal-dev
``````

Install ViZDoom:
```
pip install vizdoom
```

Assuming all is well, next install Sample Factory:
```
pip install sample-factory
```
Then install Weights and Biases:
```
pip install wandb==0.15
```
Then we can clone the repo.

## Experiment #1
Using the basic example for ViZDoom, I ran it on the A10 instance on Lambda Labs. Command is here: 
```
python -m sf_examples.vizdoom.train_vizdoom --train_for_env_steps=500000000 --algo=APPO --env=doom_my_way_home --env_frameskip=4 --use_rnn=True --num_workers=36 --num_envs_per_worker=8 --num_policies=1 --batch_size=2048 --wide_aspect_ratio=False --experiment=doom_basic_envs
```

It is pretty slow, but even then, it might be a better solution than having to store large files.

## Experiment #2
Using the script to generate files. Much faster!