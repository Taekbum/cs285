## How to run

```
cd <path to hw1 folder>
```

1. For 1-(2), run
```
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name bc_ant --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v2.pkl --video_log_freq -1
```

2. For 1-(3), run
```
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name bc_ant_expert_data_100 --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v2.pkl --batch_size 100 --video_log_freq -1
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name bc_ant_grad_per_steps_5000 --n_iter 1 --expert_data cs285/expert_data/expert_data_Ant-v2.pkl --num_agent_train_steps_per_iter 5000 --video_log_freq -1
```

3. For 2-(2), run
```
python cs285/scripts/run_hw1.py --expert_policy_file cs285/policies/experts/Ant.pkl --env_name Ant-v2 --exp_name dagger_ant --n_iter 10 --do_dagger --expert_data cs285/expert_data/expert_data_Ant-v2.pkl --video_log_freq -1
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


# How To DO
## Setup
You can run this code on your own machine or on Google Colab. 

1. **Local option:** If you choose to run locally, you will need to install MuJoCo and some Python packages; see [installation.md](installation.md) for instructions.
2. **Colab:** The first few sections of the notebook will install all required dependencies. You can try out the Colab option by clicking the badge below:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/berkeleydeeprlcourse/homework_fall2020/blob/master/hw1/cs285/scripts/run_hw1.ipynb)

## Complete the code

Fill in sections marked with `TODO`. In particular, see
 - [infrastructure/rl_trainer.py](cs285/infrastructure/rl_trainer.py)
 - [policies/MLP_policy.py](cs285/policies/MLP_policy.py)
 - [infrastructure/replay_buffer.py](cs285/infrastructure/replay_buffer.py)
 - [infrastructure/utils.py](cs285/infrastructure/utils.py)
 - [infrastructure/pytorch_util.py](cs285/infrastructure/pytorch_util.py)

Look for sections maked with `HW1` to see how the edits you make will be used.
Some other files that you may find relevant
 - [scripts/run_hw1.py](cs285/scripts/run_hw1.py) (if running locally) or [scripts/run_hw1.ipynb](cs285/scripts/run_hw1.ipynb) (if running on Colab)
 - [agents/bc_agent.py](cs285/agents/bc_agent.py)

See the homework pdf for more details.

## Run the code

Tip: While debugging, you probably want to keep the flag `--video_log_freq -1` which will disable video logging and speed up the experiment. However, feel free to remove it to save videos of your awesome policy!

If running on Colab, adjust the `#@params` in the `Args` class according to the commmand line arguments above.

### Section 1 (Behavior Cloning)
Command for problem 1:

```
python cs285/scripts/run_hw1.py \
	--expert_policy_file cs285/policies/experts/Ant.pkl \
	--env_name Ant-v2 --exp_name bc_ant --n_iter 1 \
	--expert_data cs285/expert_data/expert_data_Ant-v2.pkl
	--video_log_freq -1
```

Make sure to also try another environment.
See the homework PDF for more details on what else you need to run.
To generate videos of the policy, remove the `--video_log_freq -1` flag.

### Section 2 (DAgger)
Command for section 1:
(Note the `--do_dagger` flag, and the higher value for `n_iter`)

```
python cs285/scripts/run_hw1.py \
    --expert_policy_file cs285/policies/experts/Ant.pkl \
    --env_name Ant-v2 --exp_name dagger_ant --n_iter 10 \
    --do_dagger --expert_data cs285/expert_data/expert_data_Ant-v2.pkl \
	--video_log_freq -1
```

Make sure to also try another environment.
See the homework PDF for more details on what else you need to run.

## Visualization the saved tensorboard event file:

You can visualize your runs using tensorboard:
```
tensorboard --logdir data
```

You will see scalar summaries as well as videos of your trained policies (in the 'images' tab).

You can choose to visualize specific runs with a comma-separated list:
```
tensorboard --logdir data/run1,data/run2,data/run3...
```

If running on Colab, you will be using the `%tensorboard` [line magic](https://ipython.readthedocs.io/en/stable/interactive/magics.html) to do the same thing; see the [notebook](cs285/scripts/run_hw1.ipynb) for more details.

