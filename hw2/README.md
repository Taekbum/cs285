## Video 
* Implement of Bonus (Walker2d, w/ gae)
in ```cd <path to hw2/run_logs/walker_gae_b10000_r0.005_eval5000_Walker2d-v2_10-02-2021_00-22-35>``` folder, try ```tensorboard --logdir .```. You can see video in IMAGES tab.

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

4. For 4-(1), experiment <b*> = {10000, 30000, 50000}, <r*> = {0.005, 0.01, 0.02}.
```
python cs285/scripts/run_hw2.py --env_name HalfCheetah-v2 --ep_len 150 --discount 0.95 -n 100 -l 2 -s 32 -b <b*> -lr <r*> -rtg --nn_baseline --exp_name q4_search_b<b*>_lr<r*>_rtg_nnbaseline
```

I found <b*>=30000, <r*>=0.02. So, for 4-(2), run
```
python cs285/scripts/run_hw2.py --env_name HalfCheetah-v2 --ep_len 150 --discount 0.95 -n 100 -l 2 -s 32 -b 30000 -lr 0.02 --exp_name q4_b30000_r0.02
python cs285/scripts/run_hw2.py --env_name HalfCheetah-v2 --ep_len 150 --discount 0.95 -n 100 -l 2 -s 32 -b 30000 -lr 0.02 -rtg --exp_name q4_b30000_r0.02_rtg
python cs285/scripts/run_hw2.py --env_name HalfCheetah-v2 --ep_len 150 --discount 0.95 -n 100 -l 2 -s 32 -b 30000 -lr 0.02 --nn_baseline --exp_name q4_b30000_r0.02_nnbaseline
python cs285/scripts/run_hw2.py --env_name HalfCheetah-v2 --ep_len 150 --discount 0.95 -n 100 -l 2 -s 32 -b 30000 -lr 0.02 -rtg --nn_baseline --exp_name q4_b30000_r0.02_rtg_nnbaseline
```

5. For Bonus (implement GAE-lambda), run
```
python cs285/scripts/run_hw2.py --env_name Walker2d-v2 --ep_len 1000 --discount 0.99 --lambda 0.95 -n 100 -l 2 -s 64 -b 10000 -lr 0.005 -rtg --nn_baseline --exp_name walker_gae_b10000_r0.005_eval5000 --eval_batch_size 5000 --use_gae=True
python cs285/scripts/run_hw2.py --env_name Walker2d-v2 --ep_len 1000 --discount 0.99 -n 100 -l 2 -s 64 -b 10000 -lr 0.005 -rtg --nn_baseline --exp_name walker_nogae_b10000_r0.005_eval5000 --eval_batch_size 5000
```

## Results
+ You can see results of each experiments in tensorboard. Just click these urls.
	* 1 (CartPole)
	https://tensorboard.dev/experiment/V7mmHAGpRzWJdkp0pcWT7Q/#scalars  PG w/ batch size: 1000, trajectory-centric reward, and w/o advantage normalization
	https://tensorboard.dev/experiment/ae3212I6T2erGionCls4Cg/#scalars  PG w/ batch size: 1000, reward-to-go, and w/o advantage normalization
	https://tensorboard.dev/experiment/SpDbYG24QBeQ5OYrEwMlZQ/#scalars  PG w/ batch size: 1000, reward-to-go, and advantage normalization

	https://tensorboard.dev/experiment/ViKJNwK8SZaanuYjZvU8Bw/#scalars  PG w/ batch size: 5000, trajectory-centric reward, and w/o advantage normalization
	https://tensorboard.dev/experiment/rpO83rvhQJiOwrBRgG0xGQ/#scalars  PG w/ batch size: 5000, reward-to-go, and w/o advantage normalization
	https://tensorboard.dev/experiment/MkIYlTbcRei9rt0I6Rxo4A/#scalars  PG w/ batch size: 5000, reward-to-go, and advantage normalization

	* 2 (InvertedPendulum)
	https://tensorboard.dev/experiment/iOVlYBQrReOWhAmfoZKBSw/#scalars  default setting
	https://tensorboard.dev/experiment/4npam85fQBet8W5MWmyoig/#scalars  lr 0.008
	https://tensorboard.dev/experiment/zdOGfGXLS7KWpqh5S68K0A/#scalars  lr 0.01
	https://tensorboard.dev/experiment/Y6hrBa7SQRmg2yFaWpg0cQ/#scalars  b 500
	https://tensorboard.dev/experiment/LH4AoTKPR0aZiGe6ElU6XA/#scalars  b 100
	https://tensorboard.dev/experiment/1QK1MwYdRemQA9ZSJR2o9w/#scalars  b 100 lr 0.008 -> this is best case
	https://tensorboard.dev/experiment/gKzRZbPdT26OPkX9ewtv9Q/#scalars  b 100 lr 0.01

	* 3 (LunarLander)
	https://tensorboard.dev/experiment/rOmwMvbdTLOfqKojDguopQ/#scalars  PG w/ baseline
	
	* 4-(1) (HalfCheetah)
	https://tensorboard.dev/experiment/6jhXOZ7JSPS0G9BcxXD5XA/#scalars  b = 30000, lr = 0.02 (best case)
	
	* 4-(2)
	https://tensorboard.dev/experiment/O00yrmD3TpOIdlLo1MiahA/#scalars  w/ trajectory-centric reward & w/o baseline
	https://tensorboard.dev/experiment/YIMoptLuQoOUzS6r9oWs2Q/#scalars  w/ reward-to-go & w/o baseline
	https://tensorboard.dev/experiment/ycMFqw1wRgqqu8D66EyLeA/#scalars  w/ trajectory-centric reward & baseline
	https://tensorboard.dev/experiment/6jhXOZ7JSPS0G9BcxXD5XA/#scalars  w/ reward-to-go & baseline
	
	* Bonus (Walker2d)
	https://tensorboard.dev/experiment/GVq90UAYTOewEqR3DE8p7A/#scalars  w/ gae, lambda = 0.95
	https://tensorboard.dev/experiment/APaH15TYQs2cRiNm6EsyjA/#scalars  w/o gae

+ Or go to each folder in run_logs folder, try:
```
tensorboard --logdir .
```
You can see video in ```walker_gae_b10000_r0.005_eval5000_Walker2d-v2_10-02-2021_00-22-35``` folder (Walker2d, w/ gae) by this way.


## Discuss
* 1
1) Reward_to_go is better than trajectory centric one.
2) Advantage standarization helps.
3) Larger batch size(evaluate objective function with many rollouts at each iteration) helps a lot.

* 4-(2)
Both reward-to-go and baseline are better than default. Using reward-to-go and baseline together is best because they decrease variance of objective of PG.

* Bonus
w/o gae is lambda = 1 case of gae-lambda because hw2 is implementation of REINFORCE algorithm (using sum of actual returns). Performance is variant according to lambda value.

## Plotting your results

We have provided a snippet that may be used for reading your Tensorboard eventfiles in [scripts/read_results.py](cs285/scripts/read_results.py). Reading these eventfiles and plotting them with [matplotlib](https://matplotlib.org/) or [seaborn](https://seaborn.pydata.org/) will produce the cleanest results for your submission. For debugging purposes, we recommend visualizing the Tensorboard logs using `tensorboard --logdir data`.
