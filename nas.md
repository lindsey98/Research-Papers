
Neural Architecture search is a subset of Hyperparameter Optimization problem. As when we talking about hyperparameter, it includes architectural param (num of layers, num of nodes per layer, type of activation used) and non-architectural param (learning rate, trade-off parameter).

## Hyperparameter Optimization

### Definition: 
Algorithm is A, \lambda is the hyperparameter(s), a HPO problem is trying to ![equation](https://latex.codecogs.com/gif.latex?%5Clambda*%20%3D%20argmin_%7B%5Clambda%7D%7BL%28A_%7B%5Clambda%7D%2C%20D_%7B%5Ctextit%7Btrain%7D%7D%2C%20D_%7B%5Ctextit%7Bvalid%7D%7D%20%29%7D)

### Blackbox optimization
Given lambda, feed into a black-box model, get f(\lambda)

### Methods
- Grid search or Random search 
<img src="pic/Screenshot 2021-06-10 at 11.26.42 AM.png">
Inefficient, however RS perform better than GS when there are some unimportant dimensions

- BO-GP
Fit a probalistic model ![equation](https://latex.codecogs.com/gif.latex?%3Cf%28%5Clambda%29%2C%20%5Clambda%3E) where f(.) is the evaluation metric (loss/accuracy). Every iteration sample hyperparameter with the highest aquisation function to balance between exploration (lambda that are unexplored and with high uncertainty) and exploitation (current best lambda found). 
<img src="pic/Screenshot 2021-06-10 at 11.28.56 AM.png">

- 








## NAS
