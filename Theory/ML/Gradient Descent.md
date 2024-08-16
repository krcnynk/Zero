Status: **Editing**

Tags: [[Machine Learning]]

# Gradient Descent

It is a mathematical optimization method
goal is to find local minima of multivariate differentiable function
assume a line fit in 2D
using the cost function 
$$\text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2$$
$$\hat{y}_i = m\hat{x}_i + b$$
![[../../z_images/imageMSE.png]]
We can now find $$\frac{\partial f}{\partial m},\frac{\partial f}{\partial b}$$
and take small steps towards a local minima (a is the learning rate)
$$m=m-\alpha \frac{\partial f}{\partial m}$$
$$b=b-\alpha \frac{\partial f}{\partial b}$$
stop at region where f changes very little

## Batch Gradient
n observation from dataset -> update m&b -> entire dataset needs to fit in memory
## SGD
update m&b at each observation
## Minibatch
n observations are split into smaller chunks -> update m&b



# References