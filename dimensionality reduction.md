# dimensionality reduction

## preserve the pairwise distance structure

- PCA

  Points that are dissimilar that would fall apart from each other. This is to preserve some large pairwise distance in the map.

- MDS

- sammon mapping
- NCA (Goldberger et al., 2005)

## preserve of local distance over global distance

- [t-SNE](https://lvdmaaten.github.io/publications/papers/JMLR_2008.pdf)

  a popular implementation of t-SNE is using Barnes-Hut approximation

  - [flt-sne](https://github.com/KlugerLab/FIt-SNE)

    accelerate t-SNE, one of the implementation

- LLE,locally linear embedding

- Isomap

- LargeVis

- Laplacian eigenmaps

- diffusion maps

- MVU weinberger et al. 2004

- umap

## out-of-sample extension

- Nystrom approximation (Bengio et al., 2004),

## neural network based approaches

key words: parametric, dimension reduction,autoencoder, neural network

- autoencoder

  http://mcn2017public.pbworks.com/w/file/fetch/137810175/HintonSalakhudtkinov2006.pdf

  they focus on maximize the variance in the latent space

  example: https://towardsdatascience.com/autoencoder-on-dimension-reduction-100f2c98608c

  http://gradientdescending.com/pca-vs-autoencoders-for-dimensionality-reduction/

  compare with PCA https://medium.com/@ee18m003/autoencoder-and-pca-for-dimensionality-reduction-on-mnist-dataset-with-code-dace21d87432

- [Learning a Nonlinear Embedding by Preserving Class Neighbourhood Structure](http://proceedings.mlr.press/v2/salakhutdinov07a/salakhutdinov07a.pdf)

  autoencoder, try to preserve the knn property

  [Neighbourhood Components Analysis](https://proceedings.neurips.cc/paper/2004/file/42fe880812925e520249e808937738d2-Paper.pdf)

- train a NN to learn t-SNE mapping

  [Learning a Parametric Embedding by Preserving Local Structure](https://lvdmaaten.github.io/publications/papers/AISTATS_2009.pdf)

  only the mapping, but use the t-SNE KL as loss

  python implementation:

  https://github.com/jsilter/parametric_tsne

  https://github.com/Academich/param_tsne

  https://github.com/johnhw/tsne_demo

  https://github.com/kylemcdonald/Parametric-t-SNE

  

- 

- [Deep Supervised t-Distributed Embedding](https://icml.cc/Conferences/2010/papers/149.pdf)

- parametrization

- [Deep Auto-Encoder Neural Networks in Reinforcement Learning](http://ml.informatik.uni-freiburg.de/former/_media/publications/langeijcnn2010.pdf)

  Similar parametrizations have been proposed before, e.g., in NeuroScale (Lowe and Tipping, 1996) and back-constrained GPLVMs (Lawrence and Candela, 2006).

- [a folded neural network autoencoder for dimensionality reduction](https://reader.elsevier.com/reader/sd/pii/S1877050912007272?token=F2E8595924308C8E445972892CD63AA5196B0B97FA6FE909048D1F43C0C49C94E444E5BC63D5B1B73DA65F93FC3161DC)

- https://lvdmaaten.github.io/publications/papers/MachLearn_2012.pdf

# metric learning

- supervised
- unsupervised



