```python
import tensorflow as tf
from tensorflow.keras import layers, models
import numpy as np

# Load and preprocess the MNIST dataset 
mnist = tf.keras.datasets.mnist (x_train, y_train), (x_test, y_test) = mnist.load_data() 
# Normalize the images to a range of [0, 1] 
x_train, x_test = x_train / 255.0, x_test / 255.0 
# Define a simple sequential model 
model = models.Sequential([ layers.Flatten(input_shape=(28, 28)), layers.Dense(128, activation='relu'), layers.Dropout(0.2), layers.Dense(10) ]) 
# Compile the model 
model.compile(optimizer='adam', loss=tf.keras.losses.SparseCategoricalCrossentropy(from_logits=True), metrics=['accuracy']) 
# Train the model 
model.fit(x_train, y_train, epochs=5) 
# Evaluate the model 
test_loss, test_acc = model.evaluate(x_test, y_test, verbose=2) print('\nTest accuracy:', test_acc)

```