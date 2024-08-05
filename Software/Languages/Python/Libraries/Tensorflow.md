Eager execution
evaluates operations immediately, without building graphs (easier to debug)
```python
import tensorflow as tf

# Enable eager execution
tf.config.experimental_run_functions_eagerly(True)

# Define some tensors
a = tf.constant([[1, 2], [3, 4]])
b = tf.constant([[5, 6], [7, 8]])

# Perform a matrix multiplication
c = tf.matmul(a, b)

print("Eager Execution:")
print(c)

```

Graph Execution
performance and deployment
```python
import tensorflow as tf

# Disable eager execution
tf.compat.v1.disable_eager_execution()

# Define the computational graph
a = tf.constant([[1, 2], [3, 4]]) # constant tensor a as node
b = tf.constant([[5, 6], [7, 8]]) # same
c = tf.matmul(a, b) # same

# Create a session to run the graph
with tf.compat.v1.Session() as sess:
    result = sess.run(c)
    print("Graph Execution:")
    print(result)

```
Advanced example
```python
import tensorflow as tf
from tensorflow.keras.datasets import mnist
from tensorflow.keras.utils import to_categorical

# Disable eager execution
tf.compat.v1.disable_eager_execution()

# Load and preprocess the MNIST dataset
(x_train, y_train), (x_test, y_test) = mnist.load_data()
x_train = x_train.reshape(-1, 28, 28, 1).astype('float32') / 255.0 #32 bit float
x_test = x_test.reshape(-1, 28, 28, 1).astype('float32') / 255.0
y_train = to_categorical(y_train, 10)
y_test = to_categorical(y_test, 10)

# Define the computational graph
tf.compat.v1.reset_default_graph()

# Input placeholders
X = tf.compat.v1.placeholder(tf.float32, shape=[None, 28, 28, 1], name='X')
Y = tf.compat.v1.placeholder(tf.float32, shape=[None, 10], name='Y')

# Convolutional layer 1
conv1 = tf.compat.v1.layers.conv2d(X, filters=32, kernel_size=(5, 5), padding='same', activation=tf.nn.relu)
pool1 = tf.compat.v1.layers.max_pooling2d(conv1, pool_size=(2, 2), strides=2)

# Convolutional layer 2
conv2 = tf.compat.v1.layers.conv2d(pool1, filters=64, kernel_size=(5, 5), padding='same', activation=tf.nn.relu)
pool2 = tf.compat.v1.layers.max_pooling2d(conv2, pool_size=(2, 2), strides=2)

# Flatten the output of the second pooling layer
flat = tf.compat.v1.layers.flatten(pool2)

# Fully connected layer
fc = tf.compat.v1.layers.dense(flat, units=1024, activation=tf.nn.relu)

# Output layer
logits = tf.compat.v1.layers.dense(fc, units=10)

# Define loss and optimizer
loss = tf.reduce_mean(tf.compat.v1.nn.softmax_cross_entropy_with_logits(logits=logits, labels=Y))
optimizer = tf.compat.v1.train.AdamOptimizer(learning_rate=0.001).minimize(loss)

# Accuracy metric
correct_prediction = tf.equal(tf.argmax(logits, 1), tf.argmax(Y, 1))
accuracy = tf.reduce_mean(tf.cast(correct_prediction, tf.float32))

# Create a session to run the graph
with tf.compat.v1.Session() as sess:
    sess.run(tf.compat.v1.global_variables_initializer())

    # Training parameters
    num_epochs = 10
    batch_size = 128
    num_batches = len(x_train) // batch_size

    for epoch in range(num_epochs):
        for batch in range(num_batches):
            batch_x = x_train[batch * batch_size: (batch + 1) * batch_size]
            batch_y = y_train[batch * batch_size: (batch + 1) * batch_size]
            sess.run(optimizer, feed_dict={X: batch_x, Y: batch_y})

        # Calculate accuracy for the epoch
        train_accuracy = sess.run(accuracy, feed_dict={X: x_train, Y: y_train})
        test_accuracy = sess.run(accuracy, feed_dict={X: x_test, Y: y_test})
        print(f"Epoch {epoch + 1}/{num_epochs}, Training Accuracy: {train_accuracy:.4f}, Test Accuracy: {test_accuracy:.4f}")

    # Print final test accuracy
    final_test_accuracy = sess.run(accuracy, feed_dict={X: x_test, Y: y_test})
    print(f"Final Test Accuracy: {final_test_accuracy:.4f}")

```