## Video 
* Implement of 2 (obstacles)
in ```cd <path to hw4/run_logs/hw4_q2_obstacles_singleiteration_obstacles-cs285-v0_08-02-2021_19-39-29>``` folder, try ```tensorboard --logdir .```. 
You can see video in IMAGES tab.


## How to run

```
cd <path to hw4 folder>
```

1. For 1, run
```
python cs285/scripts/run_hw4_mb.py --exp_name q1_cheetah_n500_arch1x32 --env_name cheetah-cs285-v0 --add_sl_noise --n_iter 1 --batch_size_initial 20000 --num_agent_train_steps_per_iter 500 --n_layers 1 --size 32 --scalar_log_freq -1 --video_log_freq -1
python cs285/scripts/run_hw4_mb.py --exp_name q1_cheetah_n5_arch2x250 --env_name cheetah-cs285-v0 --add_sl_noise --n_iter 1 --batch_size_initial 20000 --num_agent_train_steps_per_iter 5 --n_layers 2 --size 250 --scalar_log_freq -1 --video_log_freq -1
python cs285/scripts/run_hw4_mb.py --exp_name q1_cheetah_n500_arch2x250 --env_name cheetah-cs285-v0 --add_sl_noise --n_iter 1 --batch_size_initial 20000 --num_agent_train_steps_per_iter 500 --n_layers 2 --size 250 --scalar_log_freq -1 --video_log_freq -1
```

2. For 2, run
```
python cs285/scripts/run_hw4_mb.py --exp_name q2_obstacles_singleiteration --env_name obstacles-cs285-v0 --add_sl_noise --num_agent_train_steps_per_iter 20 --n_iter 1 --batch_size_initial 5000 --batch_size 1000 --mpc_horizon 10
```

3. For 3, run
```
python cs285/scripts/run_hw4_mb.py --exp_name q3_obstacles --env_nameobstacles-cs285-v0 --add_sl_noise --num_agent_train_steps_per_iter 20 --batch_size_initial 5000 --batch_size 1000 --mpc_horizon 10 --n_iter 12
python cs285/scripts/run_hw4_mb.py --exp_name q3_reacher --env_name reacher-cs285-v0 --add_sl_noise --mpc_horizon 10 --num_agent_train_steps_per_iter 1000 --batch_size_initial 5000 --batch_size 5000 --n_iter 15
python cs285/scripts/run_hw4_mb.py --exp_name q3_cheetah --env_name cheetah-cs285-v0 --mpc_horizon 15 --add_sl_noise --num_agent_train_steps_per_iter 1500 --batch_size_initial 5000 --batch_size 5000 --n_iter 20
```

4. For 4, run
```
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_horizon5 --env_name reacher-cs285-v0 --add_sl_noise --mpc_horizon 5 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_horizon15 --env_name reacher-cs285-v0 --add_sl_noise --mpc_horizon 15 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_horizon30 --env_name reacher-cs285-v0 --add_sl_noise --mpc_horizon 30 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15
```
```
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_numseq100 --env_name reacher-cs285-v0 --add_sl_noise --mpc_horizon 10 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15 --mpc_num_action_sequences 100
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_numseq1000 --env_name reacher-cs285-v0 --add_sl_noise --mpc_horizon 10 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15 --mpc_num_action_sequences 1000
```
```
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_ensemble1 --env_name reacher-cs285-v0 --ensemble_size 1 --add_sl_noise --mpc_horizon 10 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_ensemble3 --env_name reacher-cs285-v0 --ensemble_size 3 --add_sl_noise --mpc_horizon 10 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15
python cs285/scripts/run_hw4_mb.py --exp_name q4_reacher_ensemble5 --env_name reacher-cs285-v0 --ensemble_size 5 --add_sl_noise --mpc_horizon 10 --num_agent_train_steps_per_iter 1000 --batch_size 800 --n_iter 15
```


