# GFR-DSOD

We have also merged our [GFR-DSOD](https://bmvc2019.org/wp-content/uploads/papers/0663-paper.pdf) code here into the DSOD repo at https://github.com/szq0214/DSOD. Check it out there if you interested in DSOD.


**We also see some very promising results on the PASCAL VOC Comp3 [Leaderboard](http://host.robots.ox.ac.uk:8080/leaderboard/displaylb.php?challengeid=11&compid=3), like https://github.com/kuangliu/torchcv. While we found they still used the ImageNet pre-trained models as the initialized parameters (https://github.com/kuangliu/torchcv/issues/11). Please note that the Comp3 Challenge only allows to use the VOC12 dataset for training (without the pre-trained models). Please check your training process carefully.**

If you find this helps your research, please consider citing:

    @inproceedings{shenimproving,
         title={Improving Object Detection from Scratch via Gated Feature Reuse},
         author={Shen, Zhiqiang and Shi, Honghui and Yu, Jiahui and Phan, Hai and Feris, Rogerio and Cao, Liangliang and Liu, Ding and Wang, Xinchao and Huang, Thomas and Savvides, Marios}
         booktitle={The British Machine Vision Conference (BMVC)},
         year={2019}


## Introduction

In GFR-DSOD, we propose a recurrent feature-pyramid structure to squeeze rich spatial and semantic features into a single prediction layer that further reduces the number of parameters to learn (DSOD need learn 1/2, but GFR-DSOD need only 1/3). Thus our new model is more fit for learning from scratch, and can converge faster than DSOD. 
We also introduce a novel gate-controlled prediction strategy in GFR-DSOD to adaptively enhance or attenuate feature activations at different scales based on the input object size.

<div align=center>
<img src="https://user-images.githubusercontent.com/3794909/36568688-8d176d42-17f0-11e8-85d6-054d90ed5bfc.jpg" width="580">
</div>

<div align=center>
Figure 1: Illustration of the motivation of GFR-DSOD.
</div> 

<div align=center>
<img src="https://user-images.githubusercontent.com/3794909/36566300-ad4d9c2e-17e8-11e8-9808-a4c3602d21b1.jpg" width="740">
</div>

<div align=center>
Figure 2: An overview of GFR-DSOD together with three one-stage detector methods.
</div> 

## Visualization

0. Visualizations of network structures (tools from [ethereon](http://ethereon.github.io/netscope/quickstart.html), please ignore the warning messages):
	- [DSOD] (http://ethereon.github.io/netscope/#/gist/b17d01f3131e2a60f9057b5d3eb9e04d)
	- [GFR-DSOD] (http://ethereon.github.io/netscope/#/gist/4dcd890cb38a7f3c55a51dc1d67068a9)


## Results & Models

Our PASCAL VOC LMDB files:
	
| Method | LMDBs
|:-------|:-----:|
| Train on VOC07+12 and test on VOC07  | [Download](https://drive.google.com/open?id=1u6ngM9hEZabT2HyvzPdWpGgVTofD6jQ3) |
| Train on VOC07++12 and test on VOC12 (Comp4)  | [Download](https://drive.google.com/open?id=1J2epI4zDFptw1RdpHAl0Z_Sphs14OtIE) |
| Train on VOC12 and test on VOC12 (Comp3)  | [Download](https://drive.google.com/open?id=1r5DI3tVGXPYyKGAmBawKGkgROJQyh5i-) |

The tables below show the results on PASCAL VOC 2007, 2012 and 2012 Comp3 (training on VOC 2012 only).

PASCAL VOC test results:

| Method | VOC 2007 test *mAP* | # params | Models 
|:-------|:-----:|:-------:|:-------:|
| GFR-DSOD300 (07+12) | 78.5 | 14.1M | [Download (56.5M)](https://drive.google.com/open?id=1LuAAlFffE3K26oyg_5WURT25hiLwMYdn) |
| GFR-DSOD320 (07+12) | 78.7 | 14.2M | [Download (56.8M)](https://drive.google.com/open?id=1HffxFdGPf-W92UKED4QZn9V66OgZr9LK) |
| GFR-DSOD320* (07+12) | 79.0 | 16.0M | [Download (63.9M)](https://drive.google.com/open?id=1NV236RkPMK2XLlsoIcWPvvAsTz9-qTOA) |


| Method | VOC 2012 test *mAP* | # params| Models 
|:-------|:-----:|:-------:|:-------:|
| GFR-DSOD320* (12) | 72.5 （VOC Comp3） | 16.0M | [Download (63.9M)](https://drive.google.com/open?id=1uMcMqVxiLK7M2BMWPmfi82jglyZssFbB) |
| GFR-DSOD320 (07++12) | 77.0 | 14.2M | [Download (56.8M)](https://drive.google.com/open?id=1CMnvxy4a_GByKKnn7UgEePpUOffIXoxh) |
| GFR-DSOD320* (07++12) | -- | -- | -- |

## Contact

Zhiqiang Shen (zhiqiangshen0214 at gmail.com) 

Any comments or suggestions are welcome!
