

Model:
------
The Neural Network (NN) model built in the tensorflow notebook (in this folder) is given by the following image:

![the NN model used in this week's notebook](https://image.ibb.co/htxina/Linear_Classifier_Tensorflow.jpg)

Notes:
------

In the second notebook, we've substituted an entire suite of our computational nodes using an out-of-the-box tensorflow api for creating a dense layer. Consider the following suite of code from the first file:

    weights_hidden = tf.Variable(tf.random_normal([n_features, n_hidden], stddev=1), name="weights_hidden")
    
    weights_out = tf.Variable(tf.random_normal([n_hidden, n_labels], stddev=1), name="weights_out")
    
    biases_hidden = tf.Variable(tf.random_normal([n_hidden], stddev=1), name="biases_hidden")
    
    biases_out = tf.Variable(tf.random_normal([n_labels], stddev=1), name="biases_out")

followed by the following statements in a lower cell:

    hidden_inputs = tf.add(tf.matmul(features,weights_hidden),biases_hidden)
    hidden_outputs = tf.add(tf.matmul(hidden_inputs,weights_out),biases_out)
    prediction_hidden = tf.nn.relu(hidden_outputs)

The entire operation above can be simplified to one statement using tensorflow's built-in [tf.layers.dense](https://www.tensorflow.org/api_docs/python/tf/layers/dense) method. This is illustrated in the second file in this folder.

    hidden_outputs = tf.layers.dense(inputs=features, units=n_labels, activation=tf.nn.relu, use_bias=True)
