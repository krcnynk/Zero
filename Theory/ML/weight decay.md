Status: **Editing**

Tags: [[Machine Learning]]

# weight decay

Before throwing away the features, we can apply regularization, lambda is constant
$$L(\mathbf{w}, b) = \frac{1}{n}\sum_{i=1}^n \frac{1}{2}\left(\mathbf{w}^\top \mathbf{x}^{(i)} + b - y^{(i)}\right)^2.$$$$L(\mathbf{w}, b) + \frac{\lambda}{2} \|\mathbf{w}\|^2.$$L2 norm (ridge regression) minimizes gives penalty to large components
If we used L1 norm here (lasso regression), we will minimize some but not others

# References