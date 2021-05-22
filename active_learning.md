
# Active learning for object detection In chronological order


## Uncertainty based

### Unstructured 
- Least confidence
- Max Margin
- Entropy
- Expected model change
- Gradient length

- Localization-aware active learning for object detection. Asian Conference on Computer Vision 2018. [[paper](https://arxiv.org/pdf/1801.05124.pdf)] No code
    - Use localization tightness and localization stability as uncertainty measures
    - Localization tightness: IoU overlap between proposals and final predicted bounding boxes 
    - Localization stability: Consistency in prediction when proposals are perturbed by noises 
     
- Towards human-machine cooperation: Self- supervised sample mining for object detection. CVPR 2018. [[paper](https://arxiv.org/pdf/1803.09867.pdf)][[code in Pytorch](https://github.com/yanxp/SSM-Pytorch)] **SSM**
   - Use cross-image consistency (crop and paste) + classification confidence to measure uncertainty
   - Leverage both high-consistency examples (trust the model's prediction as label) and low-consistency examples (pseudo-label) to complement the traditional uncertainty approach which only focus on high-uncertainty examples 

- Deep active learning for object detection. BMVC 2018. [[paper]()]


- Active learning for deep detection network. ICCV 2019 [[paper](https://arxiv.org/pdf/1911.09168.pdf)][[code in Tensorflow](https://gitlab.com/haghdam/deep_active_learning/-/tree/master)]
   - Use consistency of pixel's objectiveness with respect to its neighborhood pixels as uncertainty measure. The formula is very similar to **BALD**, taking the difference between entropy of average and average entropy. 
   - Uncertainty for a image is the average of max-pooled scores


### Structured

- Deep Bayesian Active Learning with Image Data. PMLR 2017 [[paper](http://proceedings.mlr.press/v70/gal17a/gal17a.pdf)][[code in Keras](https://github.com/Riashat/Deep-Bayesian-Active-Learning)]. **DBAL**
    - Based on BALD, use mutual information between model prediction and model posterior as uncertainty acquisation function (Idea: A sample is selected when the ensemble model is uncertain on average but there exist subsets of models producing diagreeing predictions with high certainty)
    - I(y,w|x, D_train) = H(y|x, D_train) - E_{p(w|D_train)}(H(y|x, w))

- Bayesian batch active learning as sparse subset approximation. arxiv. 2019. [[paper]
- (https://arxiv.org/pdf/1908.02144.pdf)]
   - Choose D’ such that 𝑝(𝜃│𝐷_0 ∪ D’) best approximates 𝑝(𝜃│𝐷_0 ∪ 𝐷) 

- Learning Loss for Active Learning. CVPR 2019 [[paper](https://openaccess.thecvf.com/content_CVPR_2019/papers/Yoo_Learning_Loss_for_Active_Learning_CVPR_2019_paper.pdf)][[code in Pytorch](https://github.com/Mephisto405/Learning-Loss-for-Active-Learning)] **LL4AL**
   - Introduce an additional regressor to learn the "loss" of a sample. Then given an unlabelled sample, we can predict its loss without having to know its ground-truth
   - Training is batch-wise, the loss for "loss" requires some contrastive learning

- Bayesian Generative Active Deep Learning. ICML 2019 [[paper](https://arxiv.org/pdf/1904.11643.pdf)][[code in Pytorch](https://github.com/toantm/BGADL)] **BGADL**
   - First use BALD to select informative samples. Then use VAE-ACGAN (as effective data augmentation) to generate new samples that are as informative as the selected one 

   
## Diversity based

Diversity has 3 interpretations:
<1> Selected unlabelled data are unique
<2> Selected unlabelled data have different distribution to already labelled data
<3> Labelled + Selected unlabelled data best approximate the full data distribution

- Active deep learning for classification of hyperspectral images. IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing 2016. [[paper](https://arxiv.org/pdf/1611.10031.pdf)]
   - Select subset of data as sparse subset selection

- Deep Similarity-Based Batch Mode Active Learning with Exploration-Exploitation. 2017 IEEE International Conference on Data Mining (ICDM). [[paper](https://ieeexplore.ieee.org/document/8215530)]
   - 𝑥∗=𝑎𝑟𝑔𝑚𝑎𝑥_𝑥 E(x)−𝛽𝑆𝑖𝑚(𝑥) (uncertainty-similarity of x w.r.t already selected data)

- Active learning for convolutional neural network: A core-set approach. ICLR 2018 [[paper](https://arxiv.org/pdf/1708.00489.pdf)][[code in Tensorflow](https://github.com/ozansener/active_learning_coreset)] **Core-set**
   - Diversity-based selection, selected unlabelled data + labelled data should be close to the distribution of all training data. Use K-center to optimize. We are essentially solving. i.e. x_i is random training point, s0+s1 are initial labelled samples + selected unlabelled samples. We want to choose b center points such that the largest distance between a data point and its nearest center is minimized. In other words, s0+s1 has high coverage on the distributions of x_i. 

- Diverse mini-batch Active Learning. 2019 arxiv. [[paper](https://arxiv.org/pdf/1901.05954.pdf)]
   - Very similar to Core-set, here just apply k-means clustering and take data points closest to the k centroids 
   
- Variational Adversarial Active Learning. ICCV 2019 [[paper](https://openaccess.thecvf.com/content_ICCV_2019/papers/Sinha_Variational_Adversarial_Active_Learning_ICCV_2019_paper.pdf)][[code in Pytorch](https://github.com/sinhasam/vaal)] **VAAL**
   - Similar to **BGADL**, it trains Beta-VAE-GAN(GAN only has discriminator, no generator) to project image into latent vector then discriminate whether it is labeled/unlabelled. Difference is that **VAAL** is not uncertainty-based, it will select images where the discriminator thinks they are unlabelled images with high confidence. i.e. Select images that are significantly different from labelled images. 

## Hybrid based

- Deep Batch Active Learning by Diverse, Uncertain Gradient Lower Bounds. ICLR 2020. [[paper][https://arxiv.org/pdf/1906.03671.pdf]] **BADGE**
   - Gradient Norm represents the uncertainty
   - Use k-menas++ to ensure diversity
   
- Deep Active Learning: Unified and Principled Method for Query and Training. PMLR 2020. [[paper](http://proceedings.mlr.press/v108/shui20a/shui20a.pdf)]
   - Based on both uncertainty and diversity. Contribution is more on diversity part.
   - Similar to the above two SOTA, it tries to make L(labelled)+B(selected unlabelled) --> D(total) by minimizing the Wasserstein distance (EMD distance in continuous case) between D and L+B. It can be shown that [[link](https://blog.csdn.net/c9Yv2cf9I06K2A9E/article/details/86762056)] minimizing Wassertein distance between 2 distribution p and q is equivalent of the following min-max optimization on some function f(.). 

- Contextual Diversity for Active Learning. ECCV 2020 [[paper](https://arxiv.org/pdf/2008.05723)][[code in Pytorch](https://github.com/sharat29ag/CDAL)] **CDAL**
   - Based on both uncertainty and diversity. It tries to select samples with different class confusion (distribution of prediction confidence is different) to enrich the contextual diversity
   - It implements different selection strategies: CDAL+Core-Set, CDAL+RL, Contextual Diversity, Visual representation, Semantic representation

- State-Relabeling Adversarial Active Learning. CVPR 2020. [[paper](https://openaccess.thecvf.com/content_CVPR_2020/papers/Zhang_State-Relabeling_Adversarial_Active_Learning_CVPR_2020_paper.pdf)] **SRAAL** No code
   - VAE + GAN
   - Two VAEs to learn unified representation: One VAE is unsupervised where the decoder task is to reconstruct the original image, the other is supervised where the decoder task is for classification
   - GAN discriminator is only for adversarial training, making the representation learner more robust
   - Novel uncertainty measure
   - Sampling is like K-center 
   
   
   
## Insufficient data for DL
- Cost-effective active learning for deep image classification. IEEE Transactions on Circuits and Systems for Video Technology, 2016. [[paper](https://arxiv.org/pdf/1701.03551.pdf)]
   - Do not discard certain samples, assign them pseudo-labels 

- Generative adversarial active learning. arxiv, 2017. [[paper](https://arxiv.org/pdf/1702.07956.pdf)]
   - Train a SVM classifier, use GAN to generate instances to query
   - They claim the synthesized instances might be closer to the descision boundary, thus more informative?
   
- Bayesian generative active deep learning. PMLR, 2019. [[paper](https://arxiv.org/pdf/1904.11643.pdf)]
   - Besides AL, it trains VAE-ACGAN to generate new images that is as informative as the AL selected ones




# TODO

- Towards Fine-grained Sampling for Active Learning in Object Detection. CVPR 2020 workshop [[paper](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w54/Desai_Towards_Fine-Grained_Sampling_for_Active_Learning_in_Object_Detection_CVPRW_2020_paper.pdf)] No code


- Multiple Instance Active Learning for Object Detection. 

