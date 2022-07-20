---
layout: post
title:  "智能算法在各领域发展概述"      
category: notes
author: "孟文霞"

---

## 概述

随着硬件算力的发展，大规模数据集的出现，智能算法在各行各业都初步崭露头角，当前的智能算法依托某些应用场景，被不同程度的进行实践应用。其中，由于某些领域的数据集较为充分，智能算法这些方向领域发展较快并产生了较为成熟的应用。在高校和企业届发展较快，也是学习研究算法的人员就业方向中最主要的是以下几个：

1. 多模态(MMML,Multimodal Machine Learning):[MMML CMU 2022](https://cmu-multicomp-lab.github.io/mmml-tutorial/schedule/)通过机器学习的方法实现处理和理解多源模态信息的能力；多模态学习从1970年代起步，经历了几个发展阶段，在2010后全面步入Deep Learning阶段；目前比较热门的研究方向是图像、视频、音频、语义之间的多模态学习。
 * 计算机视觉(CV,Computer Vision）：以图像分类为例，算法发展历程为AlexNet、VGG、GoogleNet、ResNet
 * 自然语言处理(NLP,Natural Language Processing)：
 * 语音/音频算法：
2. 搜索/广告/推荐系统：以推荐系统为例，算法发展历程为FM、FFM、[Wide&Deep](https://arxiv.org/pdf/1606.07792.pdf)、DeepFM、[XDeepFM](https://arxiv.org/pdf/1803.05170.pdf)，当前字节整体大框架仍为Deep部分+FM部分，Deep为网络结构，发展为Multihead Attention、lhuc、can，FM为FFM、XDFM，整体来看模型也是趋于复杂化，参数量增多。


**虽然现在各研究方向的模型都变得越来越“大”，参数越来越多，但是模型并不是越大越好，需要针对其应用场景具体分析。例如[ResNet](https://arxiv.org/pdf/1512.03385.pdf)中，针对CIFAR-10数据集19.4M参数1200层的训练结果并没有1.7M个参数110层的网络结构效果好，针对某些小型数据，使用过大的网络反而会出现无法收敛的情况。**不过对于大型数据，例如更多的点击、购买记录，更多的语言素材，更大型的图像视频数据集，使用更多参数的“大”模型是符合我们的直觉的，对此也有不少的学术研究材料。[待补充。]



## CV

## NLP

## 搜广推

## 多模态

## 其他
