# AR_PretrainedModels
### Pretrained models for action recognition models

This repository provides pre-trained models for people who want to develop their own action recognition AI applications.

## Dataset used for pretraining
Models are pretrained by the dataset that combined four exsiting datasets for action videos.  They are
* stair actions
* Activitynet
* charades
* subset of Kinetics 700
Toltal number of videos is 348,879.

## Codebase
Codes for models and training scripts etc. are based on the codebase “SlowFast” of Meta Research (https://github.com/facebookresearch/SlowFast/tree/main).   
Before using pretrained models, users have to first install “slowfast”.

## Pretraining methods
1. MAE (Masked AutoEncoder)
Title: [Masked Autoencoders As Spatiotemporal Learners](https://arxiv.org/abs/2205.09113)

2. MaskFeat
Title: [Masked Feature Prediction for Self-Supervised Visual Pre-Training](https://arxiv.org/abs/2112.09133)

## Pretrained models

1. A model pretrained by MAE for 200 epochs
[DL](https://drive.google.com/file/d/1JwuFBfcK1W7ngOI13bUqIAqSIV1Z8RQF/view?usp=sharing)
2. A model pretrained by MaskFeat for 300 epochs
[DL](https://drive.google.com/file/d/1LDxOrvp-Nvb43dec0s9q9YIsQ3qdQJ09/view?usp=sharing)

## How to use pretrained models
1. MAE
   
```
python tools/run_net.py \
  --cfg configs/masked_ssl/4DS_VIT_B_16x4_FT.yaml
```

2. MaskFeat
```
python tools/run_net.py \
  --cfg configs/masked_ssl/4DS_MVITv2_S_16x4_FT.yaml 
```
In both cases, a user need to specify some fields in the config files such as  ``PATH_TO_DATA_DIR`` and ``CHECKPOINT_FILE_PATH``.
