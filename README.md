# GRP-DSOD

We have released the [GRP-DSOD](https://arxiv.org/abs/1712.00886) code in https://github.com/szq0214/DSOD. Check out the [pycaffe code](https://github.com/szq0214/DSOD) there if you would like to reproduce the exact same results as in the paper.

In this repository, we are planning to release a pytorch version of [DSOD](https://arxiv.org/abs/1708.01241) and [GRP-DSOD](https://arxiv.org/abs/1712.00886) - stay tuned!

**We also see some very promising results on the PASCAL VOC Comp3 [Leaderboard](http://host.robots.ox.ac.uk:8080/leaderboard/displaylb.php?challengeid=11&compid=3), like https://github.com/kuangliu/torchcv. Unfortunately, they used the ImageNet pre-trained models as the initialized parameters (https://github.com/kuangliu/torchcv/issues/11). Please note that the Comp3 Challenge only allows to use the VOC12 dataset for training (without the pre-trained models). Please check your training process carefully.**

If you find this helps your research, please cite:

    @article{shen2017learning,
         title={Learning Object Detectors from Scratch with Gated Recurrent Feature Pyramids},
         author={Shen, Zhiqiang and Shi, Honghui and Feris, Rogerio and Cao, Liangliang and Yan, Shuicheng and Liu, Ding and Wang, Xinchao and Xue, Xiangyang and Huang, Thomas S},
         journal={arXiv preprint arXiv:1712.00886},
         year={2017}
    }

## Introduction

In GRP-DSOD, we propose a recurrent feature-pyramid structure to squeeze rich spatial and semantic features into a single prediction layer that further reduces the number of parameters to learn (DSOD need learn 1/2, but GRP-DSOD need only 1/3). Thus our new model is more fit for learning from scratch, and can converge faster than DSOD. 
We also introduce a novel gate-controlled prediction strategy in GRP-DSOD to adaptively enhance or attenuate feature activations at different scales based on the input object size.

<div align=center>
<img src="https://user-images.githubusercontent.com/3794909/36568688-8d176d42-17f0-11e8-85d6-054d90ed5bfc.jpg" width="640">
</div>

<div align=center>
Figure 1: Illustration of the motivation of GRP-DSOD.
</div> 

<div align=center>
<img src="https://user-images.githubusercontent.com/3794909/36566300-ad4d9c2e-17e8-11e8-9808-a4c3602d21b1.jpg" width="740">
</div>

<div align=center>
Figure 2: An overview of GRP-DSOD together with three one-stage detector methods.
</div> 

## Visualization

0. Visualizations of network structures (tools from [ethereon](http://ethereon.github.io/netscope/quickstart.html), please ignore the warning messages):
	- [DSOD] (http://ethereon.github.io/netscope/#/gist/b17d01f3131e2a60f9057b5d3eb9e04d)
	- [GRP-DSOD] (http://ethereon.github.io/netscope/#/gist/4dcd890cb38a7f3c55a51dc1d67068a9)


## Results & Models

The tables below show the results on PASCAL VOC 2007, 2012 and 2012 Comp3 (training on VOC 2012 only).

PASCAL VOC test results:

| Method | VOC 2007 test *mAP* | # params | Models 
|:-------|:-----:|:-------:|:-------:|
| GRP-DSOD300 (07+12) | 78.5 | 14.1M | [Download (56.5M)](https://drive.google.com/open?id=1LuAAlFffE3K26oyg_5WURT25hiLwMYdn) |
| GRP-DSOD320 (07+12) | 78.7 | 14.2M | [Download (56.8M)](https://drive.google.com/open?id=1HffxFdGPf-W92UKED4QZn9V66OgZr9LK) |
| GRP-DSOD320* (07+12) | 79.0 | 16.0M | [Download (63.9M)](https://drive.google.com/open?id=1NV236RkPMK2XLlsoIcWPvvAsTz9-qTOA) |


| Method | VOC 2012 test *mAP* | # params| Models 
|:-------|:-----:|:-------:|:-------:|
| GRP-DSOD320* (12) | 72.5 （VOC Comp3） | 16.0M | [Download (63.9M)](https://drive.google.com/open?id=1uMcMqVxiLK7M2BMWPmfi82jglyZssFbB) |
| GRP-DSOD320 (07++12) | 77.0 | 14.2M | [Download (56.8M)](https://drive.google.com/open?id=1CMnvxy4a_GByKKnn7UgEePpUOffIXoxh) |
| GRP-DSOD320* (07++12) | -- | -- | Running |

