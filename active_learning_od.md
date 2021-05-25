
## Important baselines
- Localization-aware active learning for object detection. Asian Conference on Computer Vision 2018. [[paper](https://arxiv.org/pdf/1801.05124.pdf)][Nonofficial code in Pytorch Detectron2](https://github.com/lolipopshock/Detectron2_AL)
    - Use **localization tightness** and **localization stability** as uncertainty measures
    - Localization tightness: IoU overlap between proposals and final predicted bounding boxes 
    - Localization stability: Consistency in prediction when proposals are perturbed by noises 
     
- Towards human-machine cooperation: Self- supervised sample mining for object detection. CVPR 2018. [[paper](https://arxiv.org/pdf/1803.09867.pdf)][[code in Pytorch](https://github.com/yanxp/SSM-Pytorch)] **SSM**
   - Use **cross-image consistency** (crop and paste) + classification confidence to measure uncertainty
   - Leverage both high-consistency examples (trust the model's prediction as label) and low-consistency examples (pseudo-label) to complement the traditional uncertainty approach which only focus on high-uncertainty examples 

- Consistency-based Semi-supervised Learning for Object Detection. arxiv, 2019. [[paper](https://openreview.net/pdf?id=BkgHgrSxIr)][[code](https://github.com/soo89/CSD-SSD)]
   - Compute the **consistency in prediction after horizontal flip**: Horizontal flipped image should get symmetric prediction 

- Contextual Diversity for Active Learning. ECCV 2020 [[paper](https://arxiv.org/pdf/2008.05723.pdf)][[code in Pytorch](https://github.com/sharat29ag/CDAL)] **CDAL**
  - Based on both uncertainty and diversity. It tries to **select samples with different class confusion** (distribution of prediction confidence is different) to enrich the contextual diversity
   - It implements different selection strategies: CDAL+Core-Set, CDAL+RL, Contextual Diversity, Visual representation, Semantic representation
   
- Multi-instance Active Learning for Object Detection. arxiv. 2021. [[paper](https://arxiv.org/pdf/2104.02324.pdf)][[code](https://github.com/yuantn/MI-AOD)] **MIAOD**
   - Design **instance uncertainty learning** module which introduce two adversarial classifiers and measure their agreement, training is min-max game
   - Design **instance uncertainty reweighting** module, since simply summing/averaging pixel uncertainty into image uncertainty is too coarse, we need to effectively eliminate those noisy instances 

## Task-agnostic baseline
   
- Learning Loss for Active Learning. CVPR 2019. [[paper](https://arxiv.org/pdf/1905.03677.pdf)][[code in Pytorch](https://github.com/Mephisto405/Learning-Loss-for-Active-Learning)]
   - Directly predict the loss, those samples with high loss are considered as uncertain, something like hard sample mining 
   
## For reference

- Cost-effective Object Detection: Active Sample Mining with Switchable Selection Criteria.  IEEE transactions on neural networks and learning systems, 2018. [[paper](https://arxiv.org/pdf/1807.00147.pdf)][[code in Pytorch](https://github.com/yanxp/ASM-Pytorch)]
   - This is the paper before **SSM**

- Active learning for deep detection network. ICCV 2019 [[paper](https://arxiv.org/pdf/1911.09168.pdf)][[code in Tensorflow](https://gitlab.com/haghdam/deep_active_learning/-/tree/master)]
   - Use **consistency of pixel's objectiveness with respect to its neighborhood pixels** as uncertainty measure. The formula is very similar to **BALD**, taking the difference between entropy of average and average entropy. 
   - Uncertainty for a image is the average of max-pooled scores

- Scalable Active Learning for Object Detection. arxiv. 2020. [[paper](https://arxiv.org/pdf/2004.04699.pdf)] No code
   - Scoring function: entropy at position p of class c (on objectness map), mutual information of E ensemble models, gradient of output layer, bounding box with confidence
   - Sampling strategy: k-means++, coreset, sparse-modelling


| Paper  | Dataset | Model |
| ------------- | ------------- | ------------- |
| Localization-aware  | PASCAL 2012, PASCAL 2007, MS COCO | Faster-RCNN, SSD |
| SSM  | PASCAL 2012, PASCAL 2007, MS COCO | Faster R-CNN, R-FCN |
| Consistency-based | PASCAL VOC, MSCOCO | SSD, R-FCN |
| CDAL | PASCAL VOC 2007 and 2012 | SSD |
| MIAOD | PASCAL 2012, PASCAL 2007, MS COCO | RetinaNet, SSD |
| LL4AL | PASCAL VOC 2007 and 2012 | SSD |
