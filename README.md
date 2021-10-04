# Transfer SAC
This is the SAC code of ICLR 2022 submission 'Transfer RL across Observation Feature Spaces via Model-Based Regularization'.

The code is based on [a pytorch SAC implementation](https://github.com/pranz24/pytorch-soft-actor-critic).

- Train the dynamics model and the reward model on source tasks:
```bash
CUDA_VISIBLE_DEVICES=0 python main_easy.py --env_name 'HalfCheetah-v3' --num_epoch 300 --exp_log_name exp_source_halfcheetah_0.txt
```
