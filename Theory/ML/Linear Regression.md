Status: **Editing**

Tags: [[Machine Learning]]

# Linear Regression

- x (features) ->y (target) is linear
- conditional mean `E[Y|X=x] = B_0 + B1.x1 + B2.x2` 3d example
- average outcome of `Y` when you know the value of `X`

![[../../z_images/Pasted image 20240815150914.png]]
This has all the features n-dimensional, one data
$$\hat{y} = \mathbf{w}^\top \mathbf{x} + b.$$
This is entire dataset
$${\hat{\mathbf{y}}} = \mathbf{X} \mathbf{w} + b,$$
where X is the design matrix, goal is to find `w` and `b`

Lets use loss function where i-th predictions are used $$l^{(i)}(\mathbf{w}, b) = \frac{1}{2} \left(\hat{y}^{(i)} - y^{(i)}\right)^2.$$

$$\mathbf{w}^*, b^* = \operatorname*{argmin}_{\mathbf{w}, b}\  L(\mathbf{w}, b).$$`
# Analytical solution
Using linear algebra, first incorporating b into the design matrix
$$\begin{aligned}
    \partial_{\mathbf{w}} \|\mathbf{y} - \mathbf{X}\mathbf{w}\|^2 =
    2 \mathbf{X}^\top (\mathbf{X} \mathbf{w} - \mathbf{y}) = 0
    \textrm{ and hence }
    \mathbf{X}^\top \mathbf{y} = \mathbf{X}^\top \mathbf{X} \mathbf{w}.
\end{aligned}
$$ $$\mathbf{w}^* = (\mathbf X^\top \mathbf X)^{-1}\mathbf X^\top \mathbf{y}$$
# Heuristic solution
n is the learning rate and B is mini batch size (hyperparameters tuned by etc. Bayesian optimization)
$$(\mathbf{w},b) \leftarrow (\mathbf{w},b) - \frac{\eta}{|\mathcal{B}|} \sum_{i \in \mathcal{B}_t} \partial_{(\mathbf{w},b)} l^{(i)}(\mathbf{w},b).$$
%% The Normal Distribution and Squared Loss this is for later, theoretical %%

# References