---
layout: post
title:  "Object Detection 背景和发展过程"      
category: notes
author: "孟文霞"

---


## CNN卷积方式
神经网络的基础入门和卷积的基本方式参考台湾大学李宏毅教授的讲义：[[deep learning.pdf]](/images/blog/2017-3-21/deep learning.pdf)    
卷积的动态过程见cs231n的一个动态图：[[http://cs231n.github.io/assets/conv-demo/index.html]](http://cs231n.github.io/assets/conv-demo/index.html)    

### 注意
* 卷积过程中Filter的层数与原数据层数相同
* Polling的方式可以max、average or 自己设计其他的方式
* Filter的选取也经历了许多变化的过程，从Alexnet的11×11，到VGG、SSD的3×3
* 卷积的过程也可以使用多核处理，仅在其中的几层进行通讯，见下文的Alexnet

## 常见的网络

## Alexnet
**原文**：[[ImageNet Classification with Deep Convolutional Neural Networks]](http://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)      
    
**摘要**：We trained a large, deep convolutional neural network to classify the 1.2 million
high-resolution images in the ImageNet LSVRC-2010 contest into the 1000 different
classes. On the test data, we achieved top-1 and top-5 error rates of 37.5%
and 17.0% which is considerably better than the previous state-of-the-art. The
neural network, which has 60 million parameters and 650,000 neurons, consists
of five convolutional layers, some of which are followed by max-pooling layers,
and three fully-connected layers with a final 1000-way softmax. To make training
faster, we used non-saturating neurons and a very efficient GPU implementation
of the convolution operation. To reduce overfitting in the fully-connected
layers we employed a recently-developed regularization method called “dropout”
that proved to be very effective. We also entered a variant of this model in the
ILSVRC-2012 competition and achieved a winning top-5 test error rate of 15.3%,
compared to 26.2% achieved by the second-best entry.    


**特点**：使用了GPU和dropout

## VGG   
**原文**：[[VERY DEEP CONVOLUTIONAL NETWORKS FOR LARGE-SCALE IMAGE RECOGNITION]](https://arxiv.org/pdf/1409.1556.pdf)       

**摘要**：In this work we investigate the effect of the convolutional network depth on its
accuracy in the large-scale image recognition setting. Our main contribution is
a thorough evaluation of networks of increasing depth using an architecture with
very small (3×3) convolution filters, which shows that a significant improvement
on the prior-art configurations can be achieved by pushing the depth to 16–19
weight layers. These findings were the basis of our ImageNet Challenge 2014
submission, where our team secured the first and the second places in the localisation
and classification tracks respectively. We also show that our representations
generalise well to other datasets, where they achieve state-of-the-art results. We
have made our two best-performing ConvNet models publicly available to facilitate
further research on the use of deep visual representations in computer vision.     

**特点**：使用了3×3的Filter，卷积的层数增加到16-19。


## GoogLeNet   
**原文**：[[Going Deeper with Convolutions]](http://www.cv-foundation.org/openaccess/content_cvpr_2015/papers/Szegedy_Going_Deeper_With_2015_CVPR_paper.pdf)    

**摘要**：We propose a deep convolutional neural network architecture
codenamed Inception that achieves the new
state of the art for classification and detection in the ImageNet
Large-Scale Visual Recognition Challenge 2014
(ILSVRC14). The main hallmark of this architecture is the
improved utilization of the computing resources inside the
network. By a carefully crafted design, we increased the
depth and width of the network while keeping the computational
budget constant. To optimize quality, the architectural
decisions were based on the Hebbian principle and
the intuition of multi-scale processing. One particular incarnation
used in our submission for ILSVRC14 is called
GoogLeNet, a 22 layers deep network, the quality of which
is assessed in the context of classification and detection.   

**特点**：增加网络的层数(22层)和宽度，使用一组Inception module来进行卷积。Inception module单位如下图：
![googlenet1](/images/blog/2017-3-21/Googlenet1.png)    
最终搭建好的结构如下图：
![Googlenet2](/images/blog/2017-3-21/Googlenet2.png)

## ResNet   
**原文**：[[Deep Residual Learning for Image Recognition]](https://arxiv.org/pdf/1512.03385.pdf)    

**摘要**：Deeper neural networks are more difficult to train. We
present a residual learning framework to ease the training
of networks that are substantially deeper than those used
previously. We explicitly reformulate the layers as learning
residual functions with reference to the layer inputs, instead
of learning unreferenced functions. We provide comprehensive
empirical evidence showing that these residual
networks are easier to optimize, and can gain accuracy from
considerably increased depth. On the ImageNet dataset we
evaluate residual nets with a depth of up to 152 layers—8×
deeper than VGG nets but still having lower complexity.
An ensemble of these residual nets achieves 3.57% error
on the ImageNet test set. This result won the 1st place on the
ILSVRC 2015 classification task. We also present analysis
on CIFAR-10 with 100 and 1000 layers.       
The depth of representations is of central importance
for many visual recognition tasks. Solely due to our extremely
deep representations, we obtain a 28% relative improvement
on the COCO object detection dataset. Deep
residual nets are foundations of our submissions to ILSVRC
& COCO 2015 competitions1
, where we also won the 1st
places on the tasks of ImageNet detection, ImageNet localization,
COCO detection, and COCO segmentation.    

**特点**：解决了Deeper neural networks难以训练的问题。

## Object Detection
Object Detection主要解决的问题是What and Where：   
![1](/images/blog/2017-3-21/1.png)
Object Detection的常见算法可以见高伟毅师兄整理的笔记[[https://gwyve.github.io/]](https://gwyve.github.io/)    
    
附上krosaen的GitHub上的Deep Learning Papers Reading Roadmap 中Object Detection部分:[[原文地址]](https://github.com/songrotek/Deep-Learning-Papers-Reading-Roadmap/blob/master/README.md)

**[1]** Szegedy, Christian, Alexander Toshev, and Dumitru Erhan. "**Deep neural networks for object detection**." Advances in Neural Information Processing Systems. 2013. [[pdf]](http://papers.nips.cc/paper/5207-deep-neural-networks-for-object-detection.pdf)   

**[2]** Girshick, Ross, et al. "**Rich feature hierarchies for accurate object detection and semantic segmentation**." Proceedings of the IEEE conference on computer vision and pattern recognition. 2014. [[pdf]](http://www.cv-foundation.org/openaccess/content_cvpr_2014/papers/Girshick_Rich_Feature_Hierarchies_2014_CVPR_paper.pdf) **(RCNN)**   

**[3]** He, Kaiming, et al. "**Spatial pyramid pooling in deep convolutional networks for visual recognition**." European Conference on Computer Vision. Springer International Publishing, 2014. [[pdf]](http://arxiv.org/pdf/1406.4729) **(SPPNet)**  

**[4]** Girshick, Ross. "**Fast r-cnn**." Proceedings of the IEEE International Conference on Computer Vision. 2015. [[pdf]](https://pdfs.semanticscholar.org/8f67/64a59f0d17081f2a2a9d06f4ed1cdea1a0ad.pdf)   
**[5]** Ren, Shaoqing, et al. "**Faster R-CNN: Towards real-time object detection with region proposal networks**." Advances in neural information processing systems. 2015. [[pdf]](http://papers.nips.cc/paper/5638-analysis-of-variational-bayesian-latent-dirichlet-allocation-weaker-sparsity-than-map.pdf)  

**[6]** Redmon, Joseph, et al. "**You only look once: Unified, real-time object detection**." arXiv preprint arXiv:1506.02640 (2015). [[pdf]](http://homes.cs.washington.edu/~ali/papers/YOLO.pdf) **(YOLO,Oustanding Work, really practical)**   

**[7]** Liu, Wei, et al. "**SSD: Single Shot MultiBox Detector**." arXiv preprint arXiv:1512.02325 (2015). [[pdf]](http://arxiv.org/pdf/1512.02325)   

**[8]** Dai, Jifeng, et al. "**R-FCN: Object Detection via
Region-based Fully Convolutional Networks**." arXiv preprint arXiv:1605.06409 (2016). [[pdf]](https://arxiv.org/abs/1605.06409)   


