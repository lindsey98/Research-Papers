# Active learning

## survey

- A Survey of Deep Active Learning.(2020)[[paper](https://arxiv.org/abs/2009.00236)]
- From Model-driven to Data-driven: A Survey on Active Deep Learning.(2021)

## membership query synthesis

*generate new samples(adversarial attacks, maybe)*

## stream-based selective sampling

*whether a sample should be queried or not*

##  pool-based selective sampling

*choose samples from an unlabeled pool*

- random sampling

### uncertainty based

- least confident

- entropy

- margin sampling(?

- The power of ensembles for active learning in image classification.(2018). CVPR.[[paper](https://openaccess.thecvf.com/content_cvpr_2018/papers/Beluch_The_Power_of_CVPR_2018_paper.pdf)]

- Learning Loss for Active Learning. (2019).CVPR.[[paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Yoo_Learning_Loss_for_Active_Learning_CVPR_2019_paper.pdf)]

- Deep Bayesian Active Learning with Image Data.(2017).ICML.[[paper](http://proceedings.mlr.press/v70/gal17a/gal17a.pdf)]

  *DBAL*

- Dropout as a Bayesian Approximation: Representing Model Uncertainty in Deep Learning.(2016).ICML.[[paper](http://proceedings.mlr.press/v48/gal16.pdf)]

  *MC dropout*

- State-Relabeling Adversarial Active Learning.(2020).CVPR.[[paper](https://openaccess.thecvf.com/content_CVPR_2020/papers/Zhang_State-Relabeling_Adversarial_Active_Learning_CVPR_2020_paper.pdf)]

### geometric properties

- Adversarial Active Learning for Deep Networks: a Margin Based Approach 

  *DFAL*

- Finding the Homology of Decision Boundaries with Active Learning

- Topological Data Analysis of Decision Boundaries with Application to Model Selection

### diversity based

*increase the diversity of data distribution*

-  Active learning for convolutional neural networks: A core-set approach.(2018).ICLR

  *core-set*

- discriminative active learning.(2019).ICLR(reject)

- Variational Adversarial Active Learning.(2019).ICCV.[[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Sinha_Variational_Adversarial_Active_Learning_ICCV_2019_paper.pdf)]

  *VAAL*
  
-  State-Relabeling Adversarial Active Learning.(2020).CVPR.[[paper](https://openaccess.thecvf.com/content_CVPR_2020/papers/Zhang_State-Relabeling_Adversarial_Active_Learning_CVPR_2020_paper.pdf)]

### hybrid method

- Deep Active Learning: Unified and Principled Method for Query and Training.(2020).AISTATS.[[paper](http://proceedings.mlr.press/v108/shui20a.html)]

  *WAAL*

- Adaptive Active Learning for Image Classification.(2013).CVPR.[[paper](https://www.cv-foundation.org/openaccess/content_cvpr_2013/papers/Li_Adaptive_Active_Learning_2013_CVPR_paper.pdf)]

  

### expected model change

- Active Learning for Speech Recognition: the Power of Gradients

  *EGL, expected gradient length*

SOTA:

SRAAL, LL4AL, VAAL,Core-set,WAAL




# Active learning for object detection
In chronological order: 
- Deep Bayesian Active Learning with Image Data. PMLR 2017 [[paper](http://proceedings.mlr.press/v70/gal17a/gal17a.pdf)]
- Active learning for convolutional neural network: A core-set approach. ICLR 2018 [[paper](https://arxiv.org/pdf/1708.00489.pdf)]
- Active learning for deep detection network. ICCV 2019 [[paper](https://arxiv.org/pdf/1911.09168.pdf)]
- Variational Adversarial Active Learning. ICCV 2019 [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Sinha_Variational_Adversarial_Active_Learning_ICCV_2019_paper.pdf)]
- Learning Loss for Active Learning. CVPR 2019 [[paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Yoo_Learning_Loss_for_Active_Learning_CVPR_2019_paper.pdf)]
- Contextual Diversity for Active Learning. ECCV 2020 [[paper](https://arxiv.org/pdf/2008.05723)]
- Towards Fine-grained Sampling for Active Learning in Object Detection. CVPR 2020 workshop [[paper](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w54/Desai_Towards_Fine-Grained_Sampling_for_Active_Learning_in_Object_Detection_CVPRW_2020_paper.pdf)]

- Multiple Instance Active Learning for Object Detection. arXiv 2021 [[paper](https://arxiv.org/pdf/2104.02324v1.pdf)]
- Consistency-based Active Learning for Object Detection. arXiv 2021 [[paper](https://arxiv.org/pdf/2103.10374.pdf)]





