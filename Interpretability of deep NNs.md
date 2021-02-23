# Interpretability of deep NNs

## simpler model to explain complex models

## attribution methods

### Surrogate Approaches

- Marco Tulio Ribeiro, Sameer Singh, and Carlos Guestrin. 2016.**"Why Should I Trust You?": Explaining the Predictions of Any Classifier.** In* *Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining* *(**KDD '16**). Association for Computing Machinery, New York, NY, USA, 1135–1144. DOI:https://doi.org/10.1145/2939672.2939778
- **A Unified Approach to Interpreting Model Predictions.**

### Gradients approaches

- David Baehrens, Timon Schroeter, Stefan Harmeling, Motoaki Kawanabe, Katja Hansen, and KlausRobert Müller. **How to explain individual classification decisions.** Journal of Machine Learning Research, 11(Jun):1803–1831, 2010.

  *gradient*

- Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman. **Deep inside convolutional networks: Visualising image classification models and saliency maps.** In Yoshua Bengio and Yann LeCun, editors, 2nd International Conference on Learning Representations, ICLR 2014, Banff, AB, Canada, April 14-16, 2014, Workshop Track Proceedings, 2014. URL http://arxiv.org/abs/1312.6034.

  *gradient*

- Avanti Shrikumar, Peyton Greenside, Anna Shcherbina, and Anshul Kundaje. **Not just a black box: Learning important features through propagating activation differences**. arXiv preprint arXiv:1605.01713, 2016.

- Mukund Sundararajan, Ankur Taly, and Qiqi Yan. **Axiomatic attribution for deep networks**, 2017. [[paper](https://arxiv.org/pdf/1703.01365.pdf)] 

  *Integrated gradient*

- input times Gradient

- Mukund Sundararajan and Ankur Taly and Qiqi Yan. **Gradients of Counterfactuals**, 2016. [[paper](https://arxiv.org/abs/1611.02639)]

### perturbation-based forward propagation approaches

- Aditya Chattopadhyay and Piyushi Manupriya and Anirban Sarkar and Vineeth N Balasubramanian. **Neural Network Attributions: A Causal Perspective**, 2019. [[paper](https://arxiv.org/abs/1902.02302)]

### backpropagation-based approaches

- Jost Tobias Springenberg, Alexey Dosovitskiy, Thomas Brox, and Martin Riedmiller. **Striving for simplicity: The all convolutional net.** In ICLR, 2015

  *guided backprop, GBP*

- Karen Simonyan, Andrea Vedaldi, and Andrew Zisserman. **Deep inside convolutional networks: Visualisingimage classification models and saliency maps**, 2014. [[paper](https://arxiv.org/pdf/1312.6034.pdf)]

  *gradient, calculate the gradient with respect to a output at a given input*

- **Visualizing and Understanding Convolutional Networks**.[[paper](https://link.springer.com/chapter/10.1007/978-3-319-10590-1_53)]

  *deconvNet*

- Pieter-Jan Kindermans, Kristof T Schütt, Maximilian Alber, Klaus-Robert Müller, Dumitru Erhan, Been Kim, and Sven Dähne. **Learning how to explain neural networks: Pattern net and pattern attribution.** arXiv preprint arXiv:1705.05598v2, 2017.

  *pattern net*

- Ramprasaath R. Selvaraju, Michael Cogswell, Abhishek Das, Ramakrishna Vedantam, Devi Parikh, andDhruv Batra.  **Grad-cam:  Visual explanations from deep networks via gradient-based localization.**  InProceedings of the IEEE International Conference on Computer Vision (ICCV), Oct 2017. [[paper](https://openaccess.thecvf.com/content_iccv_2017/html/Selvaraju_Grad-CAM_Visual_Explanations_ICCV_2017_paper.html)]

- Chattopadhyay, Aditya and Sarkar, Anirban and Howlader, Prantik and Balasubramanian, Vineeth N. **Grad-CAM++: Generalized Gradient-based Visual Explanations for Deep Convolutional Networks***WACV 2018

  *grad cam++*

  follow up: guided grad-cam, guided grad_cam++

- Pieter-Jan Kindermans and Sara Hooker and Julius Adebayo and Maximilian Alber and Kristof T. Schütt and Sven Dähne and Dumitru Erhan and Been Kim. **The (Un)reliability of saliency methods**, 2017. [[paper](https://arxiv.org/abs/1711.00867)]

- Avanti Shrikumar, Peyton Greenside, and Anshul Kundaje. **Learning important features through propagating activation differences**, 2019. [[paper](https://arxiv.org/pdf/1704.02685.pdf)]

  *DeepLIFT*

- Grégoire Montavon, Sebastian Lapuschkin, Alexander Binder, Wojciech Samek, and Klaus-Robert Müller. **Explaining nonlinear classification decisions with deep taylor decomposition.** Pattern Recognition, 65:211–222, 2017.

### example-based approaches

- Jeyakumar, Jeya Vikranth and Noor, Joseph and Cheng, Yu-Hsi and Garcia, Luis and Srivastava, Mani. **How Can I Explain This to You? An Empirical Study of Deep Neural Network Explanation Methods**. Advances in Neural Information Processing Systems, 2020. [[paper](https://proceedings.neurips.cc/paper/2020/file/2c29d89cc56cdb191c60db2f0bae796b-Paper.pdf)] [[github](https://github.com/nesl/Explainability-Study)]

  *This paper use the most similar samples in the training dataset to explain the prediction of models.*

## explain models

### example level

- Zijie J. Wang, Robert Turko, Omar Shaikh, Haekyu Park, Nilaksh Das, Fred Hohman, Minsuk Kahng, andDuen Horng Chau. **CNN Explainer: Learning Convolutional Neural Networks with Interactive Visualization.** IEEE Transactions on Visualization and Computer Graphics (TVCG), 2020. [[paper](https://arxiv.org/abs/2004.15004)] [[code](https://github.com/poloclub/cnn-explainer)] [[live demo](http://poloclub.github.io/cnn-explainer/)]

### model level

- Hao Yuan, Jiliang Tang, Xia Hu, and Shuiwang Ji. **XGNN: Towards model-level explanations of graph neuralnetworks. ** Proceedings of the 26th ACM SIGKDD International Conference on Knowledge Discovery DataMining, Aug 2020.[[paper](https://arxiv.org/abs/2006.02587)]
- Q. Shen *et al*., **"Visual Interpretation of Recurrent Neural Network on Multi-dimensional Time-series Forecast,**" *2020 IEEE Pacific Visualization Symposium (PacificVis)*, Tianjin, China, 2020, pp. 61-70, doi: 10.1109/PacificVis48177.2020.2785.[[paper](https://ieeexplore.ieee.org/abstract/document/9086238)]











