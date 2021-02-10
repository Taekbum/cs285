## How to run

```
cd <path to hw3 folder>
```

1. For 1, run
```
python cs285/scripts/run_hw3_dqn.py --env_name MsPacman-v0 --exp_name q1
```

2. For 2, run
```
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q2_dqn_1 --seed 1
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q2_dqn_2 --seed 2
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q2_dqn_3 --seed 3
```
```
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q2_doubledqn_1 --double_q --seed 1
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q2_doubledqn_2 --double_q --seed 2
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q2_doubledqn_3 --double_q --seed 3
```

3. For 3, run
```
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q3_hparam1 --batch_size 16
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q3_hparam2 --batch_size 64
python cs285/scripts/run_hw3_dqn.py --env_name LunarLander-v3 --exp_name q3_hparam3 --batch_size 128
```

4. For 4, run
```
python run_hw3_actor_critic.py --env_name CartPole-v0 -n 100 -b 1000 --exp_name q4_ac_1_1 -ntu 1 -ngsptu 1
python run_hw3_actor_critic.py --env_name CartPole-v0 -n 100 -b 1000 --exp_name q4_100_1 -ntu 100 -ngsptu 1
python run_hw3_actor_critic.py --env_name CartPole-v0 -n 100 -b 1000 --exp_name q4_1_100 -ntu 1 -ngsptu 100
python run_hw3_actor_critic.py --env_name CartPole-v0 -n 100 -b 1000 --exp_name q4_10_10 -ntu 10 -ngsptu 10
```

5. From 4, best setting was ntu 10, nsptu 10. So, run
```
python run_hw3_actor_critic.py --env_name InvertedPendulum-v2 --ep_len 1000 --discount 0.95 -n 100 -l 2 -s 64 -b 5000 -lr 0.01 --exp_name q5_10_10 -ntu 10 -ngsptu 10
python run_hw3_actor_critic.py --env_name HalfCheetah-v2 --ep_len 150 --discount 0.90 --scalar_log_freq 1 -n 150 -l 2 -s 32 -b 30000 -eb 1500 -lr 0.02 --exp_name q5_10_10 -ntu 10 -ngsptu 10
```

## Results
+ You can see results of each experiments in tensorboard. Just click these urls.
	* 1 (Pac-Man)
	

	* 2 (LunarLander)
	(DQN)
  	https://tensorboard.dev/experiment/qRTMTXPVSRqDRZlEb3pLsQ/#scalars  seed 1
  	https://tensorboard.dev/experiment/x8XykEq6RQ6Jx68DxB1eaw/#scalars  seed 2
  	https://tensorboard.dev/experiment/DFo7qwmcQ9m3kyTX3ipzrA/#scalars  seed 3
  
    (Double DQN)
   	https://tensorboard.dev/experiment/N0AulkJ6SqWraXIB2PO77Q/#scalars  seed 1
	https://tensorboard.dev/experiment/otjOHj0zRz22ZM68cvQVfQ/#scalars  seed 2
	https://tensorboard.dev/experiment/yaIVdbHeTlq2vOYb6yDdUw/#scalars  seed 3
    
    

	* 3 (LunarLander)
	https://tensorboard.dev/experiment/vpLCY444RwOqxGL06T41Ag/#scalars batch 16
	https://tensorboard.dev/experiment/uwwV3AsRS7mxZzxnpHXJzQ/#scalars batch 64
	https://tensorboard.dev/experiment/Etd90rBzT0WsgU4Mh5gJoA/#scalars batch 128
  
  * 4 (CartPole)
  	https://tensorboard.dev/experiment/3Ny9OyHvT0Cys7cOj5UyCA/#scalars  ntu 1 ngsptu 100
  	https://tensorboard.dev/experiment/7gjbRAqJQSyeXt0KXyzEiw/#scalars  ntu 100 ngsptu 1
  	https://tensorboard.dev/experiment/J0N5V6AjQMy3U8kOGnvwQA/#scalars  ntu 10 ngsptu 10
  	ntu (target updates per each sampled batch) 10 & ngsptu (gradient steps per each target update) 10 is best.
  
  	* 5 
 	https://tensorboard.dev/experiment/lCARrd2ZTluKbdgGeyz4uA/#scalars  (Inverted Pendulum)
  	https://tensorboard.dev/experiment/t7MJ0JWYQ7ajRPvFoBoFog/#scalars  (Half Cheetah)

+ Or go to each folder in run_logs folder, try:
```
tensorboard --logdir .
```
You can see video of DQN for Pac-Man by this way.


## Discuss
* 2
Compare Double DQN to vanila DQN:
Look at ```Train_AverageReturn```. For all random seed, those of DQN are similar(very low) to each other. With same seed, those of DDQN are much higher than those of DQN. But their values very differ to each other seed in DDQN case. I think it's because decorrelation between noise of current network(for action selection) and noise of target network(for evaluation) difers according to random seed.

* 3
effect of batch size: 
Without using DDQN, ```Train_AverageReturn``` is very low regardless of batch size.

* 4
effect of target updates per each sampled batch & gradient steps per each target update:
target updates per each sampled batch: ```ntu``` / gradient steps per each target update: ```ngsptu```
ntu 10 & ngsptu 10 is the best case (reaches maximum 200) but ntu 1 & ngsptu 100 is sufficiently good. ntu 100 & ngsptu 1 is quite bad.
It means that we don't need to update target network very often, and also gradient step 10 is enough.
