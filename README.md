# AR_PretrainedModels
Pretrained models for action recognition models

## Summary
This repository supp

このレポジトリでは、動作認識AIを開発してみようという人達のための事前学習モデルを提供している。
以下、モデルアーキテクチャ、事前学習方法、事前学習に用いたデータセット、事前学習モデルの使い方について記す。

Dataset
The dataset for pretraining 
Models are pretrained by the dataset that combined four exsiting datasets for action videos.  They are
* stair actions
* Activitynet
* charades
* subset of Kinetics 700
Toltal number of videos is 348,879.

Codebase
Codes for models and training scripts etc. are based on the codebase “SlowFast” of Meta Research (https://github.com/facebookresearch/SlowFast/tree/main).   
Users have to install first “slowfast” before using pretrained models.

事前学習方式
1. Masked autoencoder
論文：Masked Autoencoders As Spatiotemporal Learners
Paper

2. MaskFeat
論文：Masked Feature Prediction for Self-Supervised Visual Pre-Training
Paper  


How to use pretrained models
1. MAE
   
```
python tools/run_net.py \
  --cfg configs/masked_ssl/4DS_VIT_B_16x4_FT.yaml \ 
  DATA.PATH_TO_DATA_DIR path_to_your_Kinetics_dataset \
  TRAIN.CHECKPOINT_FILE_PATH path_to_your_pretrain_checkpoint
```

2. MaskFeat
```
python tools/run_net.py \
  --cfg configs/masked_ssl/4DS_MVITv2_S_16x4_FT.yaml \
  DATA.PATH_TO_DATA_DIR path_to_your_Kinetics_dataset \
  TRAIN.CHECKPOINT_FILE_PATH path_to_your_pretrain_checkpoint
```

