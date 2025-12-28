## Useful?
Probably, the authors mention using datasets of SMAC v1 and v2 and use GPT-4o to annotate labels. They also had to give the LLM additional game variable type information, shields, health, positions etc.

One possible issue is the prompt needed to do is, well, let's say verbose:
```
You are a helpful and honest judge of good game playing and progress in the StarCraft Multi-Agent Challenge game. Always answer as helpfully as possible, while being truthful.
If you don’t know the answer to a question, please don’t share false information. I’m looking to have you evaluate a scenario in the StarCraft Multi-Agent Challenge. Your role will be to assess how much the actions taken by multiple agents in a
given situation have contributed to achieving victory.
The basic information for the evaluation is as follows.
- Scenario : 5m_vs_6m
- Allied Team Agent Configuration : five Marines(Marines are ranged units in
StarCraft 2).
- Enemy Team Agent Configuration : six Marines(Marines are ranged units in
StarCraft 2).
- Situation Description : The situation involves the allied team and the enemy team
engaging in combat, where victory is achieved by defeating all the enemies.
- Objective : Defeat all enemy agents while ensuring as many allied agents as
possible survive.
* Important Notice : You should prefer the trajectory where our allies’ health is
preserved while significantly reducing the enemy’s health. In similar
situations, you should prefer shorter trajectory lengths.
I will provide you with two trajectories, and you should select the better
trajectory based on the outcomes of these trajectories. Regarding the
trajectory, it will inform you about the final states, and you should select
the better case based on these two trajectories.
[Trajectory 1]
1. Final State Information
2) Allied Agents Health : 0.000, 0.000, 0.067, 0.067, 0.000
3) Enemy Agents Health : 0.000, 0.000, 0.000, 0.000, 0.000, 0.040
4) Number of Allied Deaths : 3
5) Number of Enemy Deaths : 5
6) Total Remaining Health of Allies : 0.133
7) Total Remaining Health of Enemies : 0.040
8. Total Number of Steps : 28
[Trajectory 2]
9. Final State Information
10) Allied Agents Health : 0.000, 0.000, 0.000, 0.000, 0.000
11) Enemy Agents Health : 0.120, 0.000, 0.000, 0.000, 0.000, 0.200
12) Number of Allied Deaths : 5
13) Number of Enemy Deaths : 4
14) Total Remaining Health of Allies : 0.000
15) Total Remaining Health of Enemies : 0.320
16. Total Number of Steps : 23
Your task is to inform which one is better between [Trajectory1] and [Trajectory2]
based on the information mentioned above. For example, if [Trajectory 1] seems
better, output #1, and if [Trajectory 2] seems better, output #2. If it’s
difficult to judge or they seem similar, please output #0.
* Important : Generally, it is considered better when fewer allied agents are
killed or injured while inflicting more damage on the enemy.
Omit detailed explanations and just provide the answer.
```

While that looks pretty terrible, if we were able to get the dataset generated from these prompts, we might be able to just corrupt/perturbe the dataset.
