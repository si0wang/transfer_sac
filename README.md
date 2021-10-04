# Transfer SAC
This is the SAC code of ICLR 2022 submission 'Transfer RL across Observation Feature Spaces via Model-Based Regularization'.

The code is based on [a pytorch SAC implementation](https://github.com/pranz24/pytorch-soft-actor-critic).

To use the target tasks in our paper, please follow the steps in [this document](https://github.com/si0wang/transfer_sac/blob/main/envs/test_env_setup.txt).

## Getting started ###
- Train the dynamics model and the reward model on the source task:
```bash
CUDA_VISIBLE_DEVICES=0 python main_easy.py --env_name 'HalfCheetah-v3' --exp_log_name exp_source_halfcheetah_0.txt
```
- Train SAC on the target task:
```bash
CUDA_VISIBLE_DEVICES=0 python main_hard.py --env_name 'HalfCheetahTest-v3' --exp_log_name exp_target_halfcheetah_0.txt
``` 
- Train SAC with transferred dynamics models on the target task:
```bash
CUDA_VISIBLE_DEVICES=2 python main_hard.py --env_name 'HalfCheetahTest-v3' --exp_log_name exp_transfer_halfcheetah_0.txt --is_transfer True --model_name HalfCheetah-v3-model.pt
``` 
