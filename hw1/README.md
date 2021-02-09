![Alt Text](http://localhost:6006/data/plugin/images/individualImage?ts=1612883022.3655584&blob_key=WyIiLCJpbWFnZXMiLCIuIiwiZXZhbF9yb2xsb3V0cyIsNSwyXQ)
## How to run

```
cd <path to hw1 folder>
```

1. For 1-(2), run
```
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name bc_ant --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v2.pkl --video_log_freq -1
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/HalfCheetah.pkl --env_name HalfCheetah-v2 --exp_name bc_halfcheetah --n_iter 1 --expert_data cs285/expert_data/expert_data_HalfCheetah-v2.pkl --video_log_freq -1
```

2. For 1-(3), run
```
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name bc_ant_expert_data_100 --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v2.pkl --batch_size 100 --video_log_freq -1
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name bc_ant_grad_per_steps_5000 --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v2.pkl --num_agent_train_steps_per_iter 5000 --video_log_freq -1
```

3. For 2-(2), run
```
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Humanoid.pkl --env_name Humanoid-v2 --exp_name dagger_humanoid --n_iter 10 --do_dagger --expert_data cs285/expert_data/expert_data_Humanoid-v2.pkl --video_log_freq -1
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
