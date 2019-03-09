---
ID: 584
post_title: TensorFlow
author: admin
post_excerpt: ""
layout: post
permalink: >
  https://cscourses.online/topics/tensorflow/
published: true
post_date: 2019-02-21 13:42:12
---
<h2>Introduction</h2>
TensorFlow is an open-source machine learning library.
<h3>Hello, TensorFlow</h3>
To use TensorFlow, first install it. You can install <a href="/topics/python">Python</a> first, then install TensorFlow via pip:
<pre>pip intall tensorflow
</pre>
Put below code in a file named example.py.
<pre>import tensorflow as tf

mnist = tf.keras.datasets.mnist

(x_train, y_train), (x_test, y_test) = mnist.load_data()
x_train, x_test = x_train / 255.0, x_test / 255.0

model = tf.keras.models.Sequential([
    tf.keras.layers.Flatten(input_shape=(28, 28)),
    tf.keras.layers.Dense(512, activation=tf.nn.relu),
    tf.keras.layers.Dropout(0.2),
    tf.keras.layers.Dense(10, activation=tf.nn.softmax)
])
model.compile(optimizer='adam',
              loss='sparse_categorical_crossentropy',
              metrics=['accuracy'])
print("Train...")
model.fit(x_train, y_train, epochs=5)
print("Evaluate...")
model.evaluate(x_test, y_test)
</pre>
TensorFlow API are easy to understand. If you have a <a href="/topics/machine-learning">machine learning</a> background but not familiar with TensorFlow, you can still roughly guess waht happened from above code.
Run command,
<pre>python example.py
</pre>
It will take some time, so be patient since most machine learning algorithms are compute-intensive. First, it will download the MNIST dataset, then train the model, after that, it will evaluate the model on the test dataset.
Now we are done. What is the next step? You can go official <a href="www.tensorflow.org">TenserFow</a> website to learn more.