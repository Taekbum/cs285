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
+ You can see results of each experiments in tensorboard. Just click these urls.
	* Part 1.1 
  (pic)
  https://tensorboard.dev/experiment/80V26O4DRY2oJE0wmfrMmg/#scalars  easy, random
  https://tensorboard.dev/experiment/PsX9BBnET66PlYzjuZsBIw/#scalars  easy, rnd
  https://tensorboard.dev/experiment/xs2eZ6Z9TNyK4RroT30BIQ/#scalars  hard, random
  https://tensorboard.dev/experiment/bD5aVvfJSZa8uk5tnztGmw/#scalars  hard, rnd

	* Part 1.2 
  (pic)
  (count-based-algo.)
  https://tensorboard.dev/experiment/nySmGm6JQ3yUq8Ae8v8fkA/#scalars  medium
  https://tensorboard.dev/experiment/4ns7xeABRAKvN2vJyDx1uA/#scalars  hard
  
	* Part 2.1 (PointmassMedium)
  (pic)
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
  https://tensorboard.dev/experiment/Lh3sb2JuQ3CkaqWLF3NCWA/#scalars  medium, cql
  https://tensorboard.dev/experiment/mZ4MLSpUQkmpkvGUvXVBQA/#scalars  medium, dqn
  
  (Compare to Part 2.1!) 
  https://tensorboard.dev/experiment/Ju7LbGrAQ26Ry859IjgF5A/#scalars  hard, cql
  https://tensorboard.dev/experiment/38CqedCOQgCGbyp0Qn4gXA/#scalars  hard, dqn

+ Or go to each folder in run_logs folder, try:
```
tensorboard --logdir .
```


## Discuss
* Part 1.1
compare RND & epsilon-greedy:

* Part 1.2
compare RND & count-base-algorithm (especially, MBIE-EB) using curr_state_density.png & eval_last_traj.png:

* Part 2.1
compare DQN & CQL:
Does CQL give rise to Q-values that underestimate the Q-values learned via a standard DQN?
With this transformed reward. Is it better or worse? (can be hint)

* Part 2.2
explain effect of num_exploration_steps of CQL & DQN:

* Part 2.3
explain effect of alpha of CQL:

* Part 3
How effective compare to 2.1 (hard env) (purely rnd based exploration)?: 
