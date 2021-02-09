## Video 
* Implement of 2-(2)
http://localhost:6006/data/plugin/images/individualImage?ts=1612883022.3655584&blob_key=WyIiLCJpbWFnZXMiLCIuIiwiZXZhbF9yb2xsb3V0cyIsNSwyXQ

## How to run

```
cd <path to hw2 folder>
```

1. For 1, run
```
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 1000 -dsa --exp_name q1_sb_no_rtg_dsa
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 1000 -rtg -dsa --exp_name q1_sb_rtg_dsa
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 1000 -rtg --exp_name q1_sb_rtg_na
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 5000 -dsa --exp_name q1_lb_no_rtg_dsa
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 5000 -rtg -dsa --exp_name q1_lb_rtg_dsa
python cs285/scripts/run_hw2.py --env_name CartPole-v0 -n 100 -b 5000 -rtg --exp_name q1_lb_rtg_na
```

2. For 2, experiment <b*> = {0.005, 0.008, 0.01}, <r*> = {100, 500, 1000}. Default is <b*>=1000, <r*>=0.005
```
python cs285/scripts/run_hw2.py --env_name InvertedPendulum-v2 --ep_len 1000 --discount 0.9 -n 100 -l 2 -s 64 -b <b*> -lr <r*> -rtg --exp_name q2_b<b*>_r<r*>
```

3. For 3, run
```
python cs285/scripts/run_hw2.py --env_name LunarLanderContinuous-v2 --ep_len 1000 --discount 0.99 -n 100 -l 2 -s 64 -b 40000 -lr 0.005 --reward_to_go --nn_baseline --exp_name q3_b40000_r0.005
```

4. For 4, experiment <b> = {10000, 30000, 50000}, <r> = {0.005, 0.01, 0.02}.
```
python cs285/scripts/run_hw2.py --env_name HalfCheetah-v2 --ep_len 150 \
--discount 0.95 -n 100 -l 2 -s 32 -b <b> -lr <r> -rtg --nn_baseline \
--exp_name q4_search_b<b>_lr<r>_rtg_nnbaseline
```
  
## Results
+ You can see results of each experiments in tensorboard. Just click these urls.
	* 1-(2)
	https://tensorboard.dev/experiment/6m5DrrF8Sg69WYVGxxYgvA/#scalars  behavior cloning for Ant
	https://tensorboard.dev/experiment/MKzqDnWxQY6PpCP0Sv61vA/#scalars  behavior cloning for HalfCheetah

	* 1-(3)
	https://tensorboard.dev/experiment/n6qmZIpAQ4uOS6imyB4uMg/#scalars  behavior cloning for Ant, w/ less expert data: 100 (s,a) tuples (default: 1000)
	https://tensorboard.dev/experiment/3bPqzeTqRwGh0DvfQ0qF9A/#scalars  behavior cloning for Ant, w/ more gradient steps in each iteration: 5000 steps 		(default: 1000)

	* 2-(2)
	https://tensorboard.dev/experiment/qwx71P83TZ6jWlIRyXpjtQ/#scalars  DAgger for Humanoid

+ Or go to each folder in run_logs folder, try:
```
tensorboard --logdir .
```
You can see video of behavior cloning for Ant by this way.


## Discuss
* 1-(3)
You can add ```--num_agent_train_steps_per_iter<steps>``` or ```--learning_rate<lr>``` to train your policy more optimally w.r.t to data, ```--n_layers<n_layers>```, ```--size<#of hidden units in each layer>``` or ```--train_batch_size<t_b_s>``` to change policy network architecture (just classification network in hw1),  and ```--batch_size<n_b>``` to get more expert data

* 2-(2)
When you implement dagger, you can get higher performance as iteration increases because p_phi_theta gets closer to p_data as iteration increases.

## Plotting your results

We have provided a snippet that may be used for reading your Tensorboard eventfiles in [scripts/read_results.py](cs285/scripts/read_results.py). Reading these eventfiles and plotting them with [matplotlib](https://matplotlib.org/) or [seaborn](https://seaborn.pydata.org/) will produce the cleanest results for your submission. For debugging purposes, we recommend visualizing the Tensorboard logs using `tensorboard --logdir data`.