## Results
+ You can see results of each experiments in tensorboard. Just click these urls.
	* 1 (cheetah) 
	
	
	
	
	
	
	<img src="https://user-images.githubusercontent.com/53718808/107408132-e2673300-6b4d-11eb-8fe8-08839666df81.png"  width="300" height="225"> <img src="https://user-images.githubusercontent.com/53718808/107408149-ebf09b00-6b4d-11eb-9243-71bb8bacec22.png"  width="300" height="225">
	
	<img src="https://user-images.githubusercontent.com/53718808/107408200-fca11100-6b4d-11eb-9c55-9368e1e1c2fe.png"  width="300" height="225"> <img src="https://user-images.githubusercontent.com/53718808/107408211-00349800-6b4e-11eb-87ca-238012600f28.png"  width="300" height="225">
	
	<img src="https://user-images.githubusercontent.com/53718808/107408233-088cd300-6b4e-11eb-8924-8a44e759dae3.png"  width="300" height="225"> <img src="https://user-images.githubusercontent.com/53718808/107408237-0b87c380-6b4e-11eb-865c-63c5c354986d.png"  width="300" height="225">
	
	order: (n_layer 1, hidden_size 32, train_steps_per_iter 500) - (n_layer 2, hidden_size 250, train_steps_per_iter 5) - (n_layer 2, hidden_size 250, train_steps_per_iter 500)

	* 2 (obstacles)
	https://tensorboard.dev/experiment/QETGxs8rSgi1PBTNAeu8OQ/#scalars  MBRL ver 1.5 (plan w/ MPC)
  
	* 3 
	https://tensorboard.dev/experiment/BQEelK3kRxu4LzQkwpToGA/#scalars  (obstacles)
  	https://tensorboard.dev/experiment/1ptrFPOPRg2qoKbDjsEh4Q/#scalars  (reacher)
  	https://tensorboard.dev/experiment/UoEarQvQTYujYXy0JW02wA/#scalars  (cheetah)
  
  * 4 (reacher)
  [mpc horizon]
  https://tensorboard.dev/experiment/8iOyldbgQdq8P8wlN0HLLQ/#scalars  5
  https://tensorboard.dev/experiment/ANvU8xSrSKeopPf2cRwSrQ/#scalars  15
  https://tensorboard.dev/experiment/gZjpzOR5S5K0sAJvEHntjg/#scalars  30

  [# of random action sequence]
  https://tensorboard.dev/experiment/D4zJd4lVTWOJcOSv1B6pzw/#scalars  100
  https://tensorboard.dev/experiment/eXcXMYpVQRyY9wJ57P7hgQ/#scalars  1000

  [# of model ensemble]
  https://tensorboard.dev/experiment/oRWDBxDpQ5yvimzbwsP8pQ/#scalars  1
  https://tensorboard.dev/experiment/FMFxZOwoR6Koipp7K30mrQ/#scalars  3
  https://tensorboard.dev/experiment/erOnnWh4Q9mHZr419AcbHw/#scalars  5

+ Or go to each folder in run_logs folder, try:
```
tensorboard --logdir .
```
You can see video of obstacle by this way.


## Discuss
* 1
effect of network architecture(# of layers & hidden layer size) & model training amount:
Training loss decreases faster and MPE is smaller at evaluation stage as model network gets more layers and bigger hidden layers. If input states are pictures, we should use some sophisticated CNN as model network.

* 4
effect of model ensemble size, number of candidate action sequences, and planning horizon:

- planning horizon: Horizon 15 is slightly better than 5, and 30 was worst. It's because horizon 30 is so big that MPC conserns unnecessary far future and it even worsen decision for near future. If horizon is too small, agent will be trained slowly because it can't fix mistakes immediately. Small horizon is enough because the more replan, the less perfect each individual plan needs to be.
- number of candidate action sequences: With more candidates, agent could train fast. 
- model ensemble size: More model ensembled, better the agent's performance because it reduces model uncertainty by getting 'agree' of multiple models. However, it can be insufficient because we can only learn a few models due to computational complexity. We can try methods estimating model uncertainty such as Bayesian neural networks instead. 
