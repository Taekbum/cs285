## How to run

```
cd <path to hw5 folder>
```

1. For Part 1.1, run
```
python cs285/scripts/run_hw5_expl.py --env_name PointmassEasy --use_rnd --unsupervised_exploration --exp_name q1_PointmassEasy_rnd
python cs285/scripts/run_hw5_expl.py --env_name PointmassEasy --unsupervised_exploration --exp_name q1_PointmassEasy_random
python cs285/scripts/run_hw5_expl.py --env_name PointmassHard --use_rnd --unsupervised_exploration --exp_name q1_PointmassHard_rnd
python cs285/scripts/run_hw5_expl.py --env_name PointmassHard --unsupervised_exploration --exp_name q1_PointmassHard_random
```

2. For Part 1.2, run
```
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --unsupervised_exploration --use_cbe --exp_name q1_count_base_alg_med
python cs285/scripts/run_hw5_expl.py --env_name PointmassHard-v0 --unsupervised_exploration --use_cbe --exp_name q1_count_base_alg_hard
```

3. For Part 2.1, run
```
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --exp_name q2_dqn --use_rnd --unsupervised_exploration --offline_exploitation --cql_alpha=0
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --exp_name q2_cql --use_rnd --unsupervised_exploration --offline_exploitation --cql_alpha=0.1
```

4. For Part 2.2, run
```
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --num_exploration_steps=5000 --offline_exploitation --cql_alpha=0.1 --unsupervised_exploration --exp_name q2_cql_numsteps_5000
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --num_exploration_steps=15000 --offline_exploitation --cql_alpha=0.1 --unsupervised_exploration --exp_name q2_cql_numsteps_15000
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --num_exploration_steps=5000 --offline_exploitation --cql_alpha=0.0 --unsupervised_exploration --exp_name q2_dqn_numsteps_5000
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --num_exploration_steps=15000 --offline_exploitation --cql_alpha=0.0 --unsupervised_exploration --exp_name q2_dqn_numsteps_15000
```

5. For Part 2.3, run
```
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --unsupervised_exploration --offline_exploitation --cql_alpha=0.02 --exp_name q2_alpha0.02
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --unsupervised_exploration --offline_exploitation --cql_alpha=0.5 --exp_name q2_alpha0.5 
```

6. For Part 3, run
```
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --cql_alpha=0.1 --exp_name q3_medium_cql
python cs285/scripts/run_hw5_expl.py --env_name PointmassMedium-v0 --use_rnd --cql_alpha=0.0 --exp_name q3_medium_dqn
```
```
python cs285/scripts/run_hw5_expl.py --env_name PointmassHard-v0 --use_rnd --cql_alpha=0.1 --exp_name q3_hard_cql
python cs285/scripts/run_hw5_expl.py --env_name PointmassHard-v0 --use_rnd --cql_alpha=0.0 --exp_name q3_hard_dqn
```


## Results
+ You can see ```curr_state_density.png``` and  ```eval_last_traj.png``` of each experiments in each experiment folder in ```run_logs``` folder.
+ You can see results of each experiments in tensorboard. Just click these urls.
  * Part 1.1 
    
  - PointmassEasy (L: random / R: rnd)
  
  
  
  
  
  <img src="https://user-images.githubusercontent.com/53718808/107468079-b037ee80-6baa-11eb-95b9-44d00eb12d11.png" width="300" height="225"> <img src="https://user-images.githubusercontent.com/53718808/107468113-c2b22800-6baa-11eb-8af0-466db569bc34.png" width="300" height="225">
  
  - PointmassHard (L: random / R: rnd)
  
  
  
  
  
  <img src="https://user-images.githubusercontent.com/53718808/107468146-d493cb00-6baa-11eb-91d9-7a54e5b3334c.png" width="300" height="225"> <img src="https://user-images.githubusercontent.com/53718808/107468172-e2495080-6baa-11eb-8423-d33746524c11.png" width="300" height="225">
  
  https://tensorboard.dev/experiment/80V26O4DRY2oJE0wmfrMmg/#scalars  easy, random
  https://tensorboard.dev/experiment/PsX9BBnET66PlYzjuZsBIw/#scalars  easy, rnd
  https://tensorboard.dev/experiment/xs2eZ6Z9TNyK4RroT30BIQ/#scalars  hard, random
  https://tensorboard.dev/experiment/bD5aVvfJSZa8uk5tnztGmw/#scalars  hard, rnd

  * Part 1.2 
  (count-based-algo.)
  
  
  
  
  
  <img src="https://user-images.githubusercontent.com/53718808/107468256-01e07900-6bab-11eb-8684-34d9d9fff214.png" width="300" height="225"> <img src="https://user-images.githubusercontent.com/53718808/107468312-13298580-6bab-11eb-8776-0b5176113410.png" width="300" height="225">
  (L: PointmassMedium / R: PointmassHard)
  
  https://tensorboard.dev/experiment/nySmGm6JQ3yUq8Ae8v8fkA/#scalars  medium
  https://tensorboard.dev/experiment/4ns7xeABRAKvN2vJyDx1uA/#scalars  hard
  
  * Part 2.1 (PointmassMedium)
  https://tensorboard.dev/experiment/GZy7hdFeRUO7UjmADiEXig/#scalars  dqn
  https://tensorboard.dev/experiment/RLrVtMnIRFeRHjeWeUO3aQ/#scalars  cql
  https://tensorboard.dev/experiment/l1m0e6d4TqO5jtlefyGVYw/#scalars  cql with shift=1, scale=100
  
  * Part 2.2 (PointmassMedium)
  https://tensorboard.dev/experiment/H6cpgHO0Qj66KxwYhV648w/#scalars  cql 5000
  https://tensorboard.dev/experiment/oBK1wX31Q7yVjl3mv2jqdg/#scalars  cql 15000
  https://tensorboard.dev/experiment/b9zGYtBJToOZHpH0xlq5xw/#scalars  dqn 5000
  https://tensorboard.dev/experiment/kP6DVgehQ8qqZnNg7y7qug/#scalars  dqn 15000
  
  * Part 2.3 (PointmassMedium)
  https://tensorboard.dev/experiment/7e3Lc0pXQLmm5AjYpBoxgw/#scalars  alpha 0.02
  https://tensorboard.dev/experiment/QHeVZqxGSkOkhEMcwsQ9lQ/#scalars  alpha 0.5
  
  * Part 3
  https://tensorboard.dev/experiment/Ju7LbGrAQ26Ry859IjgF5A/#scalars  hard, cql
  https://tensorboard.dev/experiment/38CqedCOQgCGbyp0Qn4gXA/#scalars  hard, dqn
  
  (Compare to Part 2.1!) 
  https://tensorboard.dev/experiment/Lh3sb2JuQ3CkaqWLF3NCWA/#scalars  medium, cql
  https://tensorboard.dev/experiment/mZ4MLSpUQkmpkvGUvXVBQA/#scalars  medium, dqn

