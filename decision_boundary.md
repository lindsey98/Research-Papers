
# Understand NN Decision boundary

- Empirical study of the topology and geometry of deep networks. CVPR 2018. [[paper](https://openaccess.thecvf.com/content_cvpr_2018/papers/Fawzi_Empirical_Study_of_CVPR_2018_paper.pdf)]
   - Classification region is nearly convex 
   - The decision boundary in the vicinity of natural images is flat in most directions, with only a very few directions that are significantly curved.
   - Principal curvature of decision boundary is asymmetric. More directions are negatively curved than positively curved.
   - Pincipal curvature directions are shared between different data points.
   - NN is vulnerable along those pincipal curvature directions


- Improving the Adversarial Robustness and Interpretability of Deep Neural Networks by Regularizing their Input Gradients. AAAI 2018. [[paper](https://arxiv.org/pdf/1711.09404.pdf)]
   - Relationship between robustness and first-order gradient
   - Add regularizer on gradient to "flatten" loss landscape

- Ensemble adversarial training: Attacks and defenses. arXiv preprint arXiv:1705.07204. [[paper](https://arxiv.org/pdf/1705.07204.pdf%20http://arxiv.org/abs/1705.07204.pdf)]
   - Gradient masking is vulnerable
   
- Obfuscated gradients give a false sense of security: Circumventing defenses to adversarial examples. PMLR 2018. [[paper](http://proceedings.mlr.press/v80/athalye18a/athalye18a.pdf)]
   - Any approach that is trying to mask/flatten gradient is vulnerable
   
- Robustness via curvature regularization, and vice versa. CVPR 2019. [[paper](https://arxiv.org/pdf/1811.09716.pdf)]
   - Relationship between robustness and Hessian matrix
   - Add regularizer on Hessian to "flatten" loss landscape

- Interpreting adversarial robustness: A view from decision surface in input space. [[paper](https://arxiv.org/pdf/1810.00144.pdf)]
   - Theratically prove the relationship between robustness vs first order Jacobian/Gradient and Hessian 


