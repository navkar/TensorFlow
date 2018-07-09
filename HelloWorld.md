# A Simple Hello World in TensorFlow

We are first importing TensorFlow library with following code:

```
import tensorflow as tf
```

Then creating a constant with the following code:

```
msg = tf.constant('Say Hello to TensorFlow!')
```

Constants value cannot be modified once created.
Then creating an instance of TensorFlow session with following code:

```
sess = tf.Session()
```

* The tf.Session() is a session management class in TensorFlow which is responsible for running the TensorFlow operations. 
* To run the TensorFlow operations we will use the method sess.run() as shown below:

```
print(sess.run(msg))
```

## Complete Program
```
#TensorFlow Hello World example
#import tensorflow libraries
import tensorflow as tf
#create constant
msg = tf.constant('Say Hello to TensorFlow!')
#create session to run 
sess = tf.Session()
print(sess.run(msg))
```
