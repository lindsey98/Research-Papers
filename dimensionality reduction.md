# dimensionality reduction

background

- [L.J.P. van der Maaten](https://lvdmaaten.github.io/), E.O. Postma, and H.J. van den Herik. **Dimensionality reduction: A comparative review.** Online Preprint, 2008.

## preserve the pairwise distance structure

- PCA,  Principal component analysis

  Points that are dissimilar that would fall apart from each other. This is to preserve some large pairwise distance in the map.

- MDS,  multidimensional scaling

- sammon mapping
- 

## preserve of local distance over global distance

- Isomap

- J. Goldberger, S. Roweis, G.E. Hinton, and R.R. Salakhutdinov. **Neighbourhood components analysis.** In Advances in Neural Information Processing Systems, volume 17, pages 513–520, Cambridge, MA, 2005. MIT Press. [[paper](https://proceedings.neurips.cc/paper/2004/file/42fe880812925e520249e808937738d2-Paper.pdf)] 
- Geoffrey Hinton and Sam Roweis. **Stochastic Neighbor Embedding.** [[paper](https://proceedings.neurips.cc/paper/2002/file/6150ccc6069bea6b5716254057a194ef-Paper.pdf)]

- Laurens van der Maaten and Geoffrey Hinton. **Visualizing data using t-sne. Journal of machine learning research**, 9(Nov):2579–2605, 2008. [[paper](https://lvdmaaten.github.io/publications/papers/JMLR_2008.pdf)]

- George C Linderman, Manas Rachh, Jeremy G Hoskins, Stefan Steinerberger, and Yuval Kluger. **Effcient algorithms for t-distributed stochastic neighborhood embedding**. arXiv preprint arXiv:1712.09005, 2017.

  *follow up, accelerate t-SNE, one of the implementation, a popular implementation of t-SNE is using Barnes-Hut approximation*

- Jarkko Venna and Samuel Kaski. 2006. **Local multidimensional scaling**. <i>Neural Netw.</i> 19, 6 (July 2006), 889–899. [[paper](https://research.cs.aalto.fi/pml/papers/wsom05-nn.pdf)]

  *we can consider to use its metric for evaluation*

- LLE,locally linear embedding

- LargeVis

- Laplacian eigenmaps

- diffusion maps

- MVU weinberger et al. 2004

- Leland McInnes, John Healy, and James Melville. **Umap: Uniform manifold approximation and projection for dimension reduction.** arXiv preprint arXiv:1802.03426, 2018. [[paper](https://arxiv.org/pdf/2009.12981.pdf)]

  *to speep up the optimization process: using **negative sampling** from Tomas Mikolov, Ilya Sutskever, Kai Chen, Greg S Corrado, and Jeff Dean. Distributed representations of words and phrases and their compositionality. In Advances in neural information processing systems, pp. 3111–3119, 2013.*

## out-of-sample extension

- Nystrom approximation (Bengio et al., 2004),

## parametric approaches

key words: parametric, dimension reduction,autoencoder, neural network

- Geoffrey E Hinton and Ruslan R Salakhutdinov. **Reducing the dimensionality of data with neural networks.** science, 313(5786):504–507, 2006. [[paper](http://mcn2017public.pbworks.com/w/file/fetch/137810175/HintonSalakhudtkinov2006.pdf)]

  they focus on maximize the variance in the latent space

  example: https://towardsdatascience.com/autoencoder-on-dimension-reduction-100f2c98608c

  http://gradientdescending.com/pca-vs-autoencoders-for-dimensionality-reduction/

  compare with PCA https://medium.com/@ee18m003/autoencoder-and-pca-for-dimensionality-reduction-on-mnist-dataset-with-code-dace21d87432

- R.R. Salakhutdinov and G.E. Hinton. **Learning a non-linear embedding by preserving class neighbourhood structure.** In Proceedings of the 11th International Conference on Artificial Intelligence and Statistics, volume 2, pages 412–419, 2007. [[paper](http://proceedings.mlr.press/v2/salakhutdinov07a/salakhutdinov07a.pdf)]

  *nonlinear NCA, try to preserve neighbor after dimension reduction*

- Laurens Van Der Maaten. **Learning a parametric embedding by preserving local structure.** In Artificial Intelligence and Statistics, pp. 384–391, 2009. [[paper](https://lvdmaaten.github.io/publications/papers/AISTATS_2009.pdf)]

  *called **parametric-tsne**, train a NN to learn t-SNE mapping, only the mapping, but use the t-SNE KL as loss*

  python implementation:

  [impl1](https://github.com/jsilter/parametric_tsne)

  [impl2](https://github.com/Academich/param_tsne)

  [impl3](https://github.com/johnhw/tsne_demo)

  [impl4](https://github.com/kylemcdonald/Parametric-t-SNE)

  

- Jacob M. Graving, Iain D. **VAE-SNE: a deep generative model for simultaneous dimensionality reduction and clustering.** Couzin bioRxiv 2020.07.17.207993. [[paper](https://www.biorxiv.org/content/10.1101/2020.07.17.207993v1.full)]

  *use autoencoder to inverse input, loss=mse_loss + sne_loss*

- Tim Sainburg and Leland McInnes and Timothy Q Gentner. **Parametric UMAP: learning embeddings with deep neural networks for representation and semi-supervised learning.** 2020 unpublished

  [github code](https://github.com/timsainb/ParametricUMAP_paper), [umap dev0.5+](https://github.com/lmcinnes/umap), 

The development of dimension reduction technique

non-parametric: NCA-> SNE ->t-SNE-UMAP

parametric: NN and autoencoder-> nonlinear NCA->parametric-tsne->parametric umap,autoencoder

- [Deep Supervised t-Distributed Embedding](https://icml.cc/Conferences/2010/papers/149.pdf)

- parametrization

- [Deep Auto-Encoder Neural Networks in Reinforcement Learning](http://ml.informatik.uni-freiburg.de/former/_media/publications/langeijcnn2010.pdf)

  Similar parametrizations have been proposed before, e.g., in NeuroScale (Lowe and Tipping, 1996) and back-constrained GPLVMs (Lawrence and Candela, 2006).

- [a folded neural network autoencoder for dimensionality reduction](https://reader.elsevier.com/reader/sd/pii/S1877050912007272?token=F2E8595924308C8E445972892CD63AA5196B0B97FA6FE909048D1F43C0C49C94E444E5BC63D5B1B73DA65F93FC3161DC)

- https://lvdmaaten.github.io/publications/papers/MachLearn_2012.pdf

# metric learning

- supervised
- unsupervised

# nearest neighbor search

[wiki page](https://en.wikipedia.org/wiki/Nearest_neighbor_search) NNS is a form of **proximity search**. There are a lot of algorithm to speed up the optimization or approximate search. So NNS is related to **NCA** and other follow up work.

key works: fast knn search, nearest neighbors search, locally sensitive hash, approximate algorithm

- Dong, Wei, Charikar Moses, and Kai Li. **"Efficient k-nearest neighbor graph construction for generic similarity measures."** Proceedings of the 20th international conference on World wide web. ACM, 2011. [[paper](https://www.cs.princeton.edu/cass/papers/www11.pdf)]

  *PyNNDescent is a python implementation of this work. This library can be extremely fast to find k-nn.* [[python implmentation](https://github.com/lmcinnes/pynndescent)]



