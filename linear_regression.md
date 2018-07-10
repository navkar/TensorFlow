## A linear regression learning algorithm using Tensor flow Library
### Author : Naveen Karamchetti

* Find the linear relationship between datasets which is in the form y=w∗x+b

```python
import numpy as np
import tensorflow as tf
import numpy.random as rand

## Start Code 
trainX = np.asarray([4.4,7.2,3.712,6.42,4.168,8.79,7.88,7.59,2.167,7.042,10.71,5.33,9.97,5.64,9.27,3.1,3.9], dtype='float64')
                         
trainY = np.asarray([2.28644, 3.25412, 2.0486672, 2.984552, 2.2062608, 3.803624 ,3.489128, 3.388904 ,1.5147152, 3.1995152, 4.467176, 2.607848 ,4.211432, 2.714984, 3.969512, 1.83716, 2.11364], dtype='float64')
## End Code 

num_samples = trainX.shape[0]

X = tf.placeholder(dtype='float32')
Y = tf.placeholder(dtype='float32')

## Start Code 
w = tf.Variable(rand.randn(), name="weight")
b = tf.Variable(rand.randn(), name="bias")
## End Code 

num_iter = 10000 
learning_rate = 0.01

# Train the model using gradient descent to minimize the cost. Initialize the number of iterations and learning rate 

pred = tf.add(tf.multiply(X, w), b)
cost = tf.reduce_sum(tf.pow(pred-Y,2))/(2*num_samples)

optimizer = tf.train.GradientDescentOptimizer(learning_rate)
train = optimizer.minimize(cost)


ext_file = open("Output.txt", "w")
model = tf.global_variables_initializer()
with tf.Session() as session:
    session.run(model)
    for i in range(num_iter):
        session.run(train, feed_dict={X: trainX , Y: trainY})
    w = session.run(w)
    b = session.run(b)
    with open("Output.txt", "w") as text_file:
        text_file.write("w= %f\n" % w)
        text_file.write("b= %f" % b)
```