+ Or go to each folder in run_logs folder, try:
```
tensorboard --logdir .
```


## Discuss
* Part 1.1
Compare RND & epsilon-greedy: 
Look at ```curr_state_density.png```. In PointmassEasy environment, both algorithms give nearly uniform distribution of states and states of epsilon-greedy case are little more concentrated near initial state. In PointmassHard environment, both algorithms do not give uniform distribution but get stuck by wall. States of epsilon-greedy case are concentrated in initial state, and States of rnd case are concentrated in corner in the center. 
In hard environment which require some special strategy to get reward, only random action can't bring agent to states with some reward and it seems to be not enough to matching random objective function. We can try 'supervised' version, which is used in practice. In easy environment, random exploration is enough because it doesn't require some special strategy.

* Part 1.2
Compare RND & count-base-algorithm (especially, MBIE-EB):
Look at ```curr_state_density.png``` and  ```eval_last_traj.png```. Although the performance are improved because agent reach goal position now, still states are concentrated in first room. It's because bonus is given once the agent reaches new state. If some new states are very hard to reach without additional prior knowledge, (e.g: distribution over Q-function method), it's nearly impossible to reach that position and never get bonus for that position. I think this is the reason.

* Part 2.1
<compare DQN & CQL>
Does CQL give rise to Q-values that underestimate the Q-values learned via a standard DQN?:
Compared to Q-values learned via DQN, Q-values drop drastically 3 times. It’s because there is some term to lower some large Q-values each states (logsumexp - ‘softmax’) in objective during learning Q parameters. With CQL algorithm, Q-values drops every time the algorithm 'thinks' they get too high.

* Part 2.2
explain effect of num_exploration_steps of CQL & DQN:
Look at learning curve of ```Eval_AverageReturn``` of 'DQN + 15k exploration' case. It doesn't convege yet; Q-function needs to be trained more and it's the reason why it is lower than one of 'DQN + 5k exploration' case. But in CQL case, ```Eval_AverageReturn``` of both 5k & 15k case look similar. It seems CQL algorithm underestimates Q value. 

* Part 2.3
explain effect of alpha of CQL:
alpha 0.02 was better than alpha 0.5. If alpha is too big, it underestimates Q values for (s,a) which was unseen in buffer and overestimates Q values for (s,a) which was seen in buffer. 

* Part 3
How effective compare to 2.1 (hard env) (purely rnd based exploration)?: 
Look at ```curr_state_density.png``` and  ```eval_last_traj.png```. Both CQL & DQN cases show supervised exploration is better (wide-spreaded states over possible states & success reaching goal position). But in 2.1, CQL case does not reach goal position whereas DQN case reaches. It's because alpha=0.1 underestimates Q value for unseen state. Same results are shown in ```Eval_AverageReturn```. Only '2.1 + CQL' performs bad. It performs poor exploration (since rnd is not so good this case) and there are lots of unseen (s,a)s and CQL performs bad (underestimates Q values for the unseen (s,a)s) with big alpha.
