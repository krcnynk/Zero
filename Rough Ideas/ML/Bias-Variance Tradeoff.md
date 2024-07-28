[source](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff)

Plagues supervised learning, stops algorithms from generalizing beyond their training set.

- The bias is an error from wrong assumptions. Features -> target outputs are missed (underfitting)
	- Model not complex enough
	- Training data too small, has insufficient or poor features
	- Model and data incompatible (linear vs non-linear)
	- Over-regularization

- The variance is an error from sensitivity to small fluctuations in training set. (overfitting)
	- [[Feature selection]]
	- Regularization
	- Cross-validation
	- Ensemble methods
	- Early stopping (pre-pruning)
	- Data augmentation
	- Pruning 